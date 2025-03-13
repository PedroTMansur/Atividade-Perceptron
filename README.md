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
