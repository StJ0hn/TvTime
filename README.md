# TV Time

Sistema em interface de linha de comando (CLI) para gerenciamento de preferências e histórico de filmes.

## Objetivo
Projeto desenvolvido como seminário para a disciplina de Laboratório de Programação na Universidade Federal do Ceará (UFC). O foco principal foi aplicar conceitos estruturais da linguagem C, como manipulação avançada de structs, ponteiros e persistência manual de dados, construindo uma aplicação multiusuário funcional.

## Stack Tecnológico
* C (C99)
* Compilador: GCC
* Bibliotecas Nativas: stdio.h, string.h, stdlib.h, time.h, ctype.h, stdbool.h

## Arquitetura e Funcionalidades Principais
O sistema opera através do fluxo de carregamento de arquivos para a memória, processamento e salvamento contínuo do estado. As principais características incluem:

* Controle de Acesso Baseado em Perfis: O primeiro usuário registrado assume a função de Administrador (gestão do catálogo de filmes), enquanto os demais operam como Usuários Comuns (registro de visualizações e estatísticas).
* Persistência de Dados (File I/O): Estado do sistema mantido integralmente em arquivos de texto (.txt) gerados dinamicamente.
* Segurança Básica: Implementação de um algoritmo de transformação de caracteres (shift) para evitar o armazenamento de senhas em texto puro.
* Estruturação de Dados: Lógica dividida em structs focadas na responsabilidade única (usuario_comum, filme, e filmes_assistidos).

## Como Executar Localmente

1. Clone o repositório:
git clone https://github.com/StJ0hn/tv-time.git

2. Acesse a pasta do projeto e compile o código-fonte via GCC:
gcc -o tvtime main.c

3. Execute a aplicação:
./tvtime

## Desafios Técnicos e Aprendizados
O maior desafio técnico consistiu em garantir a integridade relacional dos dados sem o auxílio de um Sistema de Gerenciamento de Banco de Dados (SGBD). A necessidade de mapear manualmente as relações entre usuários e filmes utilizando arquivos de texto forçou um entendimento profundo sobre I/O em C e gerenciamento de estado em memória, solidificando as bases de estruturação de dados antes da introdução a bancos relacionais.

---
Autores: John Miguel da Silva Fernandes, Enzo Andrade dos Anjos e Luis Eduardo Bezerra Gois.
