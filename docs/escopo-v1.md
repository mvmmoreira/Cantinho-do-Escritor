# Escopo da v1: Cantinho do Escritor

## Objetivo
O Cantinho do Escritor é uma plataforma para dois públicos: pequenos escritores, que querem guardar e publicar seus contos, e leitores, que querem controlar o próprio acervo de livros. A v1 entrega as duas funções funcionando de ponta a ponta, em uma arquitetura de microsserviços.

## Comportamento

### Todo usuário (Leitor e Escritor)
- Cadastra-se escolhendo o papel (Leitor ou Escritor) e faz login.
- Gerencia o próprio acervo de livros: cadastra livros, marca quais foram lidos, quais foram emprestados e define a prioridade de leitura de cada um.

### Escritor (tudo do Leitor, mais)
- Envia um conto já pronto em PDF.
- Escreve um conto direto no editor de texto da plataforma.
- Mantém cada conto como rascunho ou publicado.

## Regras de negócio
1. O papel é escolhido no cadastro e não pode ser alterado na v1.
2. O Escritor tem acesso a todas as funções do Leitor.
3. Leitor não publica nem envia contos: a tentativa é recusada com erro 403.
4. Cada usuário só vê e altera os próprios livros.
5. Cada Escritor só vê e altera os próprios contos.
6. Usuário inativo (conta desativada) não consegue fazer login.
7. Requisição sem token válido é recusada com erro 401.
8. O upload aceita apenas PDF e tem limite de tamanho.

## Fora da v1
- Leitura pública de contos por outras pessoas
- Troca de papel depois do cadastro
- Fila de leitura com posição exata (na v1 há só prioridade por livro)
- Armazenamento de arquivos em nuvem
- Publicação na web (VPS, domínio e HTTPS)

## Pontos em aberto
- Quais valores a prioridade de leitura aceita (a definir no serviço de Acervo)
- Qual o limite de tamanho do PDF (a definir no serviço de Contos)