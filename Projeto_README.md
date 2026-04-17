# 📊 Análise de Turnover de Colaboradores (HR Analytics)

A base de dados utilizada neste projeto foi obtida a partir do repositório público Kaggle, especificamente o dataset "IBM HR Analytics Employee Attrition & Performance.

📌 Descrição do Projeto

Este projeto tem como objetivo analisar o turnover de colaboradores, identificando padrões e fatores que influenciam a saída de funcionários. A análise foi conduzida utilizando modelagem dimensional, medidas DAX e visualizações interativas no Power BI, com foco em gerar insights estratégicos para apoio à tomada de decisão.


🎯 Objetivos

* Identificar os principais fatores que influenciam o desligamento de colaboradores
* Analisar o perfil dos funcionários com maior propensão ao turnover
* Criar indicadores estratégicos de RH
* Apoiar decisões relacionadas à retenção de talentos


🧠 Hipóteses de Negócio

As seguintes hipóteses foram levantadas para guiar a análise:

* Colaboradores que moram mais longe têm maior probabilidade de sair
* Funcionários com menor salário apresentam maior turnover
* Baixo tempo de empresa está associado a maior rotatividade
* Excesso de horas extras aumenta o risco de desligamento
* Baixa satisfação no trabalho impacta a retenção
* Falta de crescimento profissional influencia a saída
* Determinados cargos e departamentos concentram maior turnover

📄 Detalhes completos em: [hipoteses_negocio.md](hipoteses_negocio.md)


🏗️ Modelagem de Dados

O projeto foi estruturado utilizando o modelo estrela (Star Schema):

🔹 Tabela Fato

**fato_Colaborador**

* Métricas numéricas (salário, tempo de empresa, experiência, etc.)
* Indicador de desligamento (Attrition)

🔹 Dimensão

**dim_Colaborador**

* Informações descritivas (gênero, estado civil, cargo, departamento, etc.)

🔹 Staging

**stg_RH**

* Base original mantida intacta para referência


📊 Principais Métricas (DAX)

✔ Total de Colaboradores

```DAX
Total Colaboradores = DISTINCTCOUNT('fato_Colaborador'[EmployeeNumber])
```

✔ Turnover (%)

```DAX
Turnover % = 
DIVIDE(
    [Total Desligados],
    [Total Colaboradores]
)
```

✔ Salário Médio

```DAX
Salario Medio = AVERAGE('fato_Colaborador'[MonthlyIncome])
```

✔ Tempo Médio de Empresa

```DAX
Tempo Medio Empresa = AVERAGE('fato_Colaborador'[YearsAtCompany])
```


📈 Dashboard

O dashboard foi desenvolvido no Power BI com foco em análise exploratória e estratégica.

Principais visuais:

* KPI de Turnover
* Turnover por Departamento
* Turnover por Cargo
* Análise de Salário vs Attrition
* Distância média dos colaboradores
* Indicadores de satisfação

📷 *Adicione aqui prints do seu dashboard*

```
/Images/dashboard.png
```

---

🔍 Principais Insights

* Colaboradores com menor salário apresentam maior taxa de desligamento
* Funcionários com pouco tempo de empresa têm maior risco de saída
* Altos níveis de horas extras estão associados a maior turnover
* A distância entre residência e trabalho impacta a retenção
* Falta de crescimento profissional é um fator relevante

---

🛠️ Ferramentas Utilizadas

* Power BI
* DAX (Data Analysis Expressions)
* Power Query
* Modelagem Dimensional

---

🚀 Próximos Passos

* Implementar análise temporal (histórico de dados)
* Criar modelo preditivo de turnover
* Integrar novas fontes de dados
* Aprofundar análise de satisfação

---

📁 Estrutura do Repositório

```
├── README.md
├── hipoteses_negocio.md
├── /Data
├── /PowerBI
├── /Images
```

---

👤 Autor 

Projeto desenvolvido por Adriano Souza com foco em análise de dados aplicada a RH e geração de insights estratégicos.


⭐ Considerações Finais

Este projeto demonstra a aplicação prática de técnicas de análise de dados, modelagem e visualização para resolver problemas reais de negócio, com foco em geração de valor e suporte à tomada de decisão.
