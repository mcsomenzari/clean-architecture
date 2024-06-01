# Clean Architecture Full Cycle

## Execução da Aplicação

1. Subir os containers Docker:
    Inicialize os containers Docker que contêm o banco de dados e o RabbitMQ usando o seguinte comando:
    
    ```bash
    docker-compose up -d
    ```

2. Preparar o Ambiente:
    Após os containers estarem em execução, execute os seguintes comandos para configurar o ambiente:

    - Comando abaixo irá buscar todos as depêndencias necessária:
    
     ```bash
    go mod tidy
    ```

    - Comando abaxio responsável por criar as migrations no banco de dados:

     ```bash
    make migrate
    ```

3. Executar a Aplicação:
    Por fim, inicie a aplicação executando o seguinte comando:
    
     ```bash
    cd cmd/ordersystem
    go run main.go wire.go
    ```

4. Aqui estão as portas disponíveis e os respectivos serviços associados:

### GraphQL - 8080
    Esta porta é usada para acessar o servidor GraphQL, que oferece consultas e mutações para interagir com a aplicação de forma flexível e eficiente.
  
### Banco de Dados MySQL - 3306
    Esta porta é usada para se comunicar com o banco de dados MySQL, que armazena e gerencia os dados da aplicação.

### gRPC (Remote Procedure Call) - 50051
    Esta porta é usada para comunicação RPC entre os serviços da aplicação, proporcionando uma forma eficiente e padronizada de interação entre componentes distribuídos.
  
### API REST - 8000
    Esta porta é usada para acessar a API REST da aplicação, que fornece pontos de extremidade HTTP para realizar operações CRUD (Create, Read, Update, Delete) nos recursos da aplicação.
