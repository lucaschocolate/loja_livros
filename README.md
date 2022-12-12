# loja_livros
import pandas as pd
from matplotlib import pyplot as plt
import numpy as np


#Abrindo o arquivo:
#df_livraria = pd.read_csv("books_scraped.csv")
#print(df_livraria.head())



class Cliente:
  def __init__(self,nome,email,endereco):
    self.nome = nome
    self.email = email
    self.endereco = endereco
    nome_cliente = input("Digite o seu nome: ")
    email_cliente = input("Digite o seu email: ")
    endereco_cliente = input("Digite o seu endereço: ")
    self.carrinho = Carrinho()

  def mostrar_catalogo(self):
    "Plota na tela uma tabela com o catálogo dos livros"
    df_livraria = pd.read_csv("books_scraped.csv")
    display(df_livraria)

  def ordenar_produtos(self):#Ordenar a lista de produtos para visualização(groupby)
    "Ordena e mostra uma tabela com o nome dos livros, preço e quantidade no estoque"
    df_livraria = df_livraria.groupby("Title").sum()
    display(df_livraria)

  def calcular_produto(self,carrinho):
    "Calcular o valor do carrinho de compras do cliente"
    print(self.carrinho.sum())
  

class Carrinho:
  def __init__(self,produtos):
    self.produtos = produtos
  
  def add_produto(self, lista_produto):
    lista_produto = []
    opcao = input("Escreva o nome do produto: ")
    self.lista_produto.append(opcao)  

class Produto:
  def __init__(self):# filtrar pelo produto a partir
    pass

class Vendedor(Cliente):
  def __init__(self):
    pass

class Administrador:
  def __init__(self,nome_adm,senha):
    self.nome = nome_adm
    self.senha = senha
    print(f"Bem vindo,{nome_adm}!")
    if senha == '12345':
      print("Acesso liberado")
  def menu(self):
    print("MENU ADM:") 
    print("1 - Visualizar o catálogo de produtos e suas quantidades em estoque")
    print("2 - Adicionar produtos ao estoque")
    print("3 - Alterar o preço de um produto")
    print("4 - Visualizar gráficos com estatísticas de compras")
    print("5 - Fechar")
    escolha = input("Escolha uma opção acima: ")

  def catalogo_atualizado(self):
    pass
  
  def visualizar_graficos(self):#plotar gráficos com estatísticas de compras
    "Apenas um exemplo!"
    df_livraria = df_livraria.groupby("Title").sum()
    df_livraria[:5].plot(figsize=(20,10))

###-------------------------------------------------------------------------------------------------###
def main():# apenas no final do projeto, executar a função main
    print(mostrar_catalogo)
    cliente1 = Cliente("lucas","lcs@gmail")
    catalogo = cliente1.mostrar_catalogo()
    menu()


if __main__ == "__main__":
  main()
