# FIAP - Faculdade de Informática e Administração Paulista

<img width="2385" height="642" alt="image" src="https://github.com/user-attachments/assets/594c28cc-66ae-40ac-b8a6-8c39e6f14de4" />

# O Despertar da Rede Neural

## 👨‍🎓 Integrantes
- [CAUAN OTTO RODRIGUES SOUSA (RM567940)](https://www.linkedin.com/in/cauanotto)
- [FERNANDO A GURGEL (RM567606)](https://www.linkedin.com/in/fernando-gurgel-75aa8369)
- [IRACI MONTEIRO SOUZA (RM567544)](https://www.linkedin.com/in/iraci-souza-bab42034)
- [MARIA LUISA RODRIGUES NASCIMENTO (RM567659)](https://www.linkedin.com/in/malu-rodrigues-bb756b271)
- [RAFAELA TORRES MARTINS (RM567735)](https://www.linkedin.com/in/rafaela-torres222)

## 👩‍🏫 Professores
- **Tutor(a):** [ANA CRISTINA DOS SANTOS](https://www.linkedin.com/company/inova-fusca)
- **Coordenador(a):** [ANDRÉ GODOI](https://www.linkedin.com/in/andregodoichiovato)

---

## 📌 Contexto

A **FarmTech Solutions**, empresa de tecnologia voltada ao agronegócio, está expandindo sua atuação para a área de **visão computacional**. Um cliente do setor agrícola procurou a empresa com uma necessidade crítica: a **detecção precoce de doenças em plantações**, que hoje é feita manualmente — um processo lento, sujeito a falhas e com altos custos operacionais.

Este projeto foi desenvolvido como **prova de conceito** para demonstrar ao cliente a viabilidade de um sistema automatizado de detecção baseado em redes neurais convolucionais, capaz de analisar imagens de plantas e identificar sinais de doença em tempo real.

---

## 🎯 Objetivo

Desenvolver e avaliar um sistema de **detecção de objetos** utilizando **YOLOv5** (You Only Look Once, versão 5) capaz de identificar **plantas saudáveis** e **plantas doentes** a partir de imagens, comparando o desempenho do modelo em diferentes configurações de treinamento (30 vs 60 épocas).

---

## 📊 Dataset

A base de imagens foi organizada manualmente e rotulada via [MakeSense.ai](https://www.makesense.ai/), seguindo o formato de anotação YOLO (bounding boxes com coordenadas normalizadas).

| Classe | Treino | Validação | Teste | Total |
|--------|--------|-----------|-------|-------|
| Planta Saudável | 32 | 4 | 4 | 40 |
| Planta Doente | 32 | 4 | 4 | 40 |
| **Total** | **64** | **8** | **8** | **80** |

> ⚠️ As imagens de validação e teste são **inéditas** — não foram utilizadas durante o treinamento, evitando overfitting e garantindo uma avaliação realista do modelo.

**Link do dataset:** [Google Drive](https://drive.google.com/drive/folders/1JokeVmMrXhfRU3kh9TMkYff-34FXyE9f)

### Estrutura de pastas no Google Drive

```
FIAP/
├── images/
│   ├── train/      (64 imagens: 32 saudáveis + 32 doentes)
│   ├── val/        (8 imagens: 4 saudáveis + 4 doentes)
│   └── test/       (8 imagens: 4 saudáveis + 4 doentes)
├── labels/
│   ├── train/      (64 arquivos .txt com bounding boxes)
│   └── val/        (8 arquivos .txt com bounding boxes)
└── plantas.yaml    (configuração do dataset para o YOLOv5)
```

---

## ⚙️ Metodologia

1. **Coleta e Rotulação:** imagens coletadas e rotuladas manualmente no [MakeSense.ai](https://www.makesense.ai/), gerando arquivos `.txt` no formato YOLO (classe, x_centro, y_centro, largura, altura)
2. **Treinamento:** modelo YOLOv5s (small) com **transfer learning** a partir de pesos pré-treinados no COCO (`yolov5s.pt`), executado no Google Colab com GPU T4
3. **Comparação:** duas execuções com parâmetros idênticos, variando apenas o número de épocas (**30 e 60**), para avaliar o impacto na acurácia
4. **Validação:** métricas automáticas (Precision, Recall, mAP@0.5, mAP@0.5:0.95) calculadas sobre o conjunto de validação (8 imagens)
5. **Teste:** inferência sobre **imagens inéditas** com `detect.py` para demonstrar capacidade de generalização

---

## 📈 Resultados - (PENDENTE)

### Comparação: 30 vs 60 épocas

| Métrica | 30 Épocas | 60 Épocas |
|---------|----------|----------|
| Precision | X.XXX | X.XXX |
| Recall | X.XXX | X.XXX |
| mAP@0.5 | X.XXX | X.XXX |
| mAP@0.5:0.95 | X.XXX | X.XXX |

> ⚠️ **Preencha com os valores reais** obtidos após executar o notebook.

### Exemplos de detecção (PENDENTE)

> Inclua aqui 2-4 prints das imagens de teste processadas pelo modelo (disponíveis em `yolov5/runs/detect/teste_final/`). Para incluir no README do GitHub, faça upload das imagens na pasta do repositório e referencie-as assim:
>
> `![Teste 1](caminho/da/imagem.jpg)`

---

## 🧪 Conclusões

- O **YOLOv5** se mostrou eficaz para detectar plantas doentes mesmo com um dataset reduzido (80 imagens)
- O uso de **transfer learning** foi essencial para convergência rápida com poucos dados de treinamento
- O treinamento com [30/60] épocas apresentou melhor desempenho, com mAP@0.5 de X.XX
- A separação rigorosa entre treino, validação e teste garante a confiabilidade das métricas

**Limitações identificadas:**
- Dataset pequeno (80 imagens) pode restringir a robustez em cenários reais
- Pouca variabilidade de condições (iluminação, ângulos, estágios de doença)
- Ausência de data augmentation

**Trabalhos futuros:**
- Expansão do dataset para 500+ imagens por classe
- Testes com YOLOv8 para comparação de arquiteturas
- Implementação com ESP32-CAM para uso em campo
- Inclusão de mais classes para diagnóstico específico de doenças

---

## 🎬 Vídeo Demonstrativo (PENDENTE)

📹 [Assistir no YouTube (não listado)](https://youtube.com/COLOQUE_SEU_LINK_AQUI)

> Vídeo de até 5 minutos demonstrando o treinamento, validação, teste e resultados do projeto.

---

## 📓 Notebook do Projeto

📔 [Acessar no Google Colab](https://colab.research.google.com/drive/1oGBpVkBhn6dQvNuHnu6EJLyhXG9fafff?usp=sharing)

> O notebook está com todas as células executadas e contém documentação completa em Markdown, incluindo análise comparativa de 30 vs 60 épocas.

---

## 🚀 Como Executar

### Requisitos
- Python 3.10+
- Google Colab com GPU habilitada (Runtime > Change runtime type > T4 GPU)

### Passos
1. Abra o notebook no Google Colab
2. Ative a GPU: `Runtime > Change runtime type > T4 GPU`
3. Execute todas as células sequencialmente (o notebook conecta automaticamente ao Google Drive)
4. Os resultados são salvos automaticamente em `yolov5/runs/`

### Principais bibliotecas utilizadas
- `torch` / `torchvision` — framework de deep learning (PyTorch)
- `opencv-python` — processamento de imagens
- `matplotlib` — visualização de gráficos e resultados
- `pandas` — manipulação de dados tabulares (métricas)
- **YOLOv5** (Ultralytics) — framework de detecção de objetos
