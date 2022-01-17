# Como funciona?
A API possui seis rotas: **/register /auth /item /items /store /stores**

Primeiro vou ensinar a iniciar ela e depois explico cada rota.

# Como testar?
Clone o repositório e entre nele:



    git clone https://github.com/runiorr/flask-restapi runiorr/ && cd runiorr/



Crie uma VM, instale as libs necessárias e inicie a aplicação.



    python3 -m venv <venv> // Crie ela - Escolha o nome para a venv em <venv>
    source <venv>/bin/activate // Inicie ela
    pip install -r requirements.txt // Instale as libs
    python app.py


*Pronto!* O acesso as rotas se dá por meio do http://localhost:5000/

# Rotas
## /register
A primeira rota recebe dois parâmetros pelo body da requisição: **username e password** e cria um usuário com eles.


    "username": "username",
    
    "password": "password"


## /auth
A rota auth, recebe os mesmos dois parâmetros pelo body da requisição: **username e password** e verifica se está correto. 


    "username": "username",
    
    "password": "password"


No caso de sucesso, você recebe um JWT para acessar outra rotas.
Na falha, ela informa o erro ocorrido.

## /items

Devolve todos os itens armazenados no banco de dados.

## /item/<name> - GET, POST, DELETE, PUT

Receber um item específico, inserir um item, deletar um item e atualizar um item.
A rota GET necessita do JWT.

Recebe três parâmetros da requisição: **price e store_id** do body e um **nome** da url

{
    "price": 15.99,
    "store_id": 1
}

## /stores

Devolve todos as lojas armazenadas no banco de dados.

## /store/<name> - GET, POST, DELETE

Receber uma loja específica, inserir uma loja, deletar uma loja.

Recebe um parâmetros da requisição: o **nome** dela pela url

