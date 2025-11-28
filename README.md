# Projeto-Final---Yorrana-Gabryelly---Tecnicas-De-Desenvolvimento-De-Algoritmos-
 Este projeto é um gerenciador simples de alunos, feito para organizar informações de estudantes de forma rápida e prática. Ele permite criar novos alunos, listar todos os alunos cadastrados e atualizar os dados de cada um, tudo de maneira direta e fácil de usar.
A ideia é criar algo intuitivo, mas funcional, que ajude a treinar lógica de programação e manipulação de dados!
também para adicionar exclusão de alunos, busca por nome ou salvar dados em arquivos. (O projeto de um sistema CRUD (Create, Read, Update e Delete) para gerenciamento de alunos utilizando Python. O sistema permite cadastrar novos alunos, listar todos os registros, atualizar informações existentes e remover alunos da lista.) 

Linguagem Utilizada

O sistema foi desenvolvido em Python, devido à sua simplicidade e facilidade para manipulação de listas e dados.
	•	Python permite criar funções, listas e menus interativos de forma clara e intuitiva.
	•	Todas as funcionalidades estão implementadas em um único arquivo (main.py), com comentários explicativos em cada função.

	Descrição do Trabalho

O objetivo deste projeto é desenvolver um sistema de gerenciamento de alunos que permita criar, listar e atualizar informações de estudantes.

O trabalho tem como finalidade:
	•	Demonstrar o uso de listas e estruturas de dados em programação;
	•	Aplicar conceitos de lógica e algoritmos, como pseudocódigo e fluxograma;
	•	Praticar a documentação de software, incluindo README, pseudocódigo e fluxograma;
	•	Desenvolver uma aplicação funcional e organizada, servindo como base para projetos maiores.


Funcionalidades: 
	•	Criar Aluno: Adiciona um novo aluno à lista, com nome, idade e curso.
	•	Listar Alunos: Mostra todos os alunos cadastrados, com todos os dados.
	•	Atualizar Aluno: Permite alterar os dados de um aluno específico.
  
  # Projeto CRUD de Alunos

Este projeto demonstra um CRUD simples (Create, Read, Update, Delete) para gerenciamento de alunos usando Python.
CODIGO FONTE:

```python
alunos = []

def criar_aluno(nome, idade, curso):
    aluno = {"nome": nome, "idade": idade, "curso": curso}
    alunos.append(aluno)

def listar_alunos():
    return alunos

def atualizar_aluno(indice, novo_nome, nova_idade, novo_curso):
    if 0 <= indice < len(alunos):
        alunos[indice]["nome"] = novo_nome
        alunos[indice]["idade"] = nova_idade
        alunos[indice]["curso"] = novo_curso
        return True
    return False

def deletar_aluno(indice):
    if 0 <= indice < len(alunos):
        alunos.pop(indice)
        return True
    return False

while True:
    print("\nCRUD de Alunos")
    print("1 - Cadastrar aluno")
    print("2 - Listar alunos")
    print("3 - Atualizar aluno")
    print("4 - Deletar aluno")
    print("0 - Sair")

    opcao = input("Escolha uma opção: ")

    if opcao == "1":
        nome = input("Nome: ")
        idade = input("Idade: ")
        curso = input("Curso: ")
        criar_aluno(nome, idade, curso)
        print("Aluno cadastrado!")

    elif opcao == "2":
        print("\nLista de alunos:")
        for i, a in enumerate(listar_alunos()):
            print(f"{i} - {a['nome']} | {a['idade']} anos | Curso: {a['curso']}")

    elif opcao == "3":
        indice = int(input("Índice do aluno: "))
        novo_nome = input("Novo nome: ")
        nova_idade = input("Nova idade: ")
        novo_curso = input("Novo curso: ")
        if atualizar_aluno(indice, novo_nome, nova_idade, novo_curso):
            print("Aluno atualizado!")
        else:
            print("Índice inválido.")

    elif opcao == "4":
        indice = int(input("Índice do aluno: "))
        if deletar_aluno(indice):
            print("Aluno deletado!")
        else:
            print("Índice inválido.")

    elif opcao == "0":
        print("Saindo...")
        break

    else:
        print("Opção inválida!")

PSEUDOGOÓDIGO

    SE opção = criar:
        ler nome, idade, curso
        adicionar aluno na lista

    SE opção = listar:
        mostrar cada aluno

    SE opção = atualizar:
        ler índice
        ler novos dados
        atualizar aluno na posição escolhida

    SE opção = deletar:
        ler índice
        remover aluno da lista

    SE opção = sair:
        encerrar programa

FLUXOGRAMA

Início
 ↓
Exibe menu
 ↓
Usuário escolhe opção
 ├── Cadastrar → lê dados → adiciona aluno → volta
 ├── Listar → mostra todos → volta
 ├── Atualizar → lê índice → lê novos dados → altera → volta
 ├── Deletar → lê índice → remove → volta
 └── Sair → Fim

LINGUAGEM ALGORÍTMICA 

  Algoritmo CriarAluno
  Entrada: nome, idade, curso
  Processo: adicionar aluno à lista
  Saída: aluno criado
  FimAlgoritmo

Algoritmo ListarAlunos
  Entrada: nenhuma
  Processo: percorrer lista de alunos
  Saída: exibição dos dados
FimAlgoritmo

Algoritmo AtualizarAluno
  Entrada: indice, novo_nome, nova_idade, novo_curso
  Processo: substituir dados do aluno
  Saída: confirmação
FimAlgoritmo

Algoritmo DeletarAluno
  Entrada: indice
  Processo: remover aluno da lista
  Saída: confirmação
FimAlgoritmo

exemplo-execucao.txt

$ python main.py
==========================
   GERENCIADOR DE ALUNOS
==========================

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 1

NOME: Ana
IDADE: 22
CURSO: Engenharia
Aluno criado com sucesso!

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 1

NOME: João
IDADE: 20
CURSO: Informática
Aluno criado com sucesso!

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 2

ALUNOS CADASTRADOS:
1. Ana, 22 anos, Curso: Engenharia
2. João, 20 anos, Curso: Informática

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 3

Escolha o índice do aluno que deseja atualizar: 2
Novo nome: João Pedro
Nova idade: 21
Novo curso: Ciência da Computação
Aluno atualizado com sucesso!

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 2

ALUNOS CADASTRADOS:
1. Ana, 22 anos, Curso: Engenharia
2. João Pedro, 21 anos, Curso: Ciência da Computação

1. Criar Aluno
2. Listar Alunos
3. Atualizar Aluno
4. Sair
Escolha uma opção: 4

Saindo do sistema...


Projeto-Final/
│
├─ main.py                 # Código principal do sistema
├─ README.md               # Documentação, descrição e instruções
├─ pseudocodigo.txt        # Pseudocódigo do projeto
├─ fluxograma.png          # Fluxograma do sistema
└─ exemplo_execucao.txt    # (opcional) exemplo de uso/executação


