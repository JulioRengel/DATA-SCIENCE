# 📊 Aprendizados em Data Science com Python

Este repositório reúne meus estudos iniciais em **manipulação de dados** e **visualização gráfica** usando **Pandas**, **NumPy** e **Matplotlib**.

---

## 📝 Atalhos úteis no Jupyter Notebook
- `A` → Inserir célula antes  
- `B` → Inserir célula depois  
- `DD` → Deletar célula  
- `Ctrl + Enter` → Executar célula  

---

## 📂 Importando diferentes formatos de dados
```python
import pandas as pd

dados_csv = pd.read_csv('Downloads/DATASCIENCE/fifa.csv')
dados_xlsx = pd.read_excel('Downloads/DATASCIENCE/fifa.xlsx')
dados_txt = pd.read_csv('Downloads/DATASCIENCE/fifa.txt', delimiter='\t')
dados_html = pd.read_html('https://felipe-aguiar.gitbook.io/dio-java/gitbook/sintaxe/variaveis')

dados.head()      # primeiras 5 linhas
dados.tail()      # últimas 5 linhas
dados.head(2)     # primeiros 2 registros
dados.columns     # nomes das colunas
dados.index       # índice da tabela

# Filtrar jogadores da Venezuela
dados.loc[dados['Nationality'] == 'Venezuela']

# Ordenar por idade (maior para menor)
dados.sort_values('Age', ascending=False)
dados['Total'] = dados['Acceleration'] + dados['Agility'] + dados['Reactions']
dados[['Name', 'Total']].sort_values('Total', ascending=False)
# Condições múltiplas
filter1 = df.loc[(df['Rooms'] == 3) & (df['Type'] == 'h') & (df['Price'] <= 500000)]

# Ignorar maiúsculas/minúsculas
import re
filter2 = df.loc[df['Address'].str.contains('Turner st|Turner Rd', flags=re.I)]

df.groupby(['SellerG']).mean()   # média por vendedor
df.groupby(['SellerG']).sum().sort_values('Price', ascending=False).head(10)

import numpy as np
import sys

a = [1, 2, 3, 4, 5]
b = np.array([1, 2, 3, 4, 5])

sys.getsizeof(a)  # memória ocupada pela lista
b.nbytes          # memória ocupada pelo array

d1 = np.array([1, 2, 3])
d2 = np.array([[1, 2, 3], [4, 5, 6]])
d3 = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

import matplotlib.pyplot as plt

plt.title('Valores do Combustível em US$')
plt.plot(gas['Year'], gas['Australia'], 'r.-', label='Australia')
plt.plot(gas['Year'], gas['Italy'], 'y.-', label='Italy')
plt.plot(gas['Year'], gas['Canada'], 'b.-', label='Canada')

plt.xticks(gas['Year'][::4])
plt.xlabel('Years')
plt.ylabel('US$')
plt.legend()
plt.show()
