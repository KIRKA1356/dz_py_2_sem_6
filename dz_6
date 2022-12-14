from random import randint
print()
print()
print('Это инструкция, как прочтете ее и приступайте к расстанвке кораблей. Сейчас Вы будете задавать координаты своих кораблей, а конкретно каждой палубы, после ввода двух координат на поле выставиться палуба корабля, нумерация полей идет с левого нижнего угла. !!!Числа вводяться СТРОГО от 0 до 5!!!')
print()
print()


matrix = [[0 for j in range(6)] for i in range(6)]
pos=0

pal = int(input('Введите сколько будет палуб в Вашей флотилии: '))
def rast_player(pal,matrix,pos):
    
    for j in range(pal): #  ставится в зависимости от кораблей, а конкретно, их точного количества полуб.   
        for i in range(len(matrix)):
            print(matrix[i])
        visot = int(input(f"Введите кординату Y(высота) вашей {j+1} палубы (от 0 до 5): "))
        shir = int(input(f"Введите кординату X(ширина) вашей {j+1} палубы (от 0 до 5): "))
        chislo = 1
        if 0<=visot<=5 and 0<shir<=5:
            matrix[len(matrix) - visot - 1].insert(shir+1,chislo)
            if shir>5:
                matrix[len(matrix[i]) - visot - 1].pop(shir+1)
            else:
                matrix[len(matrix) - visot - 1].pop(shir-1)
        elif shir == 0: 
            matrix[len(matrix) - visot - 1].insert(shir,chislo)
            matrix[len(matrix) - visot - 1].pop(shir+1)
            print()
        else: 
            print('Выставить Ваш корабль по таким координатам невозможно, прочитайте инструкцию, и запустите программу снова!!!!')
            pos = 1
            break

    if pos == 0:
        print("Ваша итоговая расстановка: ")
        for i in range(len(matrix)):
            print(matrix[i])
rast_player(pal, matrix,pos)

pal_2 = int(input('Введите уровень сложности от 1 до 5, от этого зависит сколько кораблей будет у противника: '))
matrix_2 = [[0 for j in range(6)] for i in range(6)]
def rast_comp(pal_2,matrix_2):
    if pos == 0:
        
        
        pal_2 *=2
        for j in range(pal_2): #  ставится в зависимости от кораблей, а конкретно, их точного количества полуб.   
            print(matrix_2)
            visot_2 = randint(0,5)
            shir_2 = randint(0,5)
            chislo_2 = 1
            matrix_2[len(matrix_2) - visot_2 - 1].insert(shir_2+1,chislo_2)
            if shir_2>5:
                matrix_2[len(matrix_2) - visot_2 - 1].pop(shir_2+1)
            else:
                matrix_2[len(matrix_2) - visot_2 - 1].pop(shir_2-1)
            print()


        print("Расстановка противника: ")
        for i in range(len(matrix_2)):
            print(matrix_2[i])

rast_comp(pal_2,matrix_2)

print()
print()
print('Теперь мы будем стрелять по кораблям противника, а он в ответ будет стрелять по нашим')
print()
print()
s_2=0
s=0
def shoot_and_win(s,s_2,matrix,matrix_2):
    for row in matrix_2: 
        s_2 += sum(row)
    for row in matrix: 
        s += sum(row)
    # print(s_2)
    # print(s)
    for i in range(0,1000):
        if s_2 !=0:
            # print(s_2) 
            s_2 = 0 
            visot_u_ple = int(input(f"Введите кординату Y(высота) удара (от 0 до 5): "))
            shir_u_ple = int(input(f"Введите кординату X(ширина) удара (от 0 до 5): "))
            if matrix_2[len(matrix_2)  - visot_u_ple - 1][shir_u_ple] == 1:
                print("Ура вы попали")
                matrix_2[len(matrix_2) - visot_u_ple - 1].insert(shir_u_ple,0)
                matrix_2[len(matrix_2) - visot_u_ple - 1].pop(shir_u_ple+1)
                for i in range(len(matrix_2)): # 
                    print(matrix_2[i]) # 
                for row in matrix_2: 
                    s_2 += sum(row)
                    # print(s_2)
            else: 
                print("Увы, вы промахнулись")
                s_2 = 0
                for i in range(len(matrix_2)): # 
                    print(matrix_2[i]) # 
                for row in matrix_2: 
                    s_2 += sum(row)
                
        elif s_2 == 0: 
            print("Ура вы победили")
            # print(s_2)
            break
        if s != 0:
            visot_u_comp = randint(0,5)
            shir_u_comp = randint(0,5)
            if matrix[len(matrix)  - visot_u_comp - 1][shir_u_comp] == 1:
                print("Ваш противник попал")
                matrix[len(matrix) - visot_u_comp - 1].insert(shir_u_comp,0)
                matrix[len(matrix) - visot_u_comp - 1].pop(shir_u_comp+1)
                # for i in range(len(matrix)): 
                    # print(matrix[i]) 
                for row in matrix: 
                    s += sum(row)
                    # print(s)
            else: 
                print("Ура, противник мазила")
                s = 0
                # for i in range(len(matrix)): # 
                    # print(matrix[i]) #
                for row in matrix: 
                    s += sum(row)
                
        elif s == 0: 
            print("Увы вы проиграли")
            print(s)
            break

shoot_and_win(s,s_2,matrix,matrix_2)
    



# s=int(input()) #visot
# z=int(input()) #shir
# matrix = [[randint(0, 100) for j in range(6)] for i in range(6)]
# for i in range(len(matrix)):
#         print(matrix[i])
# print(matrix[len(matrix) - s -1][z])