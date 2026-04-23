# FIAP - Faculdade de Informática e Administração Paulista

<img width="2385" height="642" alt="image" src="https://github.com/user-attachments/assets/594c28cc-66ae-40ac-b8a6-8c39e6f14de4" />

# O Despertar da Rede Neural — Fase 6

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
A **FarmTech Solutions** busca automatizar a detecção precoce de doenças em plantações. Este projeto é uma Prova de Conceito (PoC) que avalia diferentes arquiteturas de visão computacional para substituir a inspeção manual lenta e custosa.

---

## 📊 Dataset Final
A base de dados foi organizada e validada com imagens reais, separadas para garantir que o modelo seja testado com dados nunca vistos.

| Classe | Treino | Teste (Inéditas) | Total | 
|--------|--------|-----------|-------|
| Planta Saudável | 74 | 4 | 78 |
| Planta Doente | 48 | 4 | 52 | 
| **Total** | **122** | **8** | **130** |

---

# 📦 ENTREGA 1 — YOLO Adaptável (Transfer Learning)

## 📈 Resultados — Entrega 1
Comparação de desempenho após o *fine-tuning* do modelo YOLOv5s:

| Métrica | 30 Épocas | 60 Épocas |
|---------|----------|----------|
| Precision | 0.2195 | 0.2338 |
| Recall | 0.5000 | 0.4943 |
| **mAP@0.5** | **0.2659** | **0.2873** |
| mAP@0.5:0.95 | 0.1301 | 0.1370 |

---

# 📦 ENTREGA 2 — Comparação de Abordagens

## 🔬 Objetivo
Confrontar a **YOLO Adaptável** com modelos genéricos e redes neurais construídas do zero para determinar a melhor solução para a FarmTech Solutions.

## 📊 Tabela Comparativa Final (Resultados Reais)

| Critério | YOLO Adaptável (E1) | YOLO Tradicional (COCO) | CNN do Zero |
|----------|-------------------|-----------------|-------------|
| **Tipo de tarefa** | Detecção (Localiza + Classifica) | Detecção Genérica | Classificação de Imagem |
| **Treinamento** | Sim (*fine-tuning*) | Não (*zero-shot*) | Sim (do zero) |
| **Tempo de Treino** | ~8 min (30ep) / 12 min (60ep) | 0 min | 11.19 segundos |
| **Inferência/Foto** | ~30ms | ~2674ms (2.67s) | ~52.8ms |
| **Precisão/Acurácia**| mAP@0.5 = 0.2873 | N/A (classes erradas) | Acurácia = 50.00% |
| **Detecta Doenças?** | ✅ Sim | ❌ Não (viu vaso/mesa) | ✅ Sim (só classifica) |

---

## 🔍 Análise Crítica

### 1. Facilidade de Uso e Integração
- **YOLO Tradicional:** Embora seja a mais simples (*plug-and-play*), provou-se **inútil** para o problema. Ao analisar a planta, o modelo detectou **"diningtable" (56%)** e **"bowl" (95%)**, falhando em reconhecer a folhagem agrícola.
- **YOLO Adaptável:** Exige rotulação prévia, mas entrega o resultado esperado pelo cliente com localização precisa.
- **CNN do Zero:** Requer esforço manual de arquitetura e organização de pastas. Resolve apenas a classificação, sem indicar onde a doença está na folha.

### 2. Precisão e Generalização
- **YOLO Adaptável:** Apresentou o melhor equilíbrio, sendo capaz de distinguir as classes agrícolas com mAP superior.
- **CNN do Zero:** Obteve **50.0% de acurácia**, porém demonstrou um forte **viés (bias)**. A Matriz de Confusão revelou que o modelo classificou todas as imagens como "Saudáveis", falhando em detectar 100% dos casos de doença no teste.

### 3. Eficiência Computacional
- A **CNN** é a mais rápida de treinar (11.19s) e leve na predição (~52.8ms).
- A **YOLO Adaptável** é a mais eficiente para uso em tempo real (inferência de ~30ms), sendo a escolha ideal para monitoramento via câmeras ou drones.

---

## 🧪 Conclusão Geral
Para a FarmTech Solutions, a **YOLO Adaptável é a única solução viável**. Ela une a capacidade de localização precisa da patologia com um tempo de resposta adequado para o campo. A CNN do zero é uma alternativa acadêmica interessante, mas sua sensibilidade ao desbalanceamento de dados e incapacidade de localização a tornam menos confiável para diagnósticos críticos em campo.

---

## 🚀 Como Executar

### Passos
1. Certifique-se de que a GPU T4 está ativa no Colab.
2. Monte o Google Drive para acessar a pasta `/MyDrive/FIAP/`.
3. Para a **Entrega 2**, os pesos `best.pt` da Entrega 1 devem estar na pasta raiz do projeto.

### 📓 Notebooks
- 📔 [Entrega 1 — YOLO Adaptável](https://colab.research.google.com/drive/1oGBpVkBhn6dQvNuHnu6EJLyhXG9fafff?usp=sharing)
- 📔 [Entrega 2 — Comparação de Abordagens](https://colab.research.google.com/drive/1VbfTGjOEqX12XvEHvUrjENbUaVGTJY5E?usp=sharing)

---

## 🎬 Vídeo Demonstrativo
📹 [Assistir no YouTube](https://youtube.com/COLOQUE_SEU_LINK_AQUI)
