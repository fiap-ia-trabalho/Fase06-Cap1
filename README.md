# FIAP - Faculdade de Informática e Administração Paulista

<img width="2385" height="642" alt="image" src="https://github.com/user-attachments/assets/594c28cc-66ae-40ac-b8a6-8c39e6f14de4" />

# FarmTech na Era da Cloud Computing

## 👨‍🎓 Integrantes: 
- [CAUAN OTTO RODRIGUES SOUSA (RM567940)](https://www.linkedin.com/in/cauanotto)
- [FERNANDO A GURGEL (RM567606)](https://www.linkedin.com/in/fernando-gurgel-75aa8369)
- [IRACI MONTEIRO SOUZA (RM567544)](https://www.linkedin.com/in/iraci-souza-bab42034)
- [MARIA LUISA RODRIGUES NASCIMENTO (RM567659)](https://www.linkedin.com/in/malu-rodrigues-bb756b271)
- [RAFAELA TORRES MARTINS (RM567735)](https://www.linkedin.com/in/rafaela-torres222)


## 👩‍🏫 Professores:
- **Tutor(a):** [ANA CRISTINA DOS SANTOS](https://www.linkedin.com/company/inova-fusca)
- **Coordenador(a):** [ANDRÉ GODOI](https://www.linkedin.com/in/andregodoichiovato)

## Objetivo

Este projeto foi desenvolvido para a Fase 6 da FIAP e tem como objetivo utilizar conheicmentos de **Visão computacional** utilizando **YOLO** para classificação de imagens.

---

## 📜 Descrição

Atualmente, um dos principais desafios do agronegócio é a detecção precoce de doenças nas plantações, fator crítico para a preservação da produtividade e redução de perdas.

Em muitos casos, o produtor identifica o problema apenas em estágios avançados, quando os danos à lavoura já são significativos e, por vezes, irreversíveis.

Diante desse cenário, esta proposta tem como objetivo o desenvolvimento de um sistema baseado em visão computacional, capaz de analisar imagens de plantas saudáveis e doentes, permitindo a identificação automática e antecipada de doenças.

🌾 **Principais problemas abordados:**
- Alta velocidade de propagação das doenças nas plantações
- Processo manual de identificação lento e sujeito a falhas
- Elevados custos operacionais e perdas produtivas

⚙️**Funcionamento da solução:**
- Armazenamento de imagens em nuvem, organizadas por labels
- Utilização do modelo YOLOv5 para treinamento e detecção
- Sistema capaz de identificar automaticamente o estado da planta (saudável ou doente) a partir de imagens

---

## Dataset utilizado

Base de imagens: https://drive.google.com/drive/u/1/folders/1JokeVmMrXhfRU3kh9TMkYff-34FXyE9f

A base é composta por um conjunto de imagens previamente rotuladas, distribuídas da seguinte forma:
- 94 imagens para treinamento
- 5 imagens para validação

---

## Principais etapas do notebook

O notebook contempla as seguintes etapas:

1. Instalação e importação das bibliotecas necessárias, incluindo o framework YOLOv5
2. Conexão com a base de dados de imagens (pré-processadas e rotuladas via MakeSense)
3. Treinamento do modelo utilizando técnicas de detecção de objetos
4. Avaliação de desempenho por meio de métricas e análise dos resultados obtidos

---

## Principais resultados

- aaaa

---

## Notebook do projeto

https://colab.research.google.com/drive/1QVhHMyEutsBLL3OkncKU3xGGeoArFx6_?usp=sharing

> Importante: para correção, o notebook deve estar com todas as células executadas.

---

## Vídeos demonstrativos

xxxx

---

## Como executar o projeto

### Requisitos
- Python 3.10+
- Jupyter Notebook ou Google Colab

### Bibliotecas utilizadas
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
