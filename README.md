import random
import time

def fazer_pergunta(operacao):
    if operacao == "adição":
        a = random.randint(1, 100)
        b = random.randint(1, 100)
        resposta_correta = a + b
        pergunta = f"Quanto é {a} + {b}? "
    elif operacao == "subtração":
        a = random.randint(1, 100)
        b = random.randint(1, a)
        resposta_correta = a - b
        pergunta = f"Quanto é {a} - {b}? "
    elif operacao == "multiplicação":
        a = random.randint(1, 12)
        b = random.randint(1, 12)
        resposta_correta = a * b
        pergunta = f"Quanto é {a} x {b}? "
    elif operacao == "divisão":
        b = random.randint(1, 12)
        resposta_correta = random.randint(1, 12)
        a = resposta_correta * b
        pergunta = f"Quanto é {a} ÷ {b}? "
    return pergunta, resposta_correta

def jogo_de_matematica():
    print("Bem-vindo ao Desafio Matemático!")
    pontos = 0
    num_rodadas = 5
    operacoes = ["adição", "subtração", "multiplicação", "divisão"]

    for _ in range(num_rodadas):
        operacao = random.choice(operacoes)
        pergunta, resposta_correta = fazer_pergunta(operacao)
        print(pergunta)
        
        inicio_tempo = time.time()
        resposta_usuario = int(input())
        fim_tempo = time.time()
        
        if fim_tempo - inicio_tempo > 30:
            print("Tempo esgotado!")
        elif resposta_usuario == resposta_correta:
            print("Correto!")
            pontos += 10
        else:
            print("Incorreto!")
    
    print(f"Você terminou o jogo com {pontos} pontos.")

if __name__ == "__main__":
    jogo_de_matematica()







