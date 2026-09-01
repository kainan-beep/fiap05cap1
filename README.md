# 🌾 FarmTech Solutions — Fase 5: Machine Learning na Cabeça

**PBL de Inteligência Artificial — FIAP | Cap 01, Fase 5**

| Integrante | RM |
|---|---|
| Kainan Bilibio Aguiar | 570594 |
| Guilherme C. Ávila | 571294 |

---

## Sobre o projeto

A FarmTech Solutions é uma startup acadêmica fictícia que presta serviços de
Inteligência Artificial ao agronegócio. Nesta fase, o cliente é uma fazenda de
**200 hectares** — cerca de 210 campos de futebol oficiais — que cultiva quatro
culturas tropicais simultaneamente e coleta dados de solo e clima por sensores em
campo.

A pergunta de negócio é direta: **dadas as condições medidas, qual será o
rendimento da safra?**

Este repositório entrega duas frentes:

| Entrega | O que é | Onde está |
|---|---|---|
| **1 — Machine Learning** | Análise exploratória, clusterização, detecção de outliers e cinco modelos preditivos sobre a base `crop_yield.csv` | [Notebook Jupyter](#-entrega-1--machine-learning) |
| **2 — Computação em Nuvem** | Estimativa de custos na AWS para hospedar a API de sensores e o modelo, comparando São Paulo e Norte da Virgínia | [Seção neste README](#-entrega-2--computação-em-nuvem-aws) |

### Continuidade do projeto

Este é o quinto capítulo de um trabalho contínuo. As fases anteriores estão em
[**kainan-beep/fiap04cap1**](https://github.com/kainan-beep/fiap04cap1):

| Fase | Entrega |
|---|---|
| 2 | Sistema IoT com ESP32 — sensores de umidade do solo, pH via LDR, presença de fósforo e potássio, bomba de irrigação por relé |
| 3 | Banco relacional Oracle e dashboard de monitoramento em Streamlit |
| 4 | Machine Learning sobre os dados dos sensores, integrado ao dashboard |
| **5** | **Este repositório** |

---

## 📓 Entrega 1 — Machine Learning

### ➡️ [**Abrir o notebook: `KainanBilibioAguiar_rm570594_pbl_fase4.ipynb`**](KainanBilibioAguiar_rm570594_pbl_fase4.ipynb)

Todo o desenvolvimento, as análises, os achados e as conclusões estão no
notebook. Ele é o documento principal desta entrega e está organizado em quatro
blocos, com todas as células executadas e os resultados salvos:

| Bloco | Conteúdo |
|---|---|
| **1. Análise exploratória** | Estrutura e qualidade da base, padronização das variáveis, correção da unidade do alvo, distribuições e análise de correlação |
| **2. Clusterização e outliers** | K-Means com escolha de `k` justificada por cotovelo e silhueta, projeção PCA, e detecção de cenários discrepantes por três critérios independentes |
| **3. Modelagem preditiva** | Cinco algoritmos de regressão comparados sob validação cruzada agrupada, com análise de resíduos e importância de variáveis |
| **4. Conclusões** | Respostas às perguntas do projeto, pontos fortes, limitações e recomendações à fazenda |

> **Sobre o nome do arquivo.** O sufixo `pbl_fase4` segue literalmente o padrão
> de nomeação exigido no enunciado da Fase 5.

### A base de dados

`dados/crop_yield.csv` — 156 linhas, 6 colunas, sem valores ausentes.

| Variável | Descrição | Unidade |
|---|---|---|
| `Crop` | Cultura para a qual o rendimento é medido | — |
| `Precipitation` | Quantidade de chuva | mm/dia |
| `Specific Humidity at 2 Meters` | Vapor de água por quilograma de ar seco, a 2 m do solo | g/kg |
| `Relative Humidity at 2 Meters` | Vapor de água como % do máximo suportado | % |
| `Temperature at 2 Meters` | Temperatura a 2 m acima do solo | °C |
| `Yield` | **Variável alvo** — rendimento da safra | hg/ha |

As quatro culturas são cacau em amêndoas, fruto de dendê, arroz em casca e
borracha natural, com 39 observações cada.

> ⚠️ **A unidade do alvo diverge do enunciado.** O enunciado descreve o
> rendimento em toneladas por hectare, mas os valores da coluna vão de 5.249 a
> 203.399 — impossível em t/ha. O notebook documenta a investigação e a correção
> aplicada. Essa checagem mudou a interpretação de todas as métricas de erro do
> trabalho.

### Como executar

```bash
# 1. Criar o ambiente e instalar as dependências
python3 -m venv .venv
source .venv/bin/activate          # no Windows: .venv\Scripts\activate
pip install -r requirements.txt

# 2. Abrir o notebook a partir da raiz do repositório
jupyter notebook KainanBilibioAguiar_rm570594_pbl_fase4.ipynb
```

O notebook lê o CSV por caminho relativo (`dados/crop_yield.csv`), então precisa
ser executado a partir da raiz do repositório. Todas as células já vêm executadas
— basta abrir para ver os resultados.

### 🎥 Vídeo demonstrativo — Entrega 1

_(link a preencher)_

---

## ☁️ Entrega 2 — Computação em Nuvem (AWS)

_(seção a preencher: comparação de custos entre São Paulo e Norte da Virgínia,
prints da calculadora AWS em `assets/aws/`, e a justificativa de escolha
considerando latência de acesso aos sensores e restrições legais de armazenamento
de dados no exterior)_

### 🎥 Vídeo demonstrativo — Entrega 2

_(link a preencher)_

---

## Estrutura do repositório

```
fiap05cap1/
├── README.md                                     Este arquivo
├── requirements.txt                              Dependências Python
├── KainanBilibioAguiar_rm570594_pbl_fase4.ipynb  Notebook da Entrega 1
├── dados/
│   └── crop_yield.csv                            Base fornecida pela FIAP
└── assets/
    ├── aws/                                      Prints da calculadora (Entrega 2)
    └── graficos/                                 Gráficos de apoio
```

## Tecnologias

`Python 3.13` · `pandas` · `NumPy` · `scikit-learn` · `Matplotlib` · `seaborn` · `Jupyter`

## Referências

- FAOSTAT — Food and Agriculture Organization, base de dados de produção agrícola
- Scikit-Learn — documentação oficial
- EMBRAPA — Agricultura Digital
