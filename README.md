📊 Projeto de Ciência de Dados com Python — ETL
🔄 Fluxo ETL na Prática (com Python)

Este projeto demonstra o fluxo ETL (Extração, Transformação e Carregamento) utilizando Python, inspirado no lab da Santander Dev Week 2023.

🧩 Exemplo 1 — Alternativa Simples (Lista de Usuários)
🔹 Extração (dados fictícios em Python)

users = [

    {"nome": "Ana", "conta": "12345-6", "cartao": "**** 1234"},
    
    {"nome": "Bruno", "conta": "65432-1", "cartao": "**** 5678"}, 
    
    {"nome": "Carla", "conta": "98765-4", "cartao": "**** 9012"}
]

🔹 Transformação (geração de mensagens personalizadas)
def gerar_mensagem(usuario):
    return f"Olá, {usuario['nome']}! Obrigado por ser cliente Santander 💙"

for user in users:

    user["mensagem"] = gerar_mensagem(user)

🔹 Carregamento (exibição ou persistência dos dados)

for user in users:

    print(user)

🧩 Exemplo 2 — ETL Completo com Arquivo CSV (Mais Profissional)
📥 Estrutura do arquivo users.csv

nome,conta,cartao

Ana,12345-6,****1234

Bruno,65432-1,****5678

Carla,98765-4,****9012

🔹 Extração — Leitura do CSV

import pandas as pd

df = pd.read_csv("users.csv")

🔹 Transformação — Criação de mensagens personalizadas

def gerar_mensagem(nome):

    return f"Olá, {nome}! Temos novidades exclusivas para você 🚀"

df["mensagem"] = df["nome"].apply(gerar_mensagem)

🔹 Carregamento — Salvando novo arquivo CSV

df.to_csv

("users_com_mensagem.csv", index=False)

📁 Estrutura do Projeto
📂 projeto-etl-python
│── users.csv
│── users_com_mensagem.csv
│── etl.py
│── README.md

🛠️ Tecnologias Utilizadas

Python

Pandas

Jupyter Notebook

Conceitos de ETL

Geração de mensagens automatizadas

🎯 Conclusão

Mesmo sem depender de uma API externa, este projeto demonstra:

Domínio do fluxo ETL

Capacidade de adaptação a falhas de fonte de dados

Uso prático de Python para Ciência de Dados

Organização de projeto voltada para portfólio
