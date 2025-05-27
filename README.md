# 📊 Análise de Movimentações e Custos com Simulação de Erros

Este projeto tem como objetivo analisar dados de movimentações de materiais (entradas e saídas) em um sistema de estoque, com foco na **detecção de anomalias**, **cálculo de custos reais e simulados** e **avaliação do impacto de erros operacionais**.

---

## 📁 Estrutura do Projeto

O projeto está estruturado em etapas executadas no Google Colab e divididas conforme abaixo:

### 1. **Carregamento dos Dados**
- Importação do dataset simulado contendo:
  - Tipo de movimento (entrada/saída)
  - Quantidade movimentada
  - Data
  - Unidade
  - Custo unitário
  - Material

---

### 2. **Tratamento Inicial**
- Conversão de colunas de data
- Cálculo do custo real (`Quantidade × Custo Unitário`)
- Filtro das movimentações de **saída**

---

### 3. **Estatísticas por Material**
- Cálculo da **média e desvio padrão** de quantidade por material
- Total de saída por unidade
- Identificação de **materiais com consumo irregular**

---

### 4. **Custo Mensal**
- Agrupamento dos dados por mês
- Cálculo da evolução mensal do custo real

📈 *Foi gerado um gráfico de linha para representar a variação mensal do custo total de saída.*

---

### 5. **Simulação de Erros e Impacto Acumulado**
- Simulação de erros nas quantidades movimentadas com acréscimos de 10% a 50%
- Cálculo do impacto mensal e acumulado no custo total
- Visualização gráfica do impacto acumulado por nível de erro

⚠️ *Essa etapa demonstra como pequenas variações podem gerar grandes prejuízos financeiros com o tempo.*

---

### 6. **Identificação de Outliers**
- Aplicação de **Z-score** e **IQR** para identificar movimentações fora do padrão
- Sinalização de possíveis erros operacionais, como lançamentos duplicados ou quantidades anormais

---

## 📌 Principais Conclusões

- Foram identificados **desvios relevantes** em materiais com alto consumo.
- A simulação mostrou que **erros operacionais recorrentes** (ex: +20% nas quantidades) podem causar **impactos acumulados significativos** nos custos.
- A identificação de outliers ajuda na criação de mecanismos de controle e auditoria mais eficientes.
- A análise reforça a importância de ferramentas automatizadas para validação e gestão de estoque.

---

## 🛠️ Tecnologias Utilizadas

- Python
- Pandas
- Seaborn / Matplotlib
- Google Colab

---

## 📷 Visualizações

Gráficos gerados:
- 📈 Evolução do custo mensal
- 📉 Impacto acumulado de erros (10% a 50%)
- 📊 Outliers detectados (Z-score e IQR)

---

## 📌 Sugestões Finais

É recomendada a implementação de:
- Validações automáticas de lançamentos
- Limites por faixa de consumo por material
- Auditorias mensais com base em relatórios estatísticos
