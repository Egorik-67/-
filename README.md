[ba.py](https://github.com/user-attachments/files/25869192/ba.py)[Uploading ba.p

import random

def main():

def menu():
    print('          Игра "Угадайка!" ')
    try:
        global num1
        global num2
        global attempts_assumption
        num1 = int(input("Введите первое значение от которого будет загадано число: "))
        num2 = int(input("Введите второе значение до которого будет загадано число: "))
        if num1 > num2:
            print("Первое число не должно быть больше второго! ")
            print(menu())
        attempts_assumption = int(input("За какое колличество попыток вы планируете отгадать число?: "))
    except ValueError:
        print("Вы ввели не число!")
        print(menu())
    print(generate())

def generate():
    global secret_num
    secret_num = random.randint(num1, num2)
    print(play())

def play():
    global user_num
    global attempts
    attempts = 0
    while user_num != secret_num:
        try:
            user_num = int(input("Введите предположенное число: "))
            if num2 > user_num > secret_num:
                print("Загаданое число меньше")
            if num1 < user_num < secret_num:
                print("Загаданое число больше")
            attempts += 1
            if num1 > user_num < num2:
                print("Вы ввели число в не заданого диапозона! ")
                continue
            if user_num == secret_num:
                print("Ты угадал!")
                break
        except ValueError:
            print("Вы ввели не число!")
            print(play())
    print(results())

def results():
    print(f" Ты угадал число за {attempts} попыток!")
    if attempts_assumption <= attempts:
        print("Молодец!")
    else:
        print("Но ты неуложился в предположенные попытки!")
print(main())


y…]()
