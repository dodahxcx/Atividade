# Atividade
#teste para atividade do curso técnico em redes.
#calculadora cientifica em .py

import math

# Funções básicas
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Erro! Divisão por zero."
    return x / y

# Funções científicas
def square_root(x):
    return math.sqrt(x)

def power(x, y):
    return math.pow(x, y)

def logarithm(x, base=math.e):
    if x <= 0:
        return "Erro! O logaritmo não está definido para valores menores ou iguais a zero."
    return math.log(x, base)

def sine(x):
    return math.sin(math.radians(x))

def cosine(x):
    return math.cos(math.radians(x))

def tangent(x):
    return math.tan(math.radians(x))

def factorial(x):
    if x < 0:
        return "Erro! O fatorial não está definido para números negativos."
    return math.factorial(int(x))

# Função principal da calculadora
def calculator():
    print("Calculadora Científica")
    print("Selecione a operação:")
    print("1. Soma (+)")
    print("2. Subtração (-)")
    print("3. Multiplicação (*)")
    print("4. Divisão (/)")
    print("5. Raiz Quadrada (√)")
    print("6. Exponenciação (^)")
    print("7. Logaritmo (log)")
    print("8. Seno (sin)")
    print("9. Cosseno (cos)")
    print("10. Tangente (tan)")
    print("11. Fatorial (x!)")

    while True:
        choice = input("Digite o número da operação (ou 'sair' para encerrar): ")

        if choice == 'sair':
            print("Saindo da calculadora...")
            break

        if choice in ['1', '2', '3', '4', '6']:
            try:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))
            except ValueError:
                print("Entrada inválida! Por favor, insira números válidos.")
                continue
        elif choice in ['5', '7', '8', '9', '10', '11']:
            try:
                num1 = float(input("Digite o número: "))
            except ValueError:
                print("Entrada inválida! Por favor, insira um número válido.")
                continue

        if choice == '1':
            print(f"{num1} + {num2} = {add(num1, num2)}")
        elif choice == '2':
            print(f"{num1} - {num2} = {subtract(num1, num2)}")
        elif choice == '3':
            print(f"{num1} * {num2} = {multiply(num1, num2)}")
        elif choice == '4':
            print(f"{num1} / {num2} = {divide(num1, num2)}")
        elif choice == '5':
            print(f"√{num1} = {square_root(num1)}")
        elif choice == '6':
            print(f"{num1} ^ {num2} = {power(num1, num2)}")
        elif choice == '7':
            base = float(input("Digite a base (ou aperte Enter para usar o valor padrão e): "))
            print(f"log({num1}) = {logarithm(num1, base)}")
        elif choice == '8':
            print(f"sin({num1}) = {sine(num1)}")
        elif choice == '9':
            print(f"cos({num1}) = {cosine(num1)}")
        elif choice == '10':
            print(f"tan({num1}) = {tangent(num1)}")
        elif choice == '11':
            print(f"{num1}! = {factorial(num1)}")
        else:
            print("Opção inválida!")

# Rodando a calculadora
if __name__ == "__main__":
    calculator()
