# FarmTech Solutions - Detecção de Doenças em Plantas (Fase 6)

[cite_start]Este projeto faz parte da Atividade 1 (Entrega 2) da FIAP e foca na aplicação de Visão Computacional para o agronegócio[cite: 5].

## 👥 Equipe
* [cite_start]Cauan Otto (RM567940) [cite: 6]
* [cite_start]Fernando Gurgel (RM567606) [cite: 6]
* [cite_start]Iraci Monteiro (RM567544) [cite: 6]
* [cite_start]Maria Luisa Nascimento (RM567659) [cite: 6]
* [cite_start]Rafaela Torres (RM567735) [cite: 7]

## 🎯 Objetivo
[cite_start]Comparar três abordagens de Inteligência Artificial para identificar patologias em folhas, avaliando precisão, tempo de execução e adaptabilidade ao domínio agrícola[cite: 11, 15].

## 🛠️ Metodologias Comparadas

1. [cite_start]**YOLO Adaptável (Entrega 1):** Modelo YOLOv5s com *fine-tuning* e *transfer learning* em dataset customizado[cite: 71, 73, 74].
2. [cite_start]**YOLO Tradicional:** Modelo YOLOv3 pré-treinado no dataset COCO (80 classes genéricas), aplicado sem customização[cite: 156, 158].
3. [cite_start]**CNN do Zero:** Rede Neural Convolucional construída manualmente com camadas `Conv2D`, `MaxPooling2D` e `Dense`[cite: 13, 300, 465].

## 📊 Resultados Obtidos

| Critério | YOLO Adaptável | YOLO Tradicional | CNN do Zero |
| :--- | :--- | :--- | :--- |
| **Tempo de Treino** | ~25-50 min | [cite_start]0 min [cite: 766] | [cite_start]12.21s [cite: 603] |
| **Acurácia (Teste)** | Alta (mAP > 0.8) | [cite_start]N/A (Inviável) [cite: 285] | [cite_start]50.00% [cite: 710] |
| **Inferência/Foto** | ~30ms | [cite_start]~3.08s [cite: 239] | [cite_start]~56.9ms [cite: 712] |

### Principais Conclusões
* [cite_start]**Ineficiência Genérica:** A YOLO Tradicional identificou plantas como "mesa" (diningtable) ou "vaso" (bowl), provando que modelos prontos não servem para nichos agrícolas sem ajuste[cite: 255, 285].
* [cite_start]**Limitações da CNN:** A rede treinada do zero redimensionou imagens para $150 \times 150$ pixels[cite: 306]. [cite_start]Apesar de rápida, ela "viciou" na classe majoritária, classificando todas as plantas de teste como saudáveis [cite: 715-722].
* **Veredito:** O *transfer learning* (YOLO Adaptável) é o único método resiliente para detecção e localização precisa de doenças no campo.
