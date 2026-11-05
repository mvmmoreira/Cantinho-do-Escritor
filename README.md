# Cantinho do Escritor

Plataforma para pequenos escritores publicarem contos e leitores organizarem seu acervo de livros. Projeto de portfólio feito em microsserviços com Java e Spring Boot.

> **Status:** v1 em construção.

## O que a v1 faz
- **Leitor:** gerencia o acervo pessoal (livros lidos, emprestados e prioridade de leitura).
- **Escritor:** tudo do Leitor, mais envio de contos em PDF ou escritos no editor da plataforma.

## Tecnologias previstas
Java 21, Spring Boot, Spring Security (JWT), Spring Cloud Gateway, PostgreSQL, Flyway, Angular e Docker Compose.

## Repositórios
| Repositório | Função | Status |
| --- | --- | --- |
| `cantinho-do-escritor` | Central: documentação e Docker Compose | Este repositório |
| `cantinho-login-api` | Cadastro, login e JWT | Em breve |
| `cantinho-acervo-api` | Acervo pessoal de livros | Em breve |
| `cantinho-contos-api` | Contos, upload de PDF e editor | Em breve |
| `cantinho-gateway` | Porta de entrada e validação do token | Em breve |
| `cantinho-frontend` | Interface em Angular | Em breve |

## Documentação
- [Decisões de arquitetura](docs/decisoes.md)
- [Escopo da v1](docs/escopo-v1.md)

## Como rodar
Em construção. A v1 vai subir inteira com um comando do Docker Compose.

## Autor
Marcos Vinicius Moreira · [LinkedIn](https://www.linkedin.com/in/marcos-viniciusmoreira)