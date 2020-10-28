# Buscaminas

import random
#import os

def crea_tablero(fil, col, val):
  tablero=[]
  for i in range(fil):
    tablero.append([])
    for j in range(col):
      tablero[i].append(val)
  return tablero

def muestra_tablero(tablero):
  for fila in tablero:
    for elem in fila:
      print(elem,end=' ')
    print()  

def coloca_minas(tablero, minas, fil,col):
  minas_ocultas=[]
  numero=0
  while numero < minas:
    y=random.randit(0,fil-1)
    x=random.randit(0,col-1)
    if tablero[y][x]!=9:
      tablero[y][x]=9
      numero+=1
      minas_ocultas.append((y,x))
  return tablero, minas_ocultas


#def presentacion():
  #os.system("cls")



columnas=10
filas=10

visible= crea_tablero(filas,columnas,'-')
oculto= crea_tablero(filas,columnas,'-')

oculto,minas_ocultas= coloca_minas(oculto,15,filas,columnas)
#presentacion()
