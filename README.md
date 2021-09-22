# PROYECTO-1
Proyecto 1 EMTECH
#PROYECTO 1

from Listas import lifestore_products, lifestore_sales, lifestore_searches
#Inicio proyecto

#Generar entrada de Usuario y Contraseña.
#Usuario: Nombre_Apellido
#Contraseña: EMTECH

Administradores = [['Norma Silva','EMTECH'],['Javier Ramirez','EMTECH']]

Usuario = input ('Ingresa tu usuario :')
Contraseña = input ('Ingresa tu contraseña: ')

Administrador = 0
Intentos = 0

while Administrador != 1 and Intentos < 2:
  for Admin in Administradores:
    if Admin[0] == Usuario and Admin[1] == Contraseña:
      Administrador = 1

  if Administrador == 0:
    print('Usuario o contraseña incorrectos')
    Usuario = input ('Ingresa nuevamente tu usuario :')
    Contraseña = input ('Ingresa nuevamente tu contraseña: ')
    Intentos +=1

if Administrador ==1:
  Saludo = 'Buen día  '
  Unir = Saludo + Usuario
  print(Unir)
  Opción = 0

#MENÚ

Administrador = 1

if Administrador == 1:
   print('Selecciona una opción:\n 1. 10 Productos con mayores ventas\n 2. 10 Productos con mayores búsquedas\n 3. 10 Productos con menores ventas\n 4. 10 Productos con menores búsquedas\n 5. 10 Productos con mayores reseñas\n 6. 10 Productos con menores reseñas\n 7. Ingresos Mensuales')
   Opción = int(input('Opción: '))

if Opción == 1:
    print('10 Productos con Mayores Ventas')
      
elif Opción == 2:
     print('10 Productos con Mayores Búsquedas')

elif Opción == 3:
     print('10 Productos con Menores Ventas')

elif Opción == 4:
     print('10 Productos con Menores Búsquedas')

elif Opción == 5:
     print('10 Productos con Mayores Reseñas')

elif Opción == 6:
     print('10 Productos con Menores Reseñas')

elif Opción == 7:
     print('Ingresos Mensuales')
   
else:
     print('Selecciona un número entre 1 y 7')

#if Administrador == 0:
    #print('Ingresa nuevamente tu Opción: ')
  
#lifestore_sales = [id_sale, id_product, score (from 1 to 5), date, refund (1 for true or 0 to false)]

#lifestore_searches = [id_search, id product]

#lifestore_products = [id_product, name, price, category, stock]

#10 Productos con Mayores Ventas

contador = 0
Ventas_Totales = []

for producto in lifestore_products:
  for venta in lifestore_sales:
    if producto[0] == venta[1]:
      contador += 1 #Suma un elemento
  formato = [producto[0],producto[1],contador]
  Ventas_Totales.append(formato)
  contador = 0 #Reinicia el contador
  #print(Ventas_Totales)

Mayores_Ventas = []

while Ventas_Totales:
  maxim = Ventas_Totales[0][2]
  lista_max = Ventas_Totales[0]
  for Venta_Total in Ventas_Totales:
    if Venta_Total[2] > maxim:
      maxim = Venta_Total[2]
      lista_max = Venta_Total
  Mayores_Ventas.append(lista_max)
  Ventas_Totales.remove(lista_max)
  #print(Mayores_Ventas)

if Opción == 1:
   for conteo in range(0,10):
    print('El producto: ',Mayores_Ventas[conteo][1],'se vendió',Mayores_Ventas[conteo][2],'veces')

#10 Productos con Mayores Búsquedas

contador = 0
Busquedas_Totales = []

for producto in lifestore_products:
  for busqueda in lifestore_searches:
    if producto[0] == busqueda[1]:
      contador += 1 
  formato = [producto[0],producto[1],contador]
  Busquedas_Totales.append(formato)
  contador = 0 

Mayores_Busquedas = []
 
while Busquedas_Totales:
  maxi = Busquedas_Totales[0][2]
  lista_maxi = Busquedas_Totales[0]
  for Busqueda_Total in Busquedas_Totales:
    if Busqueda_Total[2] > maxi:
      maxi = Busqueda_Total[2]
      lista_maxi = Busqueda_Total
  Mayores_Busquedas.append(lista_maxi)
  Busquedas_Totales.remove(lista_maxi)

if Opción == 2:
  for conteo in range(0,10):
   print('El producto: ',Mayores_Busquedas[conteo][1],'se buscó',Mayores_Busquedas[conteo][2],'veces')

#10 Productos con Menores Ventas

contador = 0
Ventas_Totales = []

for producto in lifestore_products:
  for venta in lifestore_sales:
    if producto[0] == venta[1]:
      contador += 1 
  formato = [producto[0],producto[1],contador]
  Ventas_Totales.append(formato)
  contador = 0 
  #print(Ventas_Totales)

Menores_Ventas = []

while Ventas_Totales:
  mini = Ventas_Totales[0][2]
  lista_mini = Ventas_Totales[0]
  for Venta_Total in Ventas_Totales:
    if Venta_Total[2] < mini:
      mini = Venta_Total[2]
      lista_mini = Venta_Total
  Menores_Ventas.append(lista_mini)
  Ventas_Totales.remove(lista_mini)

if Opción == 3:
   for conteo in range(0,10):
     print('El producto: ',Menores_Ventas[conteo][1],'se vendió',Menores_Ventas[conteo][2],'veces')

#10 Productos con Menores Búsquedas

contador = 0
Busquedas_Totales = []

for producto in lifestore_products:
  for busqueda in lifestore_searches:
    if producto[0] == busqueda[1]:
      contador += 1 
  formato = [producto[0],producto[1],contador]
  Busquedas_Totales.append(formato)
  contador = 0 

Menores_Busquedas = []

while Busquedas_Totales:
  minim = Busquedas_Totales[0][2]
  lista_minim = Busquedas_Totales[0]
  for Busqueda_Total in Busquedas_Totales:
    if Busqueda_Total[2] < minim:
      minim = Busqueda_Total[2]
      lista_minim = Busqueda_Total
  Menores_Busquedas.append(lista_minim)
  Busquedas_Totales.remove(lista_minim)

if Opción == 4:
   for conteo in range(0,10):
    print('El producto: ',Menores_Busquedas[conteo][1],'se buscó',Menores_Busquedas[conteo][2],'veces')

#10 Productos con Mejores Reseñas

contador = 0
Total_Resenas = []

for producto in lifestore_products:
  for resena in lifestore_sales:
    if producto[0] == resena[2]:
      contador += 1 
  formato = [producto[0],producto[2],contador]
  Total_Resenas.append(formato)
  contador = 0 

Mayores_Resenas = []

while Total_Resenas:
  maximo = Total_Resenas[0][2]
  lista_maximo = Total_Resenas[0]
  for Total_Resena in Total_Resenas:
    if Total_Resena[2] > maximo:
      maximo = Total_Resena[2]
      lista_maximo = Total_Resena
  Mayores_Resenas.append(lista_maximo)
  Total_Resenas.remove(lista_maximo)

if Opción == 5:
  for conteo in range(0,10):
    print('El producto: ',Mayores_Resenas[conteo][1],'tiene',Mayores_Resenas[conteo][2],'reseñas')

#10 Productos con Peores Reseñas

contador = 0
Total_Resenas = []

for producto in lifestore_products:
  for resena in lifestore_sales:
    if producto[0] == resena[2]:
      contador += 1 
  formato = [producto[0],producto[2],contador]
  Total_Resenas.append(formato)
  contador = 0 

Menores_Resenas = []

while Total_Resenas:
  minimo = Total_Resenas[0][2]
  lista_minimo = Total_Resenas[0]
  for Total_Resena in Total_Resenas:
    if Total_Resena[2] < minimo:
      minimo = Total_Resena[2]
      lista_minimo = Total_Resena
  Menores_Resenas.append(lista_minimo)
  Total_Resenas.remove(lista_minimo)

if Opción == 6:
  for conteo in range(0,10):
    print ('El producto: ',Menores_Resenas[conteo][1], 'tiene',Menores_Resenas[conteo][2],'reseñas')

#Total de ingresos y ventas promedio mensuales, total anual y meses con más ventas al año

Total_Ingreso = []

for ingresos in lifestore_sales:
  lista_ingresos = ingresos[3][3:5]
  Total_Ingreso.append(lista_ingresos)

Orden_Ingreso = []

while Total_Ingreso:
  for Ton_Ing in Total_Ingreso:
    if Ton_Ing[2] < minimo:
      minimo = Ton_Ing[2]
      lista_minimo = Ton_Ing
  Orden_Ingreso.append(lista_minimo)
  Total_Ingreso.remove(lista_minimo)

if Opción == 7:
  for ventas in Orden_Ingreso:
   print(Orden_Ingreso)
