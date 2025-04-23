# API-RESTFUL---OPENAPI

## Introdução
Manipular APIs é uma prática essencial na programação moderna, pois permite que aplicações sejam mais dinâmicas e interativas. Esta documentação apresenta uma API RESTful voltada para o universo de Magic: The Gathering (MTG), com foco na criação e gerenciamento de baralhos personalizados.

Com esta API, será possível aos usuários criar baralhos, gerenciar coleções, consultar estatísticas e explorar funcionalidades como busca de cartas, exportação de baralhos, e interações com a comunidade. Tudo isso seguindo o padrão OpenAPI, garantindo clareza, padronização e facilidade de integração.

## Rotas da API

| Método  | Rota                     | Descrição                              | Status Codes        |
|---------|--------------------------|----------------------------------------|---------------------|
| GET     | /cards                   | Listar todas as cartas disponíveis     | 200, 400, 500       |
| GET     | /cards/{id}              | Obter detalhes de uma carta específica | 200, 404, 500       |
| GET     | /cards/search            | Buscar cartas por nome, tipo, cor, etc.| 200, 400, 500       |
| GET     | /sets                    | Listar todas as coleções de MTG        | 200, 500            |
| GET     | /sets/{code}             | Ver detalhes de uma coleção            | 200, 404, 500       |
| GET     | /decks                   | Listar decks públicos                  | 200, 400, 500       |
| GET     | /decks/{id}              | Ver informações de um deck específico  | 200, 404, 500       |
| POST    | /decks                   | Criar um novo deck                     | 201, 400, 401, 500  |
| PUT     | /decks/{id}              | Atualizar informações de um deck       | 200, 400, 401, 404  |
| DELETE  | /decks/{id}              | Excluir um deck                        | 204, 401, 404, 500  |
| POST    | /decks/{id}/favorite     | Marcar um deck como favorito           | 200, 401, 404, 500  |
| GET     | /users/{id}/favorites    | Listar decks favoritos de um usuário   | 200, 401, 404, 500  |
| GET     | /users/{id}/friends      | Listar amigos de um usuário            | 200, 401, 404, 500  |
| POST    | /users/{id}/friends      | Enviar pedido de amizade               | 201, 400, 401, 500  |
| GET     | /tournaments             | Listar torneios disponíveis            | 200, 500            |
| GET     | /tournaments/{id}        | Ver detalhes de um torneio             | 200, 404, 500       |
| POST    | /tournaments             | Criar um novo torneio                  | 201, 400, 401, 500  |
| POST    | /tournaments/{id}/join   | Participar de um torneio               | 200, 401, 404, 500  |
| POST    | /auth/register           | Registrar novo usuário                 | 201, 400, 409, 500  |
| POST    | /auth/login              | Fazer login e obter token de acesso    | 200, 400, 401, 500  |

## DTOs e Modelos de Dados

###  1. CardDTO

```json
{
  "id": 101,
  "name": "Shivan Dragon",
  "manaCost": "{4}{R}{R}",
  "type": "Creature — Dragon",
  "rarity": "Rare",
  "set": "M21",
  "power": "5",
  "toughness": "5",
  "text": "Flying. {R}: Shivan Dragon gets +1/+0 until end of turn.",
  "colors": ["Red"],
  "imageUrl": "https://example.com/cards/shivan-dragon.jpg"
}


