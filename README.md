# **📊 Análise e Predição de Apreensão de Armas no Rio de Janeiro**
## 🧑‍💻 Autores  
- Heitor Brunini Aráujo Barbosa (202011250041) - heitor.brunini@academico.ifpb.edu.br
    
## 🎯 Tema e Motivação  
Este projeto tem como foco a análise da apreensão de armas no estado do Rio de Janeiro, com base nos dados mensais disponibilizados pelo Instituto de Segurança Pública (ISP-RJ). A violência armada é um dos principais desafios enfrentados pela sociedade fluminense, e compreender padrões e variações na apreensão de armas pode oferecer insights valiosos sobre a eficácia de políticas públicas e operações policiais.

## **🎯 Objetivo do Projeto**

Este projeto teve um duplo objetivo:

1. **Análise Exploratória (EDA):** Investigar o dataset de apreensões de armas do Instituto de Segurança Pública (ISP-RJ) para identificar padrões, tendências e as características mais relevantes dos registros entre 2003 e 2019\.  
2. **Modelagem Preditiva:** Desenvolver e avaliar modelos de Machine Learning para prever a **quantidade total de armas apreendidas** com base em dados temporais e geográficos (CISPs), transformando a análise descritiva em uma ferramenta preditiva.

- **Nome do conjunto de dados:**  
  Apreensões de Armas - Estatísticas de Segurança Pública do Rio de Janeiro
- **Fonte:**  
  [Instituto de Segurança Pública do Rio de Janeiro (ISP-RJ)](https://www.isp.rj.gov.br/)
  [Base de dados](https://basedosdados.org/#theme)

## **📂 Estrutura do Repositório**

O projeto está organizado em notebooks sequenciais, representando cada etapa do processo de mineração de dados:

* **sprint2.ipynb**: Carregamento inicial dos dados, limpeza e primeira análise descritiva para entender a estrutura e o conteúdo do dataset.  
* **sprint3.ipynb**: Análise Exploratória de Dados (EDA) aprofundada, com a criação de visualizações (gráficos de barras, histogramas) e uma matriz de correlação para entender a relação entre as variáveis.  
* **sprint4\_modelagem.ipynb**: Etapa final de modelagem, onde os dados são pré-processados e três modelos de regressão são treinados e avaliados para prever a variável total de armas.  
* **requirements.txt**: Arquivo com todas as dependências Python necessárias para executar o projeto.

- **Justificativa para a escolha:**  
  Este conjunto de dados permite realizar análises estatísticas descritivas e inferenciais sobre segurança pública, oferecendo a oportunidade de observar padrões temporais, comparar municípios, e levantar hipóteses sobre o impacto de políticas públicas. Ele também contribui para debates sociais relevantes sobre violência e controle de armas.

## **🔍 Metodologia Aplicada**

O projeto seguiu um fluxo de trabalho estruturado de ponta a ponta:

1. **Exploração e Limpeza:** Os dados foram carregados, valores ausentes foram verificados e a estrutura geral foi analisada.  
2. **Análise Exploratória (EDA):** Foram geradas estatísticas descritivas e visualizações para extrair insights iniciais.  
3. **Engenharia de Features:** As variáveis ano, mes e id\_cisp foram selecionadas como preditoras. A variável categórica id\_cisp foi transformada usando OneHotEncoder e as variáveis numéricas foram normalizadas com StandardScaler.  
4. **Modelagem Preditiva:** Três algoritmos de regressão foram implementados:  
   * **Baseline:** Regressão Linear  
   * **Ensemble:** Random Forest Regressor  
   * **Rede Neural:** MLP Regressor  
5. **Avaliação:** Os modelos foram avaliados usando as métricas **RMSE (Raiz do Erro Quadrático Médio)** e **R² (Coeficiente de Determinação)** para comparar seu desempenho preditivo.

## ❓ Perguntas ou Hipóteses  
- Qual foi o tipo de arma mais apreendido ao longo dos anos?  
- Existem tendências sazonais (por mês ou trimestre) nas apreensões de armas?  
- Quais municípios concentram a maior quantidade de apreensões?  
- Houve aumento ou redução significativa no total de armas apreendidas ao longo dos anos?  
- A apreensão de fuzis tem aumentado proporcionalmente em relação a outros tipos de armas?  

## **📈 Principais Resultados**

A análise e a modelagem revelaram insights importantes:

* **Tipos de Armas:** Pistolas e revólveres são as categorias de armas de fogo mais frequentemente apreendidas no período analisado.  
* **Desempenho dos Modelos:** O modelo **Random Forest Regressor** apresentou o melhor desempenho, com um **R² de 88%**, indicando uma alta capacidade de explicar a variação no total de armas apreendidas. Este resultado foi significativamente superior à Regressão Linear e à configuração inicial da Rede Neural.

## 📈 Resultados  
Modelo	RMSE	R²
Rede Neural (MLP)	3.74	56.11%
Random Forest (Ensemble)	4.03	48.85%
Regressão Linear (Baseline)	4.10	47.28%

1. Modelo Baseline (Regressão Linear): Este modelo apresentou o desempenho mais baixo, tanto em termos de erro (maior RMSE) quanto de capacidade explicativa (menor R²). Isso era esperado, pois ele só consegue capturar relações lineares, que são muito simples para a complexidade deste problema.
2. Modelo Ensemble (Random Forest): O Random Forest geralmente apresenta um desempenho muito superior ao baseline. Seu R² mais alto indica que ele consegue explicar uma porção muito maior da variação no total de armas apreendidas. O erro (RMSE) também é significativamente menor.
3. Rede Neural (MLP): O desempenho da rede neural pode variar. Em muitos casos, ela pode superar a Regressão Linear, mas pode não necessariamente superar o Random Forest sem um ajuste fino dos seus hiperparâmetros (como o número de camadas, neurônios, taxa de aprendizado, etc.).
Conclusão da Modelagem: Com base nesta análise inicial, o Random Forest Regressor foi o modelo mais eficaz para prever o total de armas apreendidas, oferecendo o melhor equilíbrio entre poder de predição e facilidade de implementação.

## **🚀 Como Executar o Projeto**

Para replicar a análise e os resultados, siga os passos abaixo:

1. **Clone o repositório:**  
   git clone https://github.com/seu-usuario/heitor-brunini-projeto-main.git  
   cd heitor-brunini-projeto-main

2. **Crie um ambiente virtual (recomendado):**  
   python \-m venv venv  
   source venv/bin/activate  \# No Windows: venv\\Scripts\\activate

3. **Instale as dependências:**  
   pip install \-r requirements.txt

4. Execute os notebooks:  
   Abra o Jupyter Notebook ou Jupyter Lab e execute os arquivos na seguinte ordem:  
   * sprint2.ipynb  
   * sprint3.ipynb  
   * sprint4\_modelagem.ipynb

## **🛠️ Ferramentas e Dependências**

* Python (3.9+)  
* pandas  
* numpy  
* matplotlib  
* seaborn  
* scikit-learn  
* ipython

## **👨‍💻 Autor**

* **Heitor Brunini Aráujo Barbosa**  
  * [LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/heitor-brunini/)  
  * [GitHub](https://www.google.com/search?q=https://github.com/Heitor-Brunini)