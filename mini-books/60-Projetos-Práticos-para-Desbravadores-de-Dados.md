# Projetos Práticos para Desbravadores de Dados (Nível Iniciante): Construindo Seu Portfólio! 🛠️📈📊

Olá de novo, Desbravador(a) que gosta de colocar a mão na massa!

Você já explorou muitos territórios e ferramentas neste Guia! Agora é o momento de aplicar seus conhecimentos e construir projetos reais que demonstrem suas habilidades. Projetos são a melhor forma de aprender fazendo e de criar um portfólio que mostre sua jornada e seu potencial para o mundo (ou para a sua próxima Guilda!).

Aqui estão sugestões de projetos práticos de nível iniciante, focando em aplicar o maior número possível das habilidades que vimos nos mini-livros. Siga o passo a passo, e ao final, você terá análises completas e código para adicionar ao seu portfólio no GitHub!

**Objetivo dos Projetos:** Pegar um conjunto de dados, limpá-lo, explorá-lo, visualizá-lo e apresentar os insights de forma clara.

**Ferramentas Principais:** Python 🐍, venv ⛺, Pandas 🐼, Matplotlib/Seaborn 🗺️📈, GitHub 📜🗺️🤝.

**Habilidades Aplicadas:** Dados e Analytics ✨, Algoritmos 📜, Estatística 🔬🔮, EDA 🧭📊, Visualização de Dados 🗺️📈, Comunicação 🗣️, Resolução de Problemas 🚧🔍💡🎯, Pensamento Crítico 👀🤔, Python Básico 🐍, Pandas 🐼, venv ⛺, GitHub 📜🗺️🤝, Bibliotecas 📦🛠️✨.

---

## Projeto 1: Analisando e Visualizando Dados de Vendas Simples

Neste projeto, você atuará como um(a) analista inicial de uma loja. Você tem dados de vendas e quer entender o que aconteceu e quais produtos vendem mais.

**Dados:** Usaremos um arquivo CSV simples de exemplo. Imagine que este arquivo contém dados de vendas da sua loja. Você pode criar um arquivo similar ou usar um dataset público simples do Kaggle (procure por datasets de "sales" ou "e-commerce" para iniciantes).

**Exemplo de Estrutura do Arquivo CSV (vendas.csv):**

    ```csv
    ID_Pedido,Data_Pedido,Produto,Categoria,Quantidade,Valor_Unitario,Valor_Total_Pedido,Cidade_Cliente
    101,2023-01-05,Mapa da Floresta,Mapas,2,15.00,30.00,Sao Paulo
    102,2023-01-05,Bussola Magica,Ferramentas,1,50.00,50.00,Rio de Janeiro
    103,2023-01-06,Mapa da Caverna,Mapas,3,12.00,36.00,Sao Paulo
    104,2023-01-06,Lanterna Encantada,Ferramentas,1,35.00,35.00,Minas Gerais
    105,2023-01-07,Mapa da Floresta,Mapas,1,15.00,15.00,Rio de Janeiro
    106,2023-01-07,Kit de Primeiros Socorros,Suprimentos,2,20.00,40.00,Sao Paulo
    107,2023-01-08,Bussola Magica,Ferramentas,1,50.00,50.00,Sao Paulo
    108,2023-01-08,Mapa da Montanha,Mapas,1,18.00,18.00,Minas Gerais
    109,2023-01-09,Lanterna Encantada,Ferramentas,2,35.00,70.00,Rio de Janeiro
    110,2023-01-09,Kit de Primeiros Socorros,Suprimentos,1,20.00,20.00,Sao Paulo


(Salve isso como `vendas.csv` na pasta do seu projeto)

## Passo a Passo:

1.  ### Preparar o Ambiente de Trabalho (Python e venv) 🐍⛺📦

    * Crie uma pasta para o seu projeto (ex: `analise_vendas_loja`).
    * Abra o terminal nesta pasta.
    * Crie um ambiente virtual: `python -m venv .venv` (usamos `.venv` para ser oculto).
    * Ative o ambiente:
        * No macOS/Linux: `source .venv/bin/activate`
        * No Windows (cmd): `.venv\Scripts\activate.bat`
        * No Windows (PowerShell): `.venv\Scripts\Activate.ps1`
    * Instale as bibliotecas necessárias: `pip install pandas matplotlib seaborn jupyterlab` (`JupyterLab` é ótimo para análise interativa!).
    * Rode `pip freeze > requirements.txt` para criar o arquivo de dependências.

2.  ### Iniciar o Projeto no GitHub (O Diário de Bordo) 📜🗺️🤝

    * Vá para o site do GitHub, faça login e crie um novo repositório (ex: `analise-vendas-loja`). Marque como Público (para portfólio!).
    * No terminal, na pasta do seu projeto:
        * Inicialize um repositório Git local: `git init`
        * Adicione os arquivos (seu CSV e `requirements.txt`): `git add vendas.csv requirements.txt`
        * Faça o primeiro commit: `git commit -m "Adicionado arquivo de dados inicial e dependencias"`
        * Conecte seu repositório local ao GitHub (substitua a URL pela do seu repositório!): `git remote add origin https://github.com/seu-usuario/analise-vendas-loja.git`
        * Envie para o GitHub: `git push -u origin main`

