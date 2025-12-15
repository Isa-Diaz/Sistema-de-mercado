class Produto:
    def __init__(self, preco, qntd, nome, medida, tamanho_real):
        self.preco = preco
        self.qntd = qntd
        self.nome = nome
        self.medida = medida
        self.tamanho_real = tamanho_real

Lista_produtos = []

def adicionar_produto(lista, nome, medida, quantidade, preco, tamanho_real):
    for item in lista:
        if item.nome == nome and item.tamanho_real == tamanho_real and item.medida == medida:
            item.qntd = item.qntd + quantidade
            return
        
    nova = Produto(preco, quantidade, nome, medida, tamanho_real)
    lista.append(nova)

def remover_produto(lista, nome, medida, tamanho_real, quantidade, acao):
    for item in lista:
        if item.nome == nome and item.tamanho_real == tamanho_real and item.medida == medida:
            if acao == "EXCLUIR":
                lista.remove(item)
                return

            elif acao == "REMOVE":
                item.qntd = item.qntd - quantidade
                if item.qntd <= 0:
                    lista.remove(item)
                    return

    else:
        print("ERRO: Produto não encontrado")
        return
    
def listar_produtos(lista):
    for indice in range(len(lista)):
        produto = lista[indice]
        print(f'{indice}- {produto.nome} {produto.tamanho_real:g}{produto.medida} - Quantidade:{produto.qntd:g} - Preço: {produto.preco:g}')
       
def comparar(preco1, tamanho_real1, preco2, tamanho_real2):
    resultado1 = preco1/tamanho_real1
    resultado2 = preco2/tamanho_real2
    
    if resultado1 < resultado2:
        print("Produto 1 mais barato")
    elif resultado1 == resultado2:
        print("Produtos equivalente")
    else:
        print("Produto 1 mais caro")

while True:
    print('\n________MENU_______\n')
    print("O que você gostaria de fazer?")
    escolha = input("1 → Adicionar produto \n2 → Remover produto \n3 → Listar produtos \n4 → Comparar produtos \n0 → Sair\n \nDigite Aqui: ")

    if escolha == "1":
        add = "S"
        
        while add =="S":
            nome_produto = input("Nós informe o nome do Produto: ")
            medida_produto = input("Nós informe o tipo (kg, gramas, ml ...): ")
            medida_produto = medida_produto.lower()
            while True:
                try:
                    tamanho_real_produto = float(input("Informe o tamanho real do produto (apenas o número, ex: 200):"))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")

            while True:
                try:
                    quantidade = int(input("Quantas unidades que adicionar: "))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")

            
            preco_produto1 = input("Nós informe o preço: ")
            preco_produto1 = preco_produto1.replace(",", ".")
            preco_produto = float(preco_produto1)

            adicionar_produto(Lista_produtos, nome_produto, medida_produto,quantidade, preco_produto, tamanho_real_produto)
            add = input("Quer adicionar outro produto? (S / N): ")
            add = add.upper()

    elif escolha == "2":
        nome_produto = input("Nos informe o nome do Produto: ")
        medida_produto = input("Nós informe o tipo (kg, gramas, ml ...)")
        medida_produto = medida_produto.lower()
        while True:
                try:
                    tamanho_real_produto = float(input("Informe o tamanho real do produto (apenas o número, ex: 200):"))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")

        while True:
                try:
                    quantidade = int(input("Quantas unidades que retirar: "))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")
        
        
        acao = input("Você gostaria de REMOVE ou EXCLUIR o produto: ")
        acao = acao.upper()
        remover_produto(Lista_produtos, nome_produto, medida_produto, tamanho_real_produto, quantidade, acao)

    elif escolha == "3":
        listar_produtos(Lista_produtos)


    elif escolha == "4":
        while True:
                try:
                    tamanho_produto1 = float(input("Informe o tamanho real do PRIMEIRO produto (apenas o número, ex: 200):"))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")


        while True:
                try:
                    tamanho_produto2 = float(input("Informe o tamanho real do SEGUNDO produto (apenas o número, ex: 200):"))
                    break
                except ValueError:
                    print("Valor inválido! Digite apenas números.")

        
        preco_produto1 = input("Nós informe o preço do PRIMEIRO produto: ")
        preco_produto1 = preco_produto1.replace(",", ".")
        preco1 = float(preco_produto1)

        preco_produto2 = input("Nós informe o preço do SEGUNDO produto: ")
        preco_produto2 = preco_produto2.replace(",", ".")
        preco2 = float(preco_produto2)
        
        comparar(preco1, tamanho_produto1, preco2, tamanho_produto2)
    else:
        break
