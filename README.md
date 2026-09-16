# Checkpoint-2
# 📘 Checkpoint 02 — Integrais Definidas com `scipy`

Este repositório reúne os notebooks do Checkpoint 02, focado no cálculo de **integrais definidas** usando as funções `quad` e `trapezoid` da biblioteca `scipy.integrate`.

## 📂 Arquivos

| Arquivo | Descrição |
|---|---|
| `Checkpoint_02_Exemplo_Inicial_resolvido.ipynb` | Exemplo introdutório: calcula e compara integrais de $f(x) = e^x + 1$ em diferentes intervalos, demonstrando a **propriedade aditiva** das integrais. |
| `Checkpoint_02_MMC_v2_corrigido.ipynb` | Resolução do checkpoint com duas questões aplicadas (crescimento do salmão Coho e fabricação de peças). |

---

## 1️⃣ Exemplo Inicial — Propriedade Aditiva da Integral

Usa a função $f(x) = e^x + 1$ para mostrar que:

$$\int_0^5 f(x)\,dx - \int_0^2 f(x)\,dx = \int_2^5 f(x)\,dx$$

**O que o notebook faz:**
- Calcula as integrais com `scipy.integrate.quad` (método analítico/numérico de alta precisão).
- Recalcula tudo com `scipy.integrate.trapezoid` (método de aproximação por trapézios, usando 100 mil pontos).
- Compara os dois métodos entre si e confirma que ambos concordam.

**Resultado central:** a diferença entre a integral em `[0,5]` e a integral em `[0,2]` é igual à integral calculada diretamente em `[2,5]` — confirmando a aditividade dos intervalos de integração.

---

## 2️⃣ Checkpoint (MMC) — Duas Questões Aplicadas

### Questão 1 — Taxa média de crescimento do salmão Coho
Baseada no estudo de Fisher (1963), compara a taxa média de crescimento do salmão em duas condições:
- **Sem restrição alimentar:** $y = 7.3(x+3.5)e^{-0.05x}$
- **Com restrição alimentar:** $y = 28$ (constante)

no intervalo $3 \leq x \leq 30$, usando o conceito de **valor médio de uma função**:

$$\overline{y} = \frac{1}{b-a}\int_a^b f(x)\,dx$$

**Resultados:**
| Item | Valor |
|---|---|
| Taxa média sem restrição | 58,79 mg/g/dia |
| Taxa média com restrição | 28,00 mg/g/dia |
| Razão (sem/com) | 2,10 |

### Questão 2 — Quantificação de material para fabricação de peças
Calcula a área e a massa de uma peça cuja geometria é definida por duas funções:
- $f(x) = 5e^{x^2/2}+1$ no intervalo $-2 \le x \le 2$
- $g(x) = |\sin(5x)|$ no intervalo $\frac{-3\pi}{5} \le x \le \frac{3\pi}{5}$

A área da peça é obtida pela diferença entre as integrais das duas curvas, e a partir dela são estimadas massa e custo de produção.

**Resultados:**
| Item | Valor |
|---|---|
| Área da peça | 9,56 cm² |
| Massa de 1 peça | 75,07 g |
| Massa para 500 peças (100% eficiência) | 37,53 kg |
| Massa para 500 peças (90% eficiência) | 41,70 kg |
| Custo total (90% eficiência) | R$ 4.170,48 |

> ⚠️ **Pendência:** confirmar com o professor a fórmula correta de $f(x)$ na Questão 2 antes da entrega. Caso a fórmula literal do enunciado ($5e^{x^2/2}+1$) esteja certa, os resultados devem ser substituídos pelos valores calculados na hipótese alternativa ("texto"), já preparados em paralelo em cada célula.

---

## 🛠️ Tecnologias

- Python 3.11
- [`numpy`](https://numpy.org/)
- [`scipy.integrate`](https://docs.scipy.org/doc/scipy/reference/integrate.html) (`quad`, `trapezoid`)

## ▶️ Como executar

1. Abra os notebooks no Google Colab ou Jupyter.
2. Execute as células em ordem (`Kernel > Run All`).
3. Os resultados numéricos aparecem impressos logo abaixo de cada bloco de cálculo.
