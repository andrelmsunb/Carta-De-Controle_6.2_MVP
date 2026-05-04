# Carta de Controle EWMA — Tópico 6.6
## Média Móvel Exponencialmente Ponderada (MMEP)

**Autor:** Andre Luiz Marques Serrano  
**Disciplina:** Controle Estatístico da Qualidade  
**Referência:** Montgomery, D. C. (2016). *Introdução ao Controle Estatístico da Qualidade*. 7ª ed. LTC. Seção 9.2, pp. 440–460.

---

## Descrição

Este projeto implementa o **Gráfico EWMA** (denominado MMEP no livro — Média Móvel Exponencialmente Ponderada), conforme a Seção 9.2 de Montgomery. O EWMA é uma alternativa ao CUSUM para detectar pequenos deslocamentos, com a vantagem de ser mais simples de implementar e mais robusto à não normalidade.

A estatística EWMA é uma média ponderada de todas as observações passadas, com pesos que decrescem geometricamente: zᵢ = λxᵢ + (1−λ)zᵢ₋₁.

---

## Conteúdo do Projeto

| Arquivo | Descrição |
|---------|-----------|
| `notebook_*.ipynb` | Notebook Jupyter com código, gráficos e interpretações |
| `README.md` | Este arquivo — documentação do projeto |

---

## Tópicos Abordados

- Estatística EWMA: equação recursiva e interpretação de λ
- Limites de controle exatos (variáveis) vs estado estacionário
- Análise de sensibilidade do parâmetro λ
- Comparação EWMA vs CUSUM vs Shewhart
- Recomendações de projeto: λ = 0,05–0,25 e L = 2,6–2,8
- Exercício resolvido: Exemplo 9.2 — Viscosidade (Tabela 9.1)

---

## Exercício Resolvido

> **Exemplo 9.2 — Dados de viscosidade (µ₀=10, σ=1, λ=0,10, L=2,7, Tabela 9.1, p. 420)**

O notebook reproduz integralmente o exemplo do livro, com cálculo passo a passo de todos os parâmetros, comparação com os valores tabelados por Montgomery e interpretação estatística detalhada de cada gráfico.

---

## Bibliotecas Utilizadas

| Biblioteca | Finalidade |
|------------|------------|
| `numpy` | Cálculo recursivo da estatística EWMA zᵢ e dos limites variáveis |
| `pandas` | Organização dos resultados em tabela comparável à Tabela 9.10 |
| `matplotlib` | Construção do gráfico EWMA com limites variáveis e estado estacionário |
| `scipy.stats` | Cálculo do CMS de Shewhart para comparação |
| `warnings` | Supressão de avisos não críticos |

**Instalação:**

```bash
pip install numpy pandas matplotlib scipy
```

---

## Gráficos Gerados

Os gráficos são gerados automaticamente ao executar o notebook. Todos utilizam paleta de cores neutras (escala de cinzas) adequada para publicações acadêmicas.

| Arquivo | Descrição |
|---------|-----------|
| `fig01_EWMA.png` | Gráfico EWMA com limites variáveis — Exemplo 9.2 |
| `fig02_EWMA_sensibilidade_lambda.png` | Análise de sensibilidade do parâmetro λ |
| `fig03_comparacao_metodos.png` | Comparação: Shewhart vs CUSUM vs EWMA |

---

## Como Executar

### Google Colab (recomendado)

1. Acesse [colab.research.google.com](https://colab.research.google.com)
2. Clique em **Arquivo → Fazer upload de notebook**
3. Selecione o arquivo `.ipynb` deste projeto
4. Execute todas as células com **Runtime → Run all**

### Localmente (Jupyter)

```bash
# Instalar dependências
pip install numpy pandas matplotlib scipy jupyter

# Iniciar o Jupyter
jupyter notebook notebook_*.ipynb
```

---

## Referência Bibliográfica

Montgomery, D. C. (2016). *Introdução ao Controle Estatístico da Qualidade*. 7ª ed. Rio de Janeiro: LTC.

---

*Andre Luiz Marques Serrano*
