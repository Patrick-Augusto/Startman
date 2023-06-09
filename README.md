## Star Man

# Controle de Estoque

Este repositório contém um exemplo de aplicativo de controle de estoque, com um backend escrito em C# usando o Entity Framework e um frontend escrito em HTML e JavaScript.

## Backend

### Descrição

O backend do aplicativo é construído em C# usando o Entity Framework. Ele fornece uma API para adicionar, atualizar e excluir itens de estoque em um banco de dados.

### Como usar

1. Clone este repositório para sua máquina local.
2. Certifique-se de ter o Visual Studio instalado.
3. Abra o projeto no Visual Studio.
4. Abra o arquivo `Program.cs`.
5. No método `Main`, localize a variável `connectionString` e atualize-a com as informações de conexão corretas para o seu banco de dados.
6. Execute o aplicativo.

### Requisitos

- Visual Studio
- Entity Framework
- Banco de dados SQL Server (ou outro banco de dados compatível com o Entity Framework)

### Instalação

1. Clone este repositório para sua máquina local.
2. Abra o projeto no Visual Studio.
3. Restaure os pacotes NuGet necessários.
4. Certifique-se de ter um banco de dados configurado e atualize a string de conexão no arquivo `Program.cs` com as informações corretas do banco de dados.
5. Compile e execute o aplicativo.

### Exemplos

Aqui estão alguns exemplos de como usar o backend do aplicativo:

- Adicionar um novo item de estoque:

```csharp
string name = "Nome do Item";
int quantity = 10;
decimal unitPrice = 9.99;

// Crie um novo item de estoque.
StockItem stockItem = new StockItem()
{
    Name = name,
    Quantity = quantity,
    UnitPrice = unitPrice
};

// Adicione o item de estoque ao contexto.
context.StockItems.Add(stockItem);

// Salve as alterações no banco de dados.
context.SaveChanges();
```

- Excluir um item de estoque existente:

```csharp
int id = 1;

// Exclua o item de estoque do contexto.
var stockItem = context.StockItems.SingleOrDefault(s => s.Id == id);
context.StockItems.Remove(stockItem);

// Salve as alterações no banco de dados.
context.SaveChanges();
```

- Atualizar um item de estoque existente:

```csharp
int id = 1;
string name = "Novo Nome";
int quantity = 5;
decimal unitPrice = 7.99;

// Atualize o item de estoque no contexto.
var stockItem = context.StockItems.SingleOrDefault(s => s.Id == id);
stockItem.Name = name;
stockItem.Quantity = quantity;
stockItem.UnitPrice = unitPrice;

// Salve as alterações no banco de dados.
context.SaveChanges();
```

Certifique-se de substituir os valores de exemplo pelos dados corretos do item de estoque que você deseja adicionar, atualizar ou excluir.

Lembre-se de fechar o contexto após cada operação.

## Banco de Dados 
# Aplicação de Exemplo de Uso do Entity Framework

Este projeto contém um exemplo de aplicação em C# que utiliza o Entity Framework para interagir com um banco de dados local. A aplicação demonstra operações básicas, como adicionar, excluir e atualizar itens de estoque.

## Requisitos

- Microsoft .NET Framework 4.5 ou superior
- Microsoft SQL Server (ou outro banco de dados compatível)

## Configuração do Banco de Dados

Antes de executar a aplicação, é necessário configurar o banco de dados local. Siga as instruções abaixo:

1. Crie um banco de dados vazio no seu servidor SQL local.
2. Abra o arquivo `Program.cs` e localize a string de conexão (`connectionString`) na função `Main`.
3. Substitua `localhost` pelo nome do servidor SQL, `mydb` pelo nome do banco de dados e configure as demais opções de conexão, se necessário.
4. Salve o arquivo após realizar as alterações.

## Diagrama do Banco de Dados

O banco de dados utilizado pela aplicação possui a seguinte estrutura:
```csharp
   +------------------+
      | StockItem |
   +------------------+
      | Id (PK) |
      | Name |
      | Quantity |
      | UnitPrice |
   +------------------+
```
A tabela `StockItem` representa a entidade de estoque, com os campos mencionados acima.

## Executando a Aplicação

Para executar a aplicação, siga os passos abaixo:

1. Abra o projeto no Visual Studio ou em outra IDE compatível com C#.
2. Compile o projeto para garantir que não há erros.
3. Execute a aplicação.
4. A aplicação irá realizar as operações de exemplo no banco de dados local.
5. Observe os resultados no console ou faça alterações no código conforme necessário.




## Frontend

### Descrição

O frontend do aplicativo é construído em HTML e JavaScript. Ele fornece uma interface simples para adicionar, visualizar e remover itens de estoque usando chamadas AJAX para a API fornecida pelo backend.

### Como usar

1. Abra o arquivo `index.html` em um navegador da web.

### Requisitos

- Navegador da web compatível com HTML5 e JavaScript

### Exemplos



Aqui estão alguns exemplos de como usar o frontend do aplicativo:

- Adicionar um novo item de estoque: preencha os campos de entrada e clique em "Add Stock Item".

- Remover um item de estoque existente: clique no botão "Remove" ao lado do item de estoque que você deseja remover.

O frontend se comunicará com o backend por meio das chamadas AJAX para as rotas correspondentes.

## Contribuições

Contribuições são bem-vindas! Se você encontrar problemas, tiver sugestões ou quiser adicionar novos recursos, fique à vontade para enviar um pull request.

## Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).
