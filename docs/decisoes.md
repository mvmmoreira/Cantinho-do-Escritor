# Decisões de arquitetura: Cantinho do Escritor

Este documento registra as decisões técnicas do projeto e o porquê de cada uma. Novas decisões são adicionadas conforme cada serviço é construído.

## 1. Microsserviços em vez de monólito
**Decisão:** O sistema é dividido em três serviços independentes (Login, Acervo e Contos), com um gateway na frente.
**Por quê:** Cada serviço pode ser desenvolvido, testado e implantado sem depender dos outros, e o projeto mostra como sistemas distribuídos se conectam.
**Alternativa descartada:** Monólito modular. Teria menos peças para subir, mas eu perderia a independência entre os serviços, que é o centro do aprendizado deste projeto.

## 2. Um banco por API
**Decisão:** Uma instância de PostgreSQL com três databases (login, acervo e contos), cada um com usuário próprio e migrações Flyway independentes.
**Por quê:** Cada serviço é dono dos seus dados, e uma mudança de tabela em um serviço não quebra o outro. Usar uma instância só evita subir três servidores.
**Alternativa descartada:** Banco compartilhado. É mais simples, mas acopla os serviços e é um erro clássico de microsserviços.

## 3. Soft delete no Login
**Decisão:** O usuário não é apagado: ele recebe o campo `ativo` com valor falso e deixa de conseguir fazer login.
**Por quê:** Os identificadores guardados no Acervo e no Contos continuam apontando para algo que existe, então não sobram dados órfãos, e a conta pode ser recuperada.
**Alternativa descartada:** Apagar de verdade e avisar os outros serviços por mensageria. É mais completo, mas complexo demais para a v1. Fica para a v2.