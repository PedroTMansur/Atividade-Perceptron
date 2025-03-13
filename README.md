# Atividade-Perceptron
# Parte 1

from sklearn.linear_model 

import Perceptron

X = [[0, 0], [0, 1], [1, 0], [1, 1]]

Y = [0, 1, 1, 1]

modelo = Perceptron()

modelo.fit(X, Y)

print("Previsões:")

testes = [[0,0], [0,1], [1,0], [1,1]]

for teste in testes:

  previsao = modelo.predict([teste])
  
  print(f"Nuvens: {teste[0]}, Previsão Chuva: {teste[1]} => Levar Guarda-chuva? {'Sim' if previsao[0] == 1 else 'Não'}")

# Parte 2

from sklearn.linear_model 

import Perceptron

X = [
    [0, 0, 0],  
    [0, 0, 1],  
    [0, 1, 0],  
    [0, 1, 1],  
    [1, 0, 0],  
    [1, 0, 1],  
    [1, 1, 0],  
    [1, 1, 1]   
]

Y = [1, 0, 1, 0, 1, 0, 1, 0]

modelo = Perceptron()

modelo.fit(X, Y)

print("Decisão para ir ao parque:")

for teste in X:

    previsao = modelo.predict([teste])
    
    ir_ao_parque = 'Sim' if previsao[0] == 1 else 'Não'
    
    print(f"Tempo ensolarado: {teste[0]}, Dia da semana: {teste[1]}, Parque lotado: {teste[2]} => Ir ao parque? {ir_ao_parque}")

# Parte 3

from sklearn.linear_model 

import Perceptron

X = [
    [1, 1, 1, 1],  
    [0, 1, 1, 0],  
    [1, 0, 1, 1],  
    [0, 0, 0, 0],  
    [1, 1, 0, 1],  
    [0, 1, 0, 1],  
    [1, 1, 1, 0],  
    [0, 0, 1, 1],  
]


y = [1, 0, 1, 0, 0, 0, 1, 0]

modelo = Perceptron()

modelo.fit(X, y)

def decidir_o_que_comer(cansado, tem_ingredientes, restaurante_aberto, dia_pagamento):
  
    previsao = modelo.predict([[cansado, tem_ingredientes, restaurante_aberto, dia_pagamento]])
    
    if previsao[0] == 1:
        return "Comer fora"
    else:
        return "Cozinhar em casa"

print("Decisão para comer:")

for teste in X:

    cansado, tem_ingredientes, restaurante_aberto, dia_pagamento = teste
    
    decisao = decidir_o_que_comer(cansado, tem_ingredientes, restaurante_aberto, dia_pagamento)
    
    print(f"Cansado: {cansado}, Tem ingredientes: {tem_ingredientes}, Restaurante aberto: {restaurante_aberto}, Dia de pagamento: {dia_pagamento} => {decisao}")
