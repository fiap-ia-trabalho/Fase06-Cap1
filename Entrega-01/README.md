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

Desenvolver e avaliar um sistema de **detecção de objetos** utilizando **YOLOv5** (You Only Look Once, versão 5) capaz de identificar **plantas saudáveis** e **plantas doentes** a partir de imagens, comparando o desempenho do modelo em diferentes configurações de treinamento (30 vs 60 épocas), e posteriormente confrontando os resultados com abordagens alternativas (YOLO tradicional e CNN treinada do zero).

---

## 📊 Dataset

A base de imagens foi organizada manualmente e rotulada via [MakeSense.ai](https://www.makesense.ai/), seguindo o formato de anotação YOLO (bounding boxes com coordenadas normalizadas).

| Classe | Treino | Validação | Teste | Total |
|--------|--------|-----------|-------|-------|
| Planta Saudável | 32 | 4 | 4 | 40 |
| Planta Doente | 32 | 4 | 4 | 40 |
| **Total** | **64** | **8** | **8** | **80** |

> ⚠️ As imagens de validação e teste são **inéditas** — não foram utilizadas durante o treinamento, evitando overfitting e garantindo uma avaliação realista do modelo.

**Link do dataset:** [Google Drive](https://drive.google.com/drive/u/1/folders/1JokeVmMrXhfRU3kh9TMkYff-34FXyE9f)

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

# 📦 ENTREGA 1 — YOLO Adaptável com Transfer Learning

## ⚙️ Metodologia

1. **Coleta e Rotulação:** imagens coletadas e rotuladas manualmente no [MakeSense.ai](https://www.makesense.ai/), gerando arquivos `.txt` no formato YOLO (classe, x_centro, y_centro, largura, altura)
2. **Treinamento:** modelo YOLOv5s (small) com **transfer learning** a partir de pesos pré-treinados no COCO (`yolov5s.pt`), executado no Google Colab com GPU T4
3. **Comparação:** duas execuções com parâmetros idênticos, variando apenas o número de épocas (**30 e 60**), para avaliar o impacto na acurácia
4. **Validação:** métricas automáticas (Precision, Recall, mAP@0.5, mAP@0.5:0.95) calculadas sobre o conjunto de validação (8 imagens)
5. **Teste:** inferência sobre **imagens inéditas** com `detect.py` para demonstrar capacidade de generalização

## 📈 Resultados — Entrega 1 (PENDENTE)

### Comparação: 30 vs 60 épocas

| Métrica | 30 Épocas | 60 Épocas |
|---------|----------|----------|
| Precision | X.XXX | X.XXX |
| Recall | X.XXX | X.XXX |
| mAP@0.5 | X.XXX | X.XXX |
| mAP@0.5:0.95 | X.XXX | X.XXX |

> ⚠️ **Preencha com os valores reais** obtidos após executar o notebook.

### Exemplos de detecção

> Inclua aqui 2-4 prints das imagens de teste processadas pelo modelo (disponíveis em `yolov5/runs/detect/teste_final/`). Para incluir no README do GitHub, faça upload das imagens na pasta do repositório e referencie-as assim:
>
> `![Teste 1](caminho/da/imagem.jpg)`

## 🧪 Conclusões — Entrega 1

- O **YOLOv5** se mostrou eficaz para detectar plantas doentes mesmo com um dataset reduzido (80 imagens)
- O uso de **transfer learning** foi essencial para convergência rápida com poucos dados de treinamento
- O treinamento com [30/60] épocas apresentou melhor desempenho, com mAP@0.5 de X.XX
- A separação rigorosa entre treino, validação e teste garante a confiabilidade das métricas

**Limitações identificadas:**
- Dataset pequeno (80 imagens) pode restringir a robustez em cenários reais
- Pouca variabilidade de condições (iluminação, ângulos, estágios de doença)
- Ausência de data augmentation

### 📓 Notebook — Entrega 1

📔 [Acessar no Google Colab](https://colab.research.google.com/drive/1oGBpVkBhn6dQvNuHnu6EJLyhXG9fafff?usp=sharing)

> O notebook está com todas as células executadas e contém documentação completa em Markdown, incluindo análise comparativa de 30 vs 60 épocas.

---

# 📦 ENTREGA 2 — Comparação de Abordagens

## 🔬 Objetivo da Entrega 2

Comparar a abordagem da Entrega 1 (YOLO adaptável) com duas alternativas para avaliar criticamente qual solução é mais adequada para o problema da FarmTech Solutions:

1. **YOLO Adaptável (Entrega 1):** YOLOv5 com fine-tuning no nosso dataset — **detecção de objetos**
2. **YOLO Tradicional:** YOLOv3 pré-treinada no COCO, sem customização — **detecção de objetos genéricos**
3. **CNN Treinada do Zero:** rede convolucional construída manualmente — **classificação de imagens**

## 🏗️ Abordagens Implementadas

### Abordagem 1 — YOLO Adaptável (recap da Entrega 1)

O modelo YOLOv5s foi treinado com **transfer learning** sobre nosso dataset customizado. Esta abordagem combina a capacidade de **localizar** (bounding box) e **classificar** (saudável/doente) os objetos na imagem simultaneamente.

- **Tipo de tarefa:** detecção de objetos
- **Treinamento:** fine-tuning com 30 e 60 épocas
- **Resultado:** mAP@0.5 = X.XX

### Abordagem 2 — YOLO Tradicional (sem customização)

Utilizamos a **YOLOv3 pré-treinada no COCO** (80 classes genéricas) diretamente sobre nossas imagens, **sem nenhum treinamento adicional**. O objetivo é demonstrar que um modelo genérico **não é suficiente** para resolver problemas específicos de domínio.

- **Tipo de tarefa:** detecção de objetos (classes genéricas do COCO)
- **Treinamento:** nenhum (zero-shot)
- **Resultado:** não consegue distinguir planta saudável de doente, pois essas classes não existem no COCO
- **Implementação:** baseada no Capítulo 10 do material FIAP (Darknet + YOLOv3)

### Abordagem 3 — CNN Treinada do Zero

Construímos uma **CNN manualmente** com camadas Conv2D + MaxPooling + Dense, seguindo o Capítulo 9 do material FIAP. Esta rede foi treinada do zero no nosso dataset para **classificar** imagens inteiras como "planta saudável" ou "planta doente".

- **Tipo de tarefa:** classificação de imagens (não localiza, apenas classifica)
- **Treinamento:** do zero, ~X minutos
- **Resultado:** acurácia de X.XX%
- **Arquitetura:** Conv2D(16) → MaxPool → Conv2D(32) → MaxPool → Conv2D(64) → MaxPool → Flatten → Dense(64) → Dense(32) → Dense(2, softmax)

## 📊 Tabela Comparativa Final

| Critério | YOLO Adaptável (E1) | YOLO Tradicional | CNN do Zero |
|----------|-------------------|-----------------|-------------|
| **Tipo de tarefa** | Detecção de objetos | Detecção de objetos | Classificação |
| **Treinamento necessário?** | Sim (fine-tuning) | Não (zero-shot) | Sim (do zero) |
| **Tempo de treinamento** | ~XX min | 0 min | ~X min |
| **Tempo de inferência** | ~30ms/img | ~XXms/img | ~Xms/img |
| **Precisão / Acurácia** | mAP@0.5 = X.XX | N/A (classes erradas) | Acurácia = X.XX% |
| **Detecta plantas doentes?** | ✅ Sim | ❌ Não | ✅ Sim (só classifica) |
| **Facilidade de uso** | Média | Muito fácil | Média |
| **Adaptabilidade ao domínio** | Excelente | Péssima | Boa |

> ⚠️ **Preencha com os valores reais** obtidos após executar o notebook da Entrega 2.

## 🔍 Análise Crítica

### Facilidade de uso / Integração

- **YOLO Tradicional:** a mais fácil — basta baixar os pesos e rodar. Porém, é inútil para nosso problema, pois não reconhece classes customizadas.
- **YOLO Adaptável:** esforço moderado (coleta, rotulação, treinamento), mas com resultado superior.
- **CNN do Zero:** esforço comparável ao YOLO adaptável, porém resolve apenas classificação (não localiza o objeto na imagem).

### Precisão do modelo

- **YOLO Adaptável:** melhor resultado geral — mAP@0.5 de X.XX, capaz de localizar E classificar.
- **YOLO Tradicional:** sem utilidade para nosso domínio — as classes "planta saudável/doente" não existem no COCO.
- **CNN do Zero:** acurácia de X.XX%. Viável para classificação simples, mas sem capacidade de localização.

### Tempo de treinamento e inferência

- **YOLO Tradicional:** 0 min de treino (mas sem resultado útil).
- **CNN do Zero:** treino mais rápido (~X min), inferência mais rápida (~Xms).
- **YOLO Adaptável:** treino mais longo (~XX min), mas inferência adequada para tempo real (~30ms).

## 🧪 Conclusão — Entrega 2

Na Visão Computacional, **não existe uma solução universalmente melhor** — tudo depende do cenário de aplicação. Para o problema da FarmTech Solutions:

1. **A YOLO Adaptável é a melhor abordagem** — combina detecção (localização + classificação) com boa precisão e tempo de inferência adequado para uso em tempo real.

2. **A CNN do Zero é uma alternativa viável** para cenários que exigem apenas classificação ("esta foto é de planta saudável ou doente?"), com custo computacional menor.

3. **A YOLO Tradicional é inadequada** para problemas de domínio específico — demonstra claramente a necessidade de customização via transfer learning.

> **Lição principal:** o transfer learning oferece o melhor equilíbrio entre esforço de customização e qualidade dos resultados, especialmente com datasets pequenos.

**Trabalhos futuros:**
- Expansão do dataset para 500+ imagens por classe
- Testes com YOLOv8 para comparação de arquiteturas
- Implementação com ESP32-CAM para inferência em campo
- Inclusão de mais classes para diagnóstico específico de doenças

### 📓 Notebook — Entrega 2 (PENDENTE)

📔 [Acessar no Google Colab](https://colab.research.google.com/drive/COLOQUE_SEU_LINK_AQUI_ENTREGA2)

> O notebook contém a implementação completa das três abordagens, com código executado, métricas comparativas e análise crítica em Markdown.

---

# 📋 Informações Gerais

## 🎬 Vídeo Demonstrativo (PENDENTE)

📹 [Assistir no YouTube (não listado)](https://youtube.com/COLOQUE_SEU_LINK_AQUI)

> Vídeo de até 5 minutos demonstrando o treinamento, validação, teste e resultados das Entregas 1 e 2.

---

## 🚀 Como Executar

### Requisitos
- Python 3.10+
- Google Colab com GPU habilitada (Runtime > Change runtime type > T4 GPU)

### Passos — Entrega 1
1. Abra o notebook da Entrega 1 no Google Colab
2. Ative a GPU: `Runtime > Change runtime type > T4 GPU`
3. Execute todas as células sequencialmente
4. Os resultados são salvos em `yolov5/runs/`

### Passos — Entrega 2
1. Certifique-se de que a Entrega 1 foi concluída (pesos `best.pt` salvos no Drive)
2. Abra o notebook da Entrega 2 no Google Colab
3. Ative a GPU e execute todas as células sequencialmente
4. A tabela comparativa final é gerada automaticamente

### Principais bibliotecas utilizadas
- `torch` / `torchvision` — framework de deep learning (PyTorch)
- `tensorflow` / `keras` — framework para CNN do zero
- `opencv-python` — processamento de imagens
- `matplotlib` — visualização de gráficos e resultados
- `pandas` — manipulação de dados tabulares (métricas)
- `scikit-learn` — relatório de classificação e matriz de confusão
- **YOLOv5** (Ultralytics) — detecção de objetos adaptável
- **Darknet / YOLOv3** — detecção de objetos tradicional

---

## 📚 Referências

- Ultralytics YOLOv5: https://github.com/ultralytics/yolov5
- Darknet YOLOv3: https://github.com/pjreddie/darknet
- TensorFlow/Keras: https://www.tensorflow.org/
- MakeSense.ai: https://www.makesense.ai/
- Material didático FIAP — Fase 6, Capítulo 3: ESP32 e Visão Computacional
- Material didático FIAP — Fase 6, Capítulo 9: Primeiros Passos com CNN
- Material didático FIAP — Fase 6, Capítulo 10: Técnicas de Detecção e Segmentação
- Redmon, J. et al. "You Only Look Once: Unified, Real-Time Object Detection" (2016)
- Simonyan, K. & Zisserman, A. "Very Deep Convolutional Networks" (VGG16, 2014)
