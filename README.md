# prompt_Engieneering_Architecture_04
<img width="1133" height="599" alt="image" src="https://github.com/user-attachments/assets/bd172be5-24ae-49da-96b9-b19300bc8690" />
# ============================================
# SISTEMA SIMPLES DE CADASTRO DE LOGIN
# ============================================

# Criamos um "banco de dados" simples usando um dicionário
# A estrutura será: {usuario: senha}
usuarios = {}


# --------------------------------------------
# FUNÇÃO: cadastrar_usuario
# Objetivo: Criar um novo usuário no sistema
# --------------------------------------------
def cadastrar_usuario():
    print("\n=== CADASTRO DE USUÁRIO ===")

    # Solicita o nome de usuário
    username = input("Digite um nome de usuário: ")

    # Verifica se o usuário já existe
    if username in usuarios:
        print("Erro: usuário já existe!")
        return  # Encerra a função

    # Solicita a senha
    password = input("Digite uma senha: ")

    # Salva no "banco de dados"
    usuarios[username] = password

    print("Usuário cadastrado com sucesso!")


# --------------------------------------------
# FUNÇÃO: fazer_login
# Objetivo: Verificar se o usuário e senha estão corretos
# --------------------------------------------
def fazer_login():
    print("\n=== LOGIN ===")

    # Solicita os dados
    username = input("Usuário: ")
    password = input("Senha: ")

    # Verifica se o usuário existe e se a senha está correta
    if username in usuarios and usuarios[username] == password:
        print("Login realizado com sucesso!")
    else:
        print("Usuário ou senha incorretos.")


# --------------------------------------------
# FUNÇÃO: menu
# Objetivo: Mostrar opções para o usuário
# --------------------------------------------
def menu():
    while True:
        print("\n=== MENU ===")
        print("1 - Cadastrar usuário")
        print("2 - Fazer login")
        print("3 - Sair")

        # Escolha do usuário
        opcao = input("Escolha uma opção: ")

        # Estrutura de decisão
        if opcao == "1":
            cadastrar_usuario()
        elif opcao == "2":
            fazer_login()
        elif opcao == "3":
            print("Encerrando o programa...")
            break  # Sai do loop
        else:
            print("Opção inválida!")


# --------------------------------------------
# PROGRAMA PRINCIPAL
# --------------------------------------------
# Aqui iniciamos o sistema chamando o menu
menu()
