### hamburgueria-json-server API

Arquivo Json para importar no Insomnia: (*Clique direito do mouse -> Salvar link como...*)
- [Download](https://github.com/RafaelSchug/burguerkenzieapi/blob/main/assets/Insomnia_KB_API.json)

## ENDEREÇO DE ACESSO:
https://hamburgueria-json-server.herokuapp.com/

- - -

### Endpoints:

- /products/
- /cart/
- /users/register/
- /users/signin/

- - -

### Criar nova conta: (POST)

- /users/register/

Para criar um novo usuário, informe no corpo da requisição:

```json
    {
        "name": "username",
        "email":"myemail@mail.com",
        "password": "123456"
    }
```

![Criar nova conta](/assets/register.png "Criar nova conta")

- - -

### Efetuar Login: (POST)

Para efetuar login, informe o email e senha utilizados no registro:

- /users/signin/

```json
  {
        "email":"myemail@mail.com",
        "password": "123456"
  }
```
![Efetuar login](/assets/signin.png "Efetuar login")

- - -

### Obter a lista de todos os produtos: (GET)

- /products/


![Obter lista de produtos](/assets/products.png "Obter lista de produtos")

- - -

### Adicionar produto ao carrinho (POST)

- /cart/

:exclamation:**Auth:** É necessário informar o token de autenticação no header.

#### header

**authorization** `Bearer token`

Para adicionar produto ao carrinho, informe no corpo da requisição o id de usuário (informado no login), à **userId**:


```json
   {
      "image": "https://i.ibb.co/wy0BjYh/xburguer.png",
      "title": "X-Burguer",
      "category": "Sanduíches",
      "price": 16,
      "quantity": 1,
      "userId": 2
    }
```

![Adicionar produto ao carrinho](/assets/addToCart.png "Adicionar produto ao carrinho")

- - -

### Listar todos os produtos do carrinho do usuário: (GET)

:exclamation:**Auth:** É necessário informar o token de autenticação no header.

#### header

**authorization** `Bearer token`

Informe o id de usuário (informado no login) para listar todos os produtos adicionados ao carrinho

- /cart/?userId=5
- 

![Listar produtos no carrinho](/assets/getCartList.png "Listar produtos no carrinho")

- - -

### Atualizar informações do produto no carrinho (atualizar quantidade): (PATCH)

:exclamation:**Auth:** É necessário informar o token de autenticação no header.

#### header

**authorization** `Bearer token`

- /cart/5

```json
    {
      "quantity": 2,
    }
```

![Atualizar informações do produto no carrinho](/assets/updateCartItem.png "Atualizar informações do produto no carrinho")

- - -

### Remover produto do carrinho: (DELETE)

:exclamation:**Auth:** É necessário informar o token de autenticação no header.

#### header

**authorization** `Bearer token`


- /cart/:id/



![Remoter produto do carrinho](/assets/deleteFromCart.png "Remover produto do carrinho")
  