# Exemplo-de-c-digo
Trabalho de extensão estacio

import pandas as pd

arquivo_csv = 'dados_ibge.csv'
dados = pd.read_csv(arquivo_csv)

print("Primeiras linhas do dataframe:")
print(dados.head())

print("\nInformações gerais sobre o dataframe:")
print(dados.info())

print("\nEstatísticas descritivas:")
print(dados.describe())

print("\nColunas disponíveis no dataframe:")
print(dados.columns)

if coluna_exemplo in dados.columns:
    print(f"\nDistribuição da coluna '{coluna_exemplo}':")
    print(dados[coluna_exemplo].describe())

    import matplotlib.pyplot as plt
    dados[coluna_exemplo].hist()
    plt.title(f'Histograma da coluna {coluna_exemplo}')
    plt.xlabel(coluna_exemplo)
    plt.ylabel('Frequência')
    plt.show()
else:
    print(f"\nA coluna '{coluna_exemplo}' não foi encontrada no dataframe.")

print("\nValores ausentes por coluna:")
print(dados.isnull().sum())

if categoria_exemplo in dados.columns and valor_exemplo in dados.columns:
    print(f"\nMédia da coluna '{valor_exemplo}' por '{categoria_exemplo}':")
    media_por_categoria = dados.groupby(categoria_exemplo)[valor_exemplo].mean()
    print(media_por_categoria)
else:
    print(f"\nUma das colunas '{categoria_exemplo}' ou '{valor_exemplo}' não foi encontrada no dataframe.")