3.  ### Carregar e Inspecionar os Dados (Pandas e EDA Inicial) 🐼📊

    * Abra o `JupyterLab` no terminal (dentro do ambiente `venv` ativado): `jupyter lab`.
    * Crie um novo notebook (ex: `analise_vendas.ipynb`).
    * Importe Pandas e carregue o arquivo CSV:


          import pandas as pd
          
          # Carregar o arquivo CSV
          df_vendas = pd.read_csv('vendas.csv')
          
          # Mostrar as primeiras linhas
          print("Primeiras linhas do DataFrame:")
          print(df_vendas.head())
          
          # Mostrar informações sobre as colunas e tipos de dados
          print("\nInformações do DataFrame:")
          df_vendas.info()
          
          # Mostrar estatísticas descritivas básicas para colunas numéricas
          print("\nEstatísticas Descritivas:")
          print(df_vendas.describe())


*(Use as saídas para entender seus dados - EDA!)*

4.  ### Limpar e Preparar os Dados (Pandas - Transformação Simples) 🧹🐼

    * Verifique se há valores faltando: `print("\nValores faltando por coluna:")` `print(df_vendas.isnull().sum())`. Se houver, decida como tratar (remover linhas? preencher com algo?). Use `df_vendas.dropna()` ou `df_vendas.fillna()`.
    * Verifique tipos de dados (`df_vendas.info()` já mostrou!). A coluna `Data_Pedido` está como 'object' (texto). Converta para tipo data: `df_vendas['Data_Pedido'] = pd.to_datetime(df_vendas['Data_Pedido'])`.
    * Verifique se há linhas duplicadas: `print(f"\nNúmero de linhas duplicadas: {df_vendas.duplicated().sum()}")`. Se houver, remova: `df_vendas = df_vendas.drop_duplicates()`.
    * Calcule o valor total do item (`Quantidade` * `Valor_Unitario`) e adicione como nova coluna (mesmo que já exista, bom para praticar!): `df_vendas['Valor_Total_Item'] = df_vendas['Quantidade'] * df_vendas['Valor_Unitario']`.

5.  ### Análise e Estatística (Pandas e Estatística Básica) 🔬🐼📊

    * Qual o valor total vendido? `print(f"\nValor total vendido: {df_vendas['Valor_Total_Pedido'].sum():.2f}")` (Formatação para 2 casas decimais).
    * Quantos pedidos temos? `print(f"Total de pedidos: {df_vendas['ID_Pedido'].nunique()}")` (`nunique` conta valores únicos).
    * Qual o produto mais vendido (em quantidade)?
  

          vendas_por_produto_qtd = df_vendas.groupby('Produto')['Quantidade'].sum().sort_values(ascending=False)
          print("\nProdutos mais vendidos (Quantidade):")
          print(vendas_por_produto_qtd)



(Use `groupby` e `sum` - revisão de Pandas! 🧺📊)

* Qual o produto que gerou mais valor?


      vendas_por_produto_valor = df_vendas.groupby('Produto')['Valor_Total_Pedido'].sum().sort_values(ascending=False)
      print("\nProdutos que geraram mais valor:")
      print(vendas_por_produto_valor)

* Qual a cidade que mais comprou?

      vendas_por_cidade = df_vendas.groupby('Cidade_Cliente')['Valor_Total_Pedido'].sum().sort_values(ascending=False)
      print("\nValor total de vendas por cidade:")
      print(vendas_por_cidade)


* Qual a média de valor por pedido? `print(f"\nValor médio por pedido: {df_vendas['Valor_Total_Pedido'].mean():.2f}")` (Estatística Básica!).

