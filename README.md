# codigo-das-aulas de POO (metodos,objetos e classe.)
class Produto:
    def _init_(self, nome, preco, quantidade_estoque):
        self.nome = nome
        self.preco = preco
        self.quantidade_estoque = quantidade_estoque

    def adicionar_estoque(self, quantidade):
        """Adiciona uma quantidade ao estoque do produto."""
        if quantidade > 0:
            self.quantidade_estoque += quantidade
        else:
            print("A quantidade a ser adicionada deve ser positiva.")

    def remover_estoque(self, quantidade):
        """Remove uma quantidade do estoque do produto."""
        if 0 < quantidade <= self.quantidade_estoque:
            self.quantidade_estoque -= quantidade
        else:
            print("Quantidade inválida para remoção.")

    def calcular_valor_total_estoque(self):
        """Calcula o valor total do estoque do produto."""
        return self.preco * self.quantidade_estoque

# Criando objetos da classe Produto
produto1 = Produto("Camiseta", 29.99, 100)
produto2 = Produto("Calça Jeans", 99.90, 50)
produto3 = Produto("Tênis Esportivo", 199.90, 30)

# Exemplo de uso dos métodos
print(f"Valor total em estoque de {produto1.nome}: R${produto1.calcular_valor_total_estoque():.2f}")
produto1.adicionar_estoque(20)
produto1.remover_estoque(10)
print(f"Novo valor total em estoque de {produto1.nome}: R${produto1.calcular_valor_total_estoque():.2f}")
