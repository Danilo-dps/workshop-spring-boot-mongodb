# Sistema de usuários que fazem post e esses post tem comentários
- Está API é um sistema de web services para gerenciar usuários, posts e comentários, com suporte a operações CRUD e uso de padrões de projeto como DTO. 
É construída com Spring Boot, utilizando MongoDB como banco de dados.

# O que será abordado nesse projeto?
- De forma introdutória, Design patterns(Padrões de projeto)
- Usando o padrão DTO(Data Transfer Object)
- Operações CRUD (Create, Read, Update, Delete) em um banco de dados orientado a documentos.
- Spring Boot, MongoDB, Maven, PostMan

# Design patterns(Padrões de projeto)
 - **Design patterns(Padrões de projeto)**: são soluções reutilizáveis para problemas comuns que surgem durante o desenvolvimento de software. Eles são como um guia ou uma receita para resolver questões de design em diferentes contextos, promovendo melhores práticas e facilitando a manutenção e a escalabilidade do código.

# DTO (Data Transfer Object) 
- **DTO(Data Transfer Object)** é um padrão de design (design pattern). Ele se enquadra na categoria de padrões de transferência de dados. DTOs são utilizados para transportar dados entre camadas diferentes de uma aplicação, como entre a camada de persistência de dados e a camada de apresentação, sem expor a lógica de negócios.
- A ideia geral do padrão DTO:
    - Definição: Um DTO é um objeto simples que não contém lógica de negócios, mas apenas atributos para armazenar dados.
    - Uso: Facilita a transferência de dados com eficiência, minimizando as chamadas de rede e encapsulando os dados que precisam ser enviados ou recebidos de uma maneira organizada.

# Tecnologias Utilizadas
- **Spring Boot**: Framework para construção de aplicações Java, que simplifica a criação de APIs RESTful com configuração mínima.
- **MongoDB**: Banco de dados NoSQL orientado a documentos, que oferece alta performance e flexibilidade para armazenar dados não estruturados.
- **Maven**: Ferramenta de gerenciamento de dependências e construção de projetos Java, que facilita a integração contínua e o gerenciamento de bibliotecas.
- **PostMan**: Ferramenta de teste de API que permite aos desenvolvedores criar, compartilhar, testar e documentar APIs. 
 Com uma interface amigável e recursos avançados como a automação de testes e a integração com CI/CD, o Postman simplifica o processo de desenvolvimento de APIs.

# Exemplo de métodos
- Método `fullsearch` para realizar uma consulta completa com base em um parâmetro
    - Esse é um exemplo do endpoint **GET**:**http://localhost:8080/posts/fullsearch?text=bom**
``` 
[
    {
        "id": "671432b6fbaef226ce6af617",
        "date": "2018-03-23T00:00:00.000+00:00",
        "title": "Bom dia",
        "body": "Acordei feliz hoje!",
        "author": {
            "id": "671432b5fbaef226ce6af613",
            "name": "Maria Brown"
        },
        "comments": [
            {
                "text": "Tenha um ótimo dia!",
                "date": "2018-03-23T00:00:00.000+00:00",
                "author": {
                    "id": "671432b5fbaef226ce6af614",
                    "name": "Alex Green"
                }
            }
        ]
    }
]
``` 
- Metódo `titleSearch` passando um título como pesquisa
    - Esse é um exemplo do endpoint **GET**: http://localhost:8080/posts/titlesearch?text=Bom%20dia
```
[
    {
        "id": "671432b6fbaef226ce6af617",
        "date": "2018-03-23T00:00:00.000+00:00",
        "title": "Bom dia",
        "body": "Acordei feliz hoje!",
        "author": {
            "id": "671432b5fbaef226ce6af613",
            "name": "Maria Brown"
        },
        "comments": [
            {
                "text": "Tenha um ótimo dia!",
                "date": "2018-03-23T00:00:00.000+00:00",
                "author": {
                    "id": "671432b5fbaef226ce6af614",
                    "name": "Alex Green"
                }
            }
        ]
    }
]
```

# Como usar
- Certifique-se de ter instalado o Postman, o MongoDB e o Spring Boot (ou alguma IDE equivalente)
- Clone o repositório
- Inicie o mongodb 
    - Se estiver no debian linux, abra o terminal no modo root e digite `sudo systemctl start mongod`
    - Se estiver no windows, abra o CMD e digite `mongod`
- Abra o projeto na IDE de preferência, importe o projeto
- Vá no pacote `com.danilodps.workshopmongo`
- Na classe `WorkshopmongoApplication`, rode a aplicação como `Spring Boot App`
- Alguns erros podem ocorrer caso o mongodb não esteja inicializado, por isso é importante se certificar que ele esteja funcionando corretamente, use o `chatGPT` para ajudar em algum possível erro
- Com a aplicação rodando perfeitamente, vá para o **PostMan**
- No **PostMan**, teste as requisições 