6.  ### Visualizar os Insights Chave (Matplotlib/Seaborn) 🗺️📈

    * Importe as bibliotecas de visualização.
    * Mostre as vendas por produto (valor) em um gráfico de barras:
  

          import matplotlib.pyplot as plt
          import seaborn as sns
          
          plt.figure(figsize=(10, 6)) # Ajusta o tamanho
          sns.barplot(x=vendas_por_produto_valor.index, y=vendas_por_produto_valor.values, palette='viridis')
          plt.title('Valor Total Vendido por Produto')
          plt.xlabel('Produto')
          plt.ylabel('Valor Total Vendido')
          plt.xticks(rotation=45, ha='right') # Gira rótulos do eixo X
          plt.tight_layout() # Ajusta layout
          plt.show()


  * Mostre as vendas ao longo do tempo (agrupe por data e some):

        vendas_por_data = df_vendas.groupby('Data_Pedido')['Valor_Total_Pedido'].sum().reset_index()
        
        plt.figure(figsize=(12, 6))
        sns.lineplot(data=vendas_por_data, x='Data_Pedido', y='Valor_Total_Pedido', marker='o')
        plt.title('Valor Total Vendido por Data')
        plt.xlabel('Data do Pedido')
        plt.ylabel('Valor Total Vendido')
        plt.xticks(rotation=45, ha='right')
        plt.tight_layout()
        plt.show()

* *(Opcional: Mostre as vendas por categoria, ou a distribuição do valor total do pedido (histograma).)*

## Interpretar e Concluir (EDA, Estatística, Visão Analítica, Pensamento Crítico) 💡🧠

Com base nos números e gráficos, quais são os principais insights?

* Qual produto gerou mais receita? Aquele que vendeu mais em quantidade? (Pode ser diferente!).
* Há alguma tendência nas vendas ao longo do tempo (crescimento, queda, sazonalidade)? (Neste pequeno dataset, talvez apenas mostre a variação diária!).
* Qual cidade é mais importante em termos de receita?
* O que esses insights significam para a loja? (Ligado a **Conhecimento de Negócios** - o que a loja pode fazer com essa informação?).

## Organizar e Documentar (Comunicação e Portfólio) 🗣️📖

* Organize seu notebook Jupyter com títulos, subtítulos e texto explicando cada passo (o que você está fazendo, por que e quais são os resultados/insights). Isso é crucial para a **Comunicação**!
* Adicione um resumo inicial e uma conclusão final explicando o problema, a análise realizada e os insights encontrados (Como em **Storytelling!**).
* Certifique-se de que o código está limpo e com comentários onde necessário.

## Salvar e Enviar para o GitHub (Versionamento e Portfólio) 📜🗺️🤝

* Salve seu notebook Jupyter (`analise_vendas.ipynb`).
* No terminal (na pasta do projeto, com o `venv` desativado):
    * Verifique o status: `git status` (mostrará seu notebook novo).
    * Adicione o notebook: `git add analise_vendas.ipynb`
    * Faça um commit: `git commit -m "Analise inicial de vendas com EDA e visualizacao"`
    * Envie para o GitHub: `git push origin main`
* No GitHub, adicione um arquivo `README.md` ao seu repositório. Use-o para descrever o projeto, o objetivo, as fontes de dados, as habilidades usadas e um link para o notebook Jupyter (ou copie os principais insights e gráficos no `README`). Isso é a "capa" do seu projeto no **portfólio**!

**Resultado:** Você terá um projeto completo no GitHub, mostrando que sabe obter, limpar, analisar, visualizar e comunicar insights de dados usando **Python** e bibliotecas comuns. Isso é um excelente item para o seu **portfólio**!

---

# Projeto 2: Análise Similar, Extraindo Dados de um "Banco de Dados" (Simulado/SQLite)

Este projeto é uma variação do Projeto 1, focando na habilidade de **Extração de Dados** de um banco.
Em vez de um CSV direto, vamos simular a extração de um banco de dados. Para iniciantes, a forma mais fácil de simular isso sem configurar um servidor de banco completo é usar um arquivo **SQLite**. SQLite é um banco de dados que roda a partir de um único arquivo no disco, sem precisar de um servidor separado. Python tem suporte embutido para SQLite (`sqlite3`).

## Passo a Passo (Foco na Extração):

1.  ### Configurar Ambiente e GitHub

    Igual ao Projeto 1. Instale `sqlite3` (geralmente já vem com Python) e talvez `pandas` (se quiser carregar direto para DataFrame).

