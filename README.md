# Projeto-Final---Yorrana-Gabryelly---Tecnicas-De-Desenvolvimento-De-Algoritmos-
 Este projeto é um gerenciador simples de alunos, feito para organizar informações de estudantes de forma rápida e prática. Ele permite criar novos alunos, listar todos os alunos cadastrados e atualizar os dados de cada um, tudo de maneira direta e fácil de usar.
A ideia é criar algo intuitivo, mas funcional, que ajude a treinar lógica de programação e manipulação de dados!
também para adicionar exclusão de alunos, busca por nome ou salvar dados em arquivos. (O projeto de um sistema CRUD (Create, Read, Update e Delete) para gerenciamento de alunos utilizando Python. O sistema permite cadastrar novos alunos, listar todos os registros, atualizar informações existentes e remover alunos da lista.) 

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


