# 📊 Projeto de Business Intelligence: Megaloja Global de Varejo

## 📋 Sobre o Projeto
Projeto desenvolvido que implementa uma solução completa de Business Intelligence para uma megaloja global de varejo, utilizando dados reais de transações ao longo de 4 anos.

## 🎯 Objetivos do Projeto
Transformar dados brutos de transações em insights acionáveis através de três frentes estratégicas:

### 1. **Análise de Clientes**
- Identificar os clientes mais valiosos
- Compreender o ticket médio por segmento
- Mapear comportamento de compra

### 2. **Eficiência Operacional**
- Avaliar performance dos processos de envio
- Medir consistência dos prazos logísticos
- Otimizar modalidades de entrega

### 3. **Desempenho de Vendas**
- Identificar padrões regionais de vendas
- Analisar tendências sazonais
- Otimizar alocação de recursos

## 📊 Fontes de Dados
- **Dataset:** SuperStore Sales Dataset (Kaggle)
- **Período:** 4 anos de transações
- **Volume:** 9.800 registros, 18 atributos originais
- **Tratamento:** Exclusão de colunas redundantes e limpeza de dados ausentes

## 🏗️ Arquitetura Técnica

### Modelagem de Dados (Star Schema)
```
┌─────────────────┐
│   fVendas       │
│  (Tabela Fato)  │
├─────────────────┤
│ • Order ID      │
│ • Sales         │
│ • Customer ID   │
│ • Product ID    │
│ • Order Date    │
│ • Ship Date     │
└─────┬───┬───────┘
      │   │
┌─────┘   └───────┐
▼                 ▼
┌─────────────────┐  ┌─────────────────┐
│   dClientes     │  │   dProdutos     │
├─────────────────┤  ├─────────────────┤
│ • Customer ID   │  │ • Product ID    │
│ • Segment       │  │ • Category      │
│ • Region        │  │ • Sub-Category  │
│ • State         │  └─────────────────┘
└─────────────────┘
         │
         ▼
┌─────────────────┐
│   dCalendario   │
├─────────────────┤
│ • Date          │
│ • Year          │
│ • Quarter       │
│ • Month         │
└─────────────────┘
```

### KPIs Implementados
| KPI | Cálculo | Área Responsável |
|-----|---------|------------------|
| Ticket Médio por Cliente | `SUM(Sales) / DISTINCTCOUNT(Customer ID)` | Vendas/Marketing |
| Tempo Médio de Envio | `AVERAGE(Ship Date - Order Date)` | Operações/Logística |
| Desvio Padrão do Tempo de Envio | `STDEV.P(Ship Date - Order Date)` | Operações/Logística |
| Total de Vendas por Região | `SUM(Sales) GROUP BY Region` | Vendas/Estratégia |
| Quantidade de Pedidos | `DISTINCTCOUNT(Order ID)` | Vendas/Operações |

## 📈 Principais Insights Descobertos

### ✅ O que está funcionando:
- **Crescimento consistente**: +393% em pedidos em 4 anos
- **Região West**: Motor principal de vendas (R$117M em 2018)
- **Segmento Consumer**: Base sólida (55% do faturamento)
- **Modalidade First Class**: Crescimento explosivo (+2.257% em 4 anos)

### ⚠️ O que precisa de atenção:
- **Q1**: Queda de vendas e ticket médio
- **Previsibilidade logística**: Desvio padrão aumentou 12.6%
- **Modalidade Second Class**: Alta inconsistência
- **Categoria Furniture**: Performance logística inconsistente

### 🚀 O que escalar:
- **Modelo do Q3**: Trimestre historicamente mais forte
- **Região Central**: Crescimento de +418% no Q3/2017
- **Segmento Corporate**: Ticket médio 15% maior
- **Categoria Technology**: Consistência logística exemplar

## 🎨 Dashboard - Visão Geral

### Página 1: Visão Geral
- **KPIs Principais**: Faturamento, Quantidade de Vendas, Produtos Vendidos
- **Desempenho Temporal**: Análise trimestral comparativa
- **Faturamento por Região**: Mapa de calor geográfico
- **Top Categorias**: Performance por linha de produto

### Página 2: Análise de Clientes
- **Top 5 Clientes**: Por ticket médio (Anna Gayman: R$24,91M)
- **Ticket Médio por Segmento**: Consumer, Corporate, Home Office
- **Faturamento por Segmento e Ano**: Evolução temporal
- **Detalhamento por Estado**: Performance regional

### Página 3: Produtos e Envio
- **Eficiência Operacional**: Tempo médio de envio (4 dias)
- **Consistência**: Desvio padrão do tempo de envio (1,75)
- **Performance por Modalidade**: Standard, First, Second, Same Day
- **Sazonalidade**: Padrões mensais por categoria

## 💡 Recomendações Estratégicas

### Vendas e Marketing:
1. **Focar no Segmento Corporate** - Maior ticket médio e crescimento estável
2. **Expandir na Região Central** - Capitalizar crescimento de +418%
3. **Otimizar sazonalidade do Q3** - Replicar estratégias bem-sucedidas

### Operações e Logística:
4. **Padronizar operações do Q2** - Mitigar queda histórica de performance
5. **Capitalizar crescimento da First Class** - Atender demanda premium
6. **Melhorar previsibilidade** - Reduzir desvio padrão das entregas

## 🛠️ Tecnologias Utilizadas
- **Power BI**: Desenvolvimento do dashboard e visualizações
- **DAX**: Criação de medidas e cálculos avançados
- **Star Schema**: Modelagem dimensional otimizada
- **ETL**: Transformação e limpeza de dados

## 📚 Aprendizados Técnicos
- **Modelagem dimensional** com Star Schema
- **Criação de KPIs** com DAX avançado
- **Storytelling com dados** para diferentes stakeholders
- **Análise de eficiência operacional** com métricas de tempo
- **Identificação de padrões sazonais** e regionais

---

**Desenvolvido por:** Henrique Albuquerque Araújo 
**Contato:** he.fla3@gmail.com  

*Transformando dados em decisões estratégicas.* 📊✨