2.  ### Criar o Arquivo do Banco SQLite (Configuração Única)

    No terminal Python (dentro do seu `venv`):


        import sqlite3
        import pandas as pd # Para carregar dados de exemplo
        
        # Conecta (ou cria) o arquivo do banco SQLite
        conn = sqlite3.connect('loja_dados.db')
        cursor = conn.cursor()
        
        # Cria a tabela (igual ao schema do CSV do Projeto 1)
        cursor.execute('''
            CREATE TABLE vendas (
                ID_Pedido INTEGER PRIMARY KEY,
                Data_Pedido TEXT,
                Produto TEXT,
                Categoria TEXT,
                Quantidade INTEGER,
                Valor_Unitario REAL,
                Valor_Total_Pedido REAL,
                Cidade_Cliente TEXT
            )
        ''')
        
        # Carrega dados do CSV para um DataFrame (usando o CSV de exemplo do Projeto 1)
        df_vendas_csv = pd.read_csv('vendas.csv')
        
        # Carrega os dados do DataFrame para a tabela SQLite
        # (Certifique-se que o CSV não tem cabeçalho duplicado se estiver rodando isso!)
        df_vendas_csv.to_sql('vendas', conn, if_exists='append', index=False)
        
        # Verifica se carregou
        cursor.execute("SELECT COUNT(*) FROM vendas")
        print(f"Número de registros na tabela vendas: {cursor.fetchone()[0]}")
        
        conn.commit() # Salva as mudanças
        conn.close() # Fecha a conexão
        print("Banco SQLite 'loja_dados.db' criado e populado com sucesso!")


Agora você tem um arquivo `loja_dados.db` na pasta do seu projeto. Adicione-o ao `Git`/`GitHub`!

3.  ### Extrair Dados do Banco SQLite (SQL e Python!) 🔑🎣🐍

    Em um novo notebook Jupyter ou script Python:


        import sqlite3
        import pandas as pd
        
        # Conecta ao banco SQLite
        conn = sqlite3.connect('loja_dados.db')
        
        # Escreva sua Query SQL para extrair os dados que precisa
        # Exemplo: Extrair todas as vendas de Mapas
        query_sql = "SELECT * FROM vendas WHERE Categoria = 'Mapas';"
        
        # Ou extrair todos os dados para análise (como no Projeto 1)
        query_sql_total = "SELECT * FROM vendas;"
        
        # Executar a query e carregar os resultados diretamente em um DataFrame Pandas
        df_vendas_do_banco = pd.read_sql_query(query_sql_total, conn)
        
        # Fechar a conexão
        conn.close()
        
        print("Dados extraídos do banco de dados com sucesso!")
        print(df_vendas_do_banco.head())
        print(df_vendas_do_banco.info())


Esta é a etapa de **Extração**! Você usou **SQL** (na query) e uma biblioteca Python (`pandas.read_sql_query`, que usa `sqlite3` por baixo) para puxar dados de uma **Fonte de Dados** (Banco de Dados).

### Continuar a Análise

A partir daqui, você tem um **DataFrame Pandas** (`df_vendas_do_banco`). Continue com os **Passos 4 a 9 do Projeto 1** (Limpar, Analisar, Visualizar, Interpretar, Documentar). As etapas de limpeza e preparação podem ser um pouco diferentes dependendo de como os dados estavam no banco.

### Versionar e Enviar para o GitHub

Igual ao **Passo 9 do Projeto 1**, mas inclua o arquivo `.db` (embora para bancos grandes, o arquivo `.db` não seria versionado, apenas o `código de criação/extração`!) e seu novo notebook/script no `Git`/`GitHub`.

**Resultado:** Você terá um projeto no `GitHub` mostrando que sabe extrair dados de um **banco** usando **SQL** e **Python**, e depois **analisar e visualizar**.

---

## Construindo Seu Portfólio:

* Crie um repositório **GitHub** separado para cada projeto.
* Cada repositório deve ter um arquivo **README.md** claro explicando o projeto, os dados, as perguntas respondidas, os insights encontrados e as habilidades que você usou.
* Inclua o **código** (notebooks Jupyter ou scripts Python).
* Inclua os **arquivos de dados** (CSV, arquivos `.db` pequenos).
* Inclua o arquivo `requirements.txt` para que outros possam replicar seu ambiente.
* Seus **gráficos** podem ser mostrados diretamente no notebook Jupyter ou no README (o GitHub mostra notebooks renderizados!).
* À medida que avança no Guia e aprende mais habilidades (ETL na nuvem, ML), crie projetos mais avançados que usem essas novas habilidades e adicione-os ao seu **portfólio**!

Use estes projetos como ponto de partida. Encontre datasets públicos (`Kaggle`, `dados abertos governamentais`) sobre tópicos que te interessam e aplique suas habilidades! **Boas análises!**
