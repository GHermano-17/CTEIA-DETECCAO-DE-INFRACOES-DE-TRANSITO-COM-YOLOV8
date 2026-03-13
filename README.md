# Detecção de Infrações de Trânsito com YOLOv8

Projeto final da disciplina de Processamento de Imagem e Visão Computacional — CTEIA/UFC.

Comparação entre três variantes do YOLOv8 (nano, small e medium) para detecção automática de infrações e participantes do trânsito em imagens, utilizando transfer learning a partir de pesos pré-treinados no COCO.

---

## Dataset

**Traffic Violation Detection Dataset**  
https://www.kaggle.com/datasets/guisahanes/traffic-violation-detection-dataset

| Conjunto | Imagens |
|----------|---------|
| Treino | 5.254 |
| Validação | 1.470 |
| Total | 6.724 |

**23 classes:** person, car, truck, bus, motorcycle, red light, green light, stop sign, no entry, no overtaking, speed limit (20–120), no left turn, no right turn, no stopping, no u-turn.

---

## Resultados

| Modelo | Parâmetros | Épocas | mAP50 | mAP50-95 | Precisão | Recall |
|--------|-----------|--------|-------|----------|----------|--------|
| YOLOv8n | 3.0M | 30 | 0.900 | 0.783 | 0.857 | 0.862 |
| YOLOv8s | 11.1M | 30 | 0.915 | 0.804 | 0.895 | 0.864 |
| YOLOv8m | 25.9M | 20 | 0.903 | 0.785 | 0.875 | 0.854 |

---

## Estrutura do Repositório
```
├── yolov8n/
│   ├── weights/
│   │   └── best.pt
│   └── results.csv
├── yolov8s/
│   ├── weights/
│   │   └── best.pt
│   └── results.csv
└── yolov8m/
    └── results.csv          # best.pt disponível via Google Drive (>25MB)
```

> **Nota:** o peso `yolov8m/weights/best.pt` excede o limite de 25MB do GitHub e está disponível via Google Drive:  
> https://drive.google.com/file/d/1DF8MmjwUwAMGy1PaP4xemDuFe7mPXjgE/view?usp=sharing

---

## Como Reproduzir

O notebook está configurado para rodar no **Google Colab** com GPU T4.

1. Abra o notebook no Colab
2. Ative a GPU: *Ambiente de execução → Alterar tipo de ambiente de execução → T4 GPU*
3. Execute todas as células em ordem

As células de avaliação por classe e inferência visual baixam os pesos automaticamente do GitHub e Google Drive — nenhum upload manual é necessário.

---

## Dependências
```bash
pip install ultralytics kagglehub
```

---

## Autor

**Guilherme Hermano de Paula Ferreira**  
CTEIA — Universidade Federal do Ceará
