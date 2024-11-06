# Token-jwt

**Descrição**:
> Este projeto implementa um sistema de autenticação baseado em JSON Web Token (JWT) usando a linguagem Go. A API permite que os usuários se registrem, façam login e acessem recursos protegidos através de um token JWT. Esse tipo de autenticação é útil para aplicações que precisam de um sistema seguro de controle de acesso, garantindo que apenas usuários autenticados possam acessar determinadas funcionalidades.

---

## Tabela de Conteúdos

- [Pré-requisitos](#pré-requisitos)
- [Tecnologias](#tecnologias)
- [Contribuição](#contribuição)
- [Licença](#licença)
- [Autores](#autores)

---

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- [Go 1.19+](https://golang.org/dl/)
- [Docker](https://www.docker.com/) (opcional, para rodar o banco de dados em contêiner)


---

## Tecnologias

- Backend: [GoLang](https://go.dev/)
- Lib: 
  - [JWT-Go](https://github.com/golang-jwt/jwt): Para geração e validação de tokens JWT
  - [GORM](https://gorm.io/): Para manipulação de banco de dados
  - [Gin](https://gin-gonic.com/): Framework web leve para Go
  - Banco de Dados: PostgreSQL

---

## Contribuição
Contribuições são bem-vindas! Para contribuir, siga estes passos:

1. Faça um fork do projeto
2. Crie uma nova branch: `git checkout -b minha-feature`
3. Faça suas alterações e confirme-as: `git commit -m 'feat: descricao da feature'`
4. Envie para a branch principal: `git push origin minha-feature`
5. Abra um Pull Request

---

## Licença
Este projeto está licenciado sob a [MIT License](https://mit-license.org/)

---

## Autores

- [Mizael Pardal](https://github.com/Myze16)
- [Pedro Coelho](https://github.com/pedro-coelho1604)

---

# Conceito - JSON Web Token(JWT)

### O que é JWT?
O JWT (JSON Web Token) é um padrão de token compacto e seguro usado para autenticação e troca de informações entre diferentes partes (como cliente e servidor). Ele é composto por três partes:

1. Header: Define o tipo de token (JWT) e o algoritmo de criptografia.
```
{
    "alg": "HS256",
    "typ": "JWT"
}
```
2. Payload: Contém as "claims" (informações), como ID do usuário e tempo de expiração.
```
{
    "sub": "1234567890",
    "name": "John Doe",
    "admin": true
}
```
3. Signature: Garante a integridade do token, usando uma chave secreta para evitar adulterações.
```
    HMACSHA256(
    base64UrlEncode(header) + "." +
    base64UrlEncode(payload),
    secret)
```
Após o login, o servidor gera um JWT e o envia ao cliente. O cliente armazena o token e, em cada requisição subsequente, envia-o no cabeçalho de autorização. O servidor então valida o token para autenticar o usuário, sem precisar manter uma sessão. Isso torna o JWT ideal para sistemas escaláveis e APIs RESTful, pois ele é autossuficiente e não exige armazenamento de estado no servidor.

---


## Referências

- https://jwt.io/



