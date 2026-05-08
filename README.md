# TV Time

Aplicação de terminal para gerenciamento de preferências sobre filmes, desenvolvida em C como parte de um seminário da disciplina de **Laboratório de Programação** na Universidade Federal do Ceará (UFC).

---

## Sobre o Projeto

O TV Time é um sistema multiusuário com dois perfis distintos: **administrador** e **usuário comum**. O admin cadastra filmes no catálogo; os usuários registram o que assistiram, em qual plataforma e quando — e podem visualizar estatísticas do seu histórico.

Todos os dados são persistidos em arquivos `.txt`, mantendo o estado entre execuções.

---

## Funcionalidades

### Administrador (primeiro usuário cadastrado)
- Cadastrar filmes com nome, duração, gênero e ano

### Usuário Comum
- Registrar filmes assistidos (com plataforma e data)
- Listar histórico pessoal de filmes assistidos
- Ver estatísticas: total de filmes e tempo total assistido

### Geral
- Cadastro e login com senhas criptografadas
- Validação de dados de entrada (datas, duração, ano)
- Persistência automática em arquivos

---

## Tecnologias

- **Linguagem:** C (C99)
- **Compilador:** GCC
- **Persistência:** Arquivos de texto (`.txt`)
- **Bibliotecas:** `stdio.h`, `string.h`, `stdlib.h`, `time.h`, `ctype.h`, `stdbool.h`

---

## Como Executar

### Pré-requisitos
- GCC instalado (`gcc --version`)

### Compilar e rodar

```bash
gcc -o tvtime main.c
./tvtime
```

---

## Estrutura dos Arquivos

```
tv-time/
├── main.c              # Código-fonte principal
├── usuarios.txt        # Gerado automaticamente — dados dos usuários
├── filmes.txt          # Gerado automaticamente — catálogo de filmes
└── assistidos.txt      # Gerado automaticamente — histórico de visualizações
```

---

## Segurança de Senhas

As senhas não são armazenadas em texto puro. Ao cadastrar, cada caractere passa por uma transformação (shift + conversão para maiúsculas) antes de ser salvo no arquivo `usuarios.txt`.

---

## Arquitetura

O projeto utiliza três `structs` principais:

| Struct | Responsabilidade |
|---|---|
| `usuario_comum` | Armazena login, senha, nome e tipo (admin/comum) |
| `filme` | Armazena nome, duração (em minutos), gênero e ano |
| `filmes_assistidos` | Liga um usuário a um filme, com plataforma e data |

O fluxo de dados segue o padrão: **carregar arquivos → operações em memória → salvar arquivos** a cada modificação.

---

## Autores

**John Miguel da Silva Fernandes, Enzo Andrade dos Anjos e Luis Eduardo Bezerra Gois**  
Estudante de Engenharia de Software — UFC, Campus Russas  
[github.com/StJ0hn](https://github.com/StJ0hn) · [linkedin.com/in/john-fernandesdev](https://linkedin.com/in/john-fernandesdev)
