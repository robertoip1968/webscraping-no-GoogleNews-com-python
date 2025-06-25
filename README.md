# webscraping-no-GoogleNews-com-python
Webscraping no Google News com  Python

  ## Instala a biblioteca da Google News
    !pip install GoogleNews

  ## Importa as bibliotecas da Google News e Pandas
    from GoogleNews import GoogleNews
    import pandas as pd

  ## Configurações iniciais para buscar notícias em português
    googlenews = GoogleNews(lang='pt', region='BR')
    googlenews.search("resultado eleições 2024 prefeito Cuiabá")

  ## Busca as última notícias e transforma em DataFrame para visualização
    results = googlenews.results()
    df = pd.DataFrame(results)

  ## Exibe o resultado
    df[['title', 'media', 'date', 'desc', 'link']]

  ## Gera o arquivo do Excel
    df.to_excel('/content/eleicoes_cuiaba_2024.xlsx', index=False)
    print("Arquivo Excel gerado com sucesso!")

  ## Baixa o arquivo gerado
    from google.colab import files
    df_to_save = df[['title', 'media', 'date', 'desc', 'link']]
    df_to_save.to_csv('noticias_eleicoes_cuiaba.csv', index=False) 
    files.download('noticias_eleicoes_cuiaba.csv')
