# Projeto 4 — Limpeza e preparação de dados de churn

Projeto desenvolvido no curso de Ciência de Dados da **EBAC**, com foco no pré-processamento de uma base de clientes de telecomunicações.

**Churn** representa o abandono dos serviços pelos clientes. Neste projeto, os dados são preparados para futuras análises e modelos de previsão.

## 🎯 Objetivo

Identificar e corrigir problemas de qualidade dos dados, documentando as decisões de limpeza e seus impactos.

## 🛠️ Tecnologias utilizadas

- Python
- Pandas
- Jupyter Notebook

## 🔎 Etapas realizadas

1. Carregamento e diagnóstico da base.
2. Verificação e correção dos tipos de dados.
3. Cálculo do percentual de valores ausentes por coluna.
4. Exclusão justificada de colunas e registros.
5. Padronização de valores categóricos.
6. Análise da distribuição das variáveis.
7. Preenchimento de valores ausentes.
8. Validação e exportação da base tratada.

## 📊 Tratamento dos dados

| Coluna | Problema identificado | Tratamento aplicado |
|---|---|---|
| `PhoneService` | 59,28% de valores ausentes | Exclusão da coluna para evitar imputação em grande parte dos registros |
| `Churn` | 5 registros sem informação | Exclusão das linhas, preservando a confiabilidade da variável alvo |
| `Genero` | Valores ausentes e categorias inconsistentes | Padronização de `M`, `F` e `f`; preenchimento pela moda |
| `Pagamento_Mensal` | 13% de valores ausentes na base original | Preenchimento pela mediana de 71,45 |
| `Servico_Internet` | Variação de capitalização | Padronização de `dsl` para `DSL` |

Os percentuais de ausência foram calculados sobre as **2.500 linhas originais**. Após excluir os registros sem churn, foram preenchidos **7 valores de gênero** e **320 valores de pagamento mensal**.

## ✅ Resultado final

| Indicador | Base original | Base tratada |
|---|---:|---:|
| Clientes | 2.500 | 2.495 |
| Colunas | 16 | 15 |
| Valores ausentes | 1.824 | 0 |

A base final apresenta tipos adequados no notebook, categorias padronizadas e nenhum valor ausente.

## 📁 Arquivos

- `Projeto4_Churn_Resolvido.ipynb`: notebook com código, resultados e justificativas.
- `CHURN_TELECON_MOD08_TAREFA.csv`: base original utilizada.
- `Projeto4_Base_Limpa.csv`: base após o tratamento.

## ▶️ Como executar

1. Instale o Pandas e o Jupyter:

```bash
pip install pandas jupyter
```

2. Coloque o notebook e o CSV original na mesma pasta.
3. Abra o notebook no Jupyter.
4. Execute as células em ordem.

Ao final, será gerado o arquivo `Projeto4_Base_Limpa.csv`.

## 📝 Considerações

O preenchimento pela moda e pela mediana não recupera os valores reais dos clientes e pode reduzir a variabilidade dos dados.

Em uma futura etapa de modelagem, os valores usados na imputação devem ser calculados apenas no conjunto de treino, evitando vazamento de dados.

O formato CSV não preserva os tipos definidos no notebook. As conversões devem ser reaplicadas ao carregar o arquivo.

## 👨‍💻 Autor

**Gustavo Abreu**

Projeto acadêmico desenvolvido durante o curso de Ciência de Dados da EBAC.
