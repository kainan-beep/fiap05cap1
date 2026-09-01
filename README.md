# 🌾 FarmTech Solutions — Cap 01, Fase 5: Machine Learning na Cabeça

PBL de Inteligência Artificial — FIAP

## Sobre o Projeto

A FarmTech Solutions é uma startup acadêmica fictícia da disciplina de IA na FIAP.
Esta é a quinta fase de um projeto contínuo:

| Fase | Entrega | Repositório |
|---|---|---|
| 2 | Sistema IoT com ESP32 — sensores de umidade, pH (LDR), P/K e bomba por relé | [fiap04cap1](https://github.com/kainan-beep/fiap04cap1) |
| 3 | Banco relacional Oracle + dashboard Streamlit de monitoramento | [fiap04cap1](https://github.com/kainan-beep/fiap04cap1) |
| 4 | Machine Learning (Scikit-Learn) sobre os dados dos sensores, integrado ao dashboard | [fiap04cap1](https://github.com/kainan-beep/fiap04cap1) |
| **5** | **Previsão de rendimento de safra + tendências por clusterização + estimativa de custos AWS** | **este repositório** |

Na Fase 5, a FarmTech presta serviço de IA a uma fazenda de médio porte (200 hectares)
que produz várias culturas. A partir de dados de solo e clima, o objetivo é **prever o
rendimento da safra** (aprendizado supervisionado) e **explorar tendências de
produtividade** (aprendizado não supervisionado).

---

## Entrega 1 — Machine Learning

Todo o desenvolvimento, a análise e as conclusões estão no notebook:

📓 _(link a preencher quando o notebook estiver no repositório)_

O notebook cobre, em ordem:

1. Análise exploratória da base `crop_yield.csv`
2. Clusterização para identificar tendências de rendimento e cenários discrepantes (outliers)
3. Cinco modelos preditivos de regressão, cada um com algoritmo diferente, com avaliação comparativa

### Base de dados

`dados/crop_yield.csv` — uma linha por observação:

| Variável | Descrição |
|---|---|
| Cultura | Nome da safra cujo rendimento está sendo medido |
| Precipitação (mm dia⁻¹) | Quantidade de chuva em milímetros por dia |
| Umidade específica a 2 m (g/kg) | Vapor de água por quilograma de ar seco, a 2 m do solo |
| Umidade relativa a 2 m (%) | Vapor de água como % do máximo suportado naquela temperatura/pressão |
| Temperatura a 2 m (°C) | Temperatura a 2 m acima do solo |
| Rendimento (ton/ha) | **Variável alvo** — rendimento em toneladas por hectare |

### Como executar

```bash
pip install -r requirements.txt
jupyter notebook
```

🎥 **Vídeo — Entrega 1:** _(link a preencher)_

---

## Entrega 2 — Estimativa de Custos na AWS

_(seção a preencher: comparação São Paulo × Norte da Virgínia, prints da calculadora
em `assets/aws/`, e a justificativa de escolha considerando latência e LGPD)_

🎥 **Vídeo — Entrega 2:** _(link a preencher)_

---

## Estrutura do Repositório

```
fiap05cap1/
├── README.md
├── requirements.txt
├── dados/
│   └── crop_yield.csv          Base fornecida pela FIAP
└── assets/
    └── aws/                    Prints da calculadora AWS (Entrega 2)
```

---

## Integrantes

- Kainan Bilibio Aguiar — RM570594
- Guilherme C. Ávila — RM571294
