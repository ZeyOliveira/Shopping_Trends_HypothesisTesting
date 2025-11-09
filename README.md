# 📊 Análise de Comportamento de Clientes: Aplicação de Testes de Hipóteses

## Visão Geral do Projeto

Este repositório apresenta um projeto de **Análise de Comportamento de Clientes** focado na aplicação prática de **Testes de Hipóteses Estatísticos**. O objetivo principal foi investigar padrões, relações e diferenças significativas em dados de clientes para responder a perguntas de negócio específicas, utilizando um dataset sintético de e-commerce.

Este projeto demonstra proficiência na formulação de hipóteses, seleção de testes estatísticos apropriados, execução em Python e, crucialmente, na interpretação dos resultados no contexto de negócios.

## Propósito e Objetivos

O principal propósito deste projeto é **transformar dados brutos em insights acionáveis**, utilizando a estatística inferencial. Os objetivos específicos incluem:

1.  **Formular Hipóteses:** Desenvolver perguntas de negócio claras e convertê-las em hipóteses nulas e alternativas estatisticamente testáveis.
2.  **Aplicar Testes Estatísticos:** Implementar diversos testes de hipóteses (paramétricos e não paramétricos) para diferentes tipos de variáveis e cenários.
3.  **Interpretar Resultados:** Analisar p-valores e estatísticas de teste para aceitar ou rejeitar hipóteses nulas, traduzindo esses achados em conclusões de negócio.
4.  **Desenvolver Pensamento Crítico:** Entender as limitações dos dados (sintéticos) e discutir implicações para análises futuras com dados reais.
5.  **Comunicar Resultados:** Apresentar as descobertas de forma clara e concisa, como num relatório ou apresentação.

## Dataset

O projeto utiliza um **dataset sintético** de e-commerce, contendo informações diversas sobre clientes e suas transações, como:
### Glossário do conjunto de dados (por coluna)
- **Customer ID** - Identificador único para cada cliente
- **Age** - Idade do cliente
- **Gender** - Sexo do cliente (Masculino/Feminino)
- **Item Purchased** - O item adquirido pelo cliente
- **Category** - Categoria do item adquirido
- **Purchase Amount (USD)** - O valor da compra em USD
- **Location** - Local onde a compra foi feita
- **Size** - Tamanho do item adquirido
- **Color** - Cor do item adquirido
- **Season** - Época em que a compra foi feita
- **Review Rating** - Avaliação dada pelo cliente ao item adquirido
- **Subscription Status** - Indica se o cliente tem uma assinatura (Sim/Não)
- **Shipping Type** - Tipo de envio escolhido pelo cliente
- **Discount Applied** - Indica se foi aplicado um desconto à compra (Sim/Não)
- **Promo Code Used** - Indica se um código promocional foi usado para a compra (Sim/Não)
- **Previous Purchases** - O total de transações concluídas pelo cliente na loja, excluindo a transação em andamento.
- **Payment Method** - Método de pagamento preferido do cliente
- **Frequency of Purchases** - Frequência com que o cliente faz compras (por exemplo, semanalmente, quinzenalmente, mensalmente)

Este dataset, embora sintético, foi fundamental para simular um ambiente de análise de dados e praticar as metodologias estatísticas.

### Distribuição das Variáveis Numéricas:

![hist_of_variable_numeric.png](https://github.com/ZeyOliveira/Shopping_Trends_HypothesisTesting/blob/main/reports/hist_of_variable_numeric.png)


### Distribuição das Variáveis Categóricas:

![boxplot_of_variable_categoric.png](https://github.com/ZeyOliveira/Shopping_Trends_HypothesisTesting/blob/main/reports/boxplot_of_variable_categoric.png)


## Metodologia e Testes de Hipóteses Aplicados

A análise foi conduzida num ambiente Jupyter Notebook (VSCode), utilizando Python e suas bibliotecas de Data Science. Para todos os testes, foi utilizado um **nível de significância ($\alpha$) de 0.05**.

Os seguintes testes de hipóteses foram aplicados para responder a perguntas de negócio específicas:

0. **Normalidade e Homocedasticidade:**
    *  **Testes com variáveis numéricas:** Para todos os testes com variáveis numéricas foram relizados teste de normalidade e homocedasticidade, usando métodos como: Shapiro-Wilk, Kolmogorov-Smirnov (KS), Lilliefors e Levene(variância).

2.  **Teste t de Welch (Comparação de Médias):**
    *   **Cenário:** O impacto das promoções no valor médio de compra (`Purchase Amount (USD)`) entre clientes que usaram vs. não usaram promoções.
    *   **Resultado:** Não foi encontrada evidência estatística significativa de diferença nas médias de valor de compra.

3.  **ANOVA de Dois Fatores (Two-Way ANOVA - Efeitos e Interações):**
    *   **Cenário:** Investigação da interação entre o uso de promoções e o grupo de idade (`Age Group`) no valor médio de compra (`Purchase Amount (USD)`).
    *   **Resultado:** Não foi encontrada evidência estatística significativa de interação entre os fatores ou de efeitos principais isolados.

4.  **ANOVA de Um Fator (One-Way ANOVA - Comparação de Múltiplas Médias):**
    *   **Cenário:** Variação do valor médio de compra (`Purchase Amount (USD)`) entre diferentes categorias de produto (`Category`).
    *   **Resultado:** Não foi encontrada evidência estatística significativa de diferença nos valores médios de compra entre as categorias.

5.  **Teste Qui-Quadrado de Independência (Associação Categórica):**
    *   **Cenário:** Existência de associação significativa entre o gênero do cliente (`Gender`) e as categorias de produto que eles compram (`Category`).
    *   **Resultado:** Não foi encontrada evidência estatística significativa de associação, indicando independência entre gênero e preferência por categoria.

6.  **Teste de Correlação de Spearman (Correlação Monotônica Não Paramétrica):**
    *   **Cenário:** Correlação entre o número de compras anteriores (`Previous Purchases`) e a avaliação do produto (`Review Rating`).
    *   **Resultado:** Não foi encontrada evidência estatística significativa de correlação monotônica.

7.  **Teste H de Kruskal-Wallis (Comparação de Múltiplas Medianas Não Paramétrica):**
    *   **Cenário:** Diferença na mediana do valor de compra (`Purchase Amount (USD)`) entre diferentes categorias de produto (`Category`).
    *   **Resultado:** Não foi encontrada evidência estatística significativa de diferença nas medianas de valor de compra entre as categorias.
  
## Você pode encontrar e ver todas as visualizações geradas aqui:
https://github.com/ZeyOliveira/Shopping_Trends_HypothesisTesting/tree/main/reports

## Insights Chave

Apesar de a maioria dos testes não ter encontrado associações ou diferenças estatisticamente significativas (um achado comum com datasets sintéticos ou quando as relações são realmente inexistentes), o projeto reforça a importância de:

*   **Validação Estatística:** Nem toda observação ou diferença aparente nos dados é estatisticamente significativa e deve ser generalizada.
*   **Compreensão Contextual:** Saber quando aplicar testes paramétricos vs. não paramétricos e interpretar seus resultados no contexto de negócio.
*   **Robustez Metodológica:** A capacidade de formular uma pergunta, escolher a ferramenta certa e justificar a conclusão, independentemente do resultado "esperado".

## Tecnologias e Bibliotecas Utilizadas

*   **Python 3.x**
*   **Pandas:** Para manipulação e análise de dados.
*   **NumPy:** Para operações numéricas.
*   **SciPy:** Para funções estatísticas avançadas (t-tests, Kruskal-Wallis, Spearman, Chi-squared).
*   **Statsmodels:** Para modelos estatísticos e ANOVA.
*   **Matplotlib:** Para visualizações estáticas.
*   **Seaborn:** Para visualizações estatísticas atraentes.
*   **Jupyter Notebook:** Para desenvolvimento e apresentação interativa.

## Como Executar o Projeto

Para replicar esta análise, siga os passos:

1.  **Clone o Repositório:**
    ```bash
    git clone https://github.com/ZeyOliveira/Shopping_Trends_HypothesisTesting.git
    cd Shopping_Trends_HypothesisTesting
    ```

2.  **Crie e Ative um Ambiente Virtual (Recomendado):**
    ```bash
    python -m venv venv
    # No Windows:
    .\venv\Scripts\activate
    # No macOS/Linux:
    source venv/bin/activate
    ```

3.  **Instale as Dependências:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Se estiver usando Google Colab, a maioria dessas bibliotecas já estará pré-instalada.)*

4.  **Abra o Notebook:**
    ```bash
    jupyter notebook 02_hypothesis_testings.ipynb
    ```

## Pontos de Destaque

*   **Fundamentação Estatística:** Demonstra um forte entendimento e aplicação prática de uma gama variada de testes de hipóteses estatísticas, incluindo testes paramétricos (t-test, ANOVA) e não paramétricos (Spearman, Kruskal-Wallis, Qui-Quadrado).
*   **Abordagem Orientada a Problemas:** A capacidade de traduzir perguntas de negócio em hipóteses estatísticas e usar dados para testá-las.
*   **Proficiência em Python:** Uso eficaz de bibliotecas essenciais de Data Science para manipulação, análise e visualização de dados.
*   **Interpretação e Comunicação:** Habilidade em interpretar p-valores, estatísticas de teste e comunicar os resultados de forma clara e contextualizada para um público não-técnico (conforme o relatório final).
*   **Boas Práticas de Projeto:** Estrutura de código organizada em um notebook, facilitando a reprodutibilidade e a revisão.
*   **Aprendizado Contínuo:** Abertura para discutir as limitações do dataset sintético e os próximos passos para aprofundar a análise com dados reais.

## Próximos Passos e Melhorias Futuras

*   **Visualizações Avançadas:** Desenvolver dashboards e visualizações interativas para explorar as relações descobertas (ou a ausência delas) de forma mais dinâmica.
*   **Modelagem Preditiva:** Com base nos insights, explorar a construção de modelos de Machine Learning para prever o comportamento do cliente (e.g., churn, valor de vida útil).
*   **Testes Post-Hoc:** Em casos de ANOVA ou Kruskal-Wallis significativos, aplicar testes post-hoc para identificar quais grupos específicos diferem entre si.

## Autor

**Zeygler Oliveira**
*   Estudante de Ciência de Dados
*   Foco em Ciência de dados, MLOps, LLMOps.
*   Buscando oportunidades na área de TI.
  
Conecte-se comigo! Estou sempre aberto a discussões sobre dados, projetos e oportunidades na área de TI.

*   **LinkedIn:** https://www.linkedin.com/in/zeygleroliveira/
*   **GitHub:** https://github.com/ZeyOliveira
