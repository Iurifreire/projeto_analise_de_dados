# projeto_analise_de_dados
Análise da correlação entre obesidade e renda domiciliar per capita no Brasil (2020–2023) com pipeline ETL, regressão em painel com efeitos fixos e clusterização K-Means. Dados: SISVAN, PNAD Contínua e IPCA. Projeto acadêmico — UNIFACS.

---

🥗 Obesidade e Renda no Brasil (2020–2023)


Análise da correlação entre obesidade e renda domiciliar per capita nas regiões brasileiras, com pipeline ETL completo, modelagem estatística e clusterização.




📌 Sobre o Projeto

Este projeto investiga a relação entre prevalência de obesidade e renda domiciliar per capita no Brasil entre 2020 e 2023, controlando os efeitos da pandemia de COVID-19 e da inflação no período. A análise combina fontes oficiais de saúde e socioeconômicas em um pipeline reproduzível de ponta a ponta.


🗂️ Fontes de Dados

DatasetFonteVariáveis PrincipaisSISVANOpenDataSUS (S3)Prevalência de obesidade por região/anoPNAD ContínuaIBGERenda domiciliar per capita (arquivo de largura fixa)IPCAIBGE/BCBDeflator monetário (base 2023)Censo 2022IBGEControle demográfico regional


⚙️ Pipeline

Extração (S3 / FTP) → Limpeza → Deflação IPCA → Unificação → Análise → Clusterização


ETL — download, parsing de arquivos de largura fixa (PNAD), correção de unidade monetária e deflação pelo IPCA
EDA — visualizações regionais, séries temporais, tratamento de lacunas do período COVID (2020–2021)
Regressão em Painel — modelo com efeitos fixos por região, métricas: R², p-valor, RMSE
Clusterização K-Means — agrupamento de regiões por perfil socioeconômico e nutricional (Silhouette Score)
Assistente Conversacional (opcional) — interface LangChain + GPT para consultas sobre os dados



📊 Principais Resultados


Correlação negativa significativa entre renda per capita e obesidade após controle inflacionário
Heterogeneidade regional marcante: Norte e Nordeste apresentam padrões distintos do Sul/Sudeste
K-Means identificou 3 clusters com perfis socioeconômicos e nutricionais coerentes
Lacunas de 2020–2021 tratadas com interpolação linear documentada



🛠️ Tecnologias

Mostrar Imagem
Mostrar Imagem
Mostrar Imagem
Mostrar Imagem


pandas / numpy — manipulação e análise de dados
scikit-learn — K-Means, métricas de avaliação
statsmodels — regressão em painel com efeitos fixos
matplotlib / seaborn — visualizações
langchain + openai (opcional) — assistente conversacional



📁 Estrutura do Repositório

📦 projeto-obesidade-renda/
 ┣ 📂 data/
 ┃ ┣ 📂 raw/          # Dados brutos originais (SISVAN, PNAD, IPCA)
 ┃ ┗ 📂 processed/    # Dados após ETL e deflação
 ┣ 📂 notebooks/
 ┃ ┣ 01_etl.ipynb
 ┃ ┣ 02_eda.ipynb
 ┃ ┣ 03_regressao.ipynb
 ┃ ┗ 04_clusterizacao.ipynb
 ┣ 📂 src/            # Scripts Python reutilizáveis
 ┣ 📜 requirements.txt
 ┗ 📜 README.md


🚀 Como Executar

bash# 1. Clone o repositório
git clone https://github.com/seu-usuario/obesidade-renda-brasil.git
cd obesidade-renda-brasil

# 2. Crie e ative o ambiente virtual
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
.venv\Scripts\activate     # Windows

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Execute os notebooks em ordem (01 → 04)
jupyter notebook


📚 Referências


SISVAN / OpenDataSUS
PNAD Contínua – IBGE
IPCA – IBGE



👨‍💻 Autor

Desenvolvido como projeto da disciplina de Análise de Dados / Big Data — UNIFACS, 2026.
