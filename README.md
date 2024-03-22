# Parcial-1

```python
import json
import os

# Limpia la pantalla
os.system("cls")

# Intenta abrir y leer el archivo
try:
    with open("cursos.json", "r") as archivo:
        leer = archivo.read()
                                    # Comprueba si hay contenido antes de intentar cargar el JSON
        if leer.strip():            # Si leer tiene contenido (no está vacío)
            js = json.loads(leer)
        else:
            js = {}                 # Crea un diccionario vacío si el archivo está vacío
except FileNotFoundError:           # Maneja el caso de que el archivo no exista
    js = {}                         # Crea un diccionario vacío si el archivo no existe


# ___________ABRIR____________


while True:
 try:
  os.system("cls")
  orden0 = int(input("SELECCIONE QUÉ DESEA HACER" "\n" "\n"
               "1. Consultar un estudiante" "\n"
               "2. Modificar un estudiante" "\n"
               "3. Agregar a un estudiante" "\n"
               "4. Eliminar un estudiante" "\n"
               "5. SALIR" "\n"))
 except ValueError:
   print("\nLas letras no son caracetres validos para este menu")
   input("\nOprimar cualquier tecla para continuar\n")
   continue
 
 except KeyboardInterrupt:
      print("\n Bromista")
      input("\nOprimar cualquier tecla para continuar\n")
      continue

 if orden0 == 1:
     os.system("cls")
     menu1 = print("¿QUÉ DESEA CONSULTAR?", "\n", "\n",
                   "1. Consulta completa", "\n",
                   "2. Consultar asignatuars del curso", "\n",
                   "3. Consultar notas por grupo", "\n",
                   "4. Consultar notas por asignatura", "\n",
                   "0. SALIR", "\n")
  else:
   print("Rango no valido")
   input("Oprima cualquier tecla para continuar") 
   continue

 try:
     orden51= int(input("Seleccione la accion que desea realizar: "))
     
     if orden51 == 1:
       orden52 = input("¿Cual es el codigo del estudiante?")
       if orden52.isdigit():
         print("SISIS")
       else:
         print("\nNo son validas las letras en enta opcion \n")
         input("Oprimar cualquier tecla para continuar")
         continue
       os.system("cls")
       for k,v in js.items():                              #grupo=G01, G02         codigo_nombre=100001:{juan:{}}
        for codigos, nombre_asig in v.items():                    #codigo=10001           nombre_asignaturas={juan}calculo   
         if orden52 in codigos:
          print(f"\nCodigo: {orden52}")
          for nombre55, materia_nota in nombre_asig.items():           #nombres=Juan           materia_nota={calculo: 4.2}
           if orden52 in codigos:
             print(f"Estudiante: {nombre55} ")
           for materia, notas in materia_nota.items():
            if orden52 in codigos:
             print(f" Asignatura: {materia} - Notas: {notas}")
             continue
           if orden52 in codigos:
             print(" ")
             input("Oprima cualquier tecla para continuar")
             break
          if orden52 in codigos:
            break
        if orden52 in codigos:
          break
       if orden52 not in codigos:
         print("\nNo se encuentra ningun estudiante conectado a ese codigo \n")
           
     elif orden51 == 2: 
       os.system("cls")
       orden53 = input("Digite el grupo que desea consultar de la siguiente manedera: G01, G02, G03 etc")
       prueba = js[orden53]   #dentro de grupo 1
       print(" \n"f"Grupo {orden53}: \n")
       for codigo, nombres in prueba.items():
        for llamar, asignaturas in nombres.items():
         for apellidos, asig_not in asignaturas.items():
          print( f"Asignatura 1: {apellidos}")
       orden_continuar3= input("\n Presione Enter para continuar")
       if orden_continuar3 == " ":
             os.system("cls")
       continue
  
     elif orden51 == 3:
      os.system("cls")
      orden54=input("Digite el grupo que desea consultar, de la siguiente manera: G01, G02, G03 etc")
      for codigo, nombre_asig in js[orden54].items():           #codigo=10001                nombre_asig={'JUAN CASTELLANOS PEREZ': {'CALCULO 1': 4.5,    
       for nombre, asignatura in nombre_asig.items():        #nombre=juan           asignatura={'CALCULO 1': 4.5, 'FISICA 1': 4.1,
        print(f" Estudiante: {nombre}\n Codigo: {codigo}")
        for materia, promedio in asignatura.items():         #materia=calculo 1       promedio=4.5 3.6 2.0                         
         print(f"     Asignatura 1: {materia} - Nota: {promedio}")
      continue

     elif orden51 == 4:
       os.system("cls")
       orden53=input("Digite la asignatura que desea consultar")
       for grupo,codigo_nombre in js.items():                         #grupo=g01 g02                       codigo_nombre=codigo{juan{...}}
        for codigo, nombre_materias in codigo_nombre.items():        #codigo=10001 10002                  nombre_materias={juan{4.5:calculo}}  
         for nombre, materias_nota in nombre_materias.items():       #nombre=juan                         materias_nota={calculo: 4.5}     
          for materias,nota in materias_nota.items():                #materias=todas las asignaturas      nota= todas las noats
           if materias==orden53 in materias_nota.keys():
            print(f" Materia: {orden53} \n"f"   Estudiante: {nombre} - Nota: {nota}")
   
     elif orden51==0:
       os.system("cls")
       continue

     else:
      print("Rango no valido, digite un numero entre 0 y 4")
      orden_continuar2= input("\n Presione Enter para continuar")
      if orden_continuar2 == " ":
             os.system("cls")
             continue

 except ValueError:
      print(" Las letras no son caracetres validos para este menu")
      orden_continuar1= input("\n Presione Enter para continuar")
      if orden_continuar1 == " ":
             os.system("cls")
             continue
 except KeyboardInterrupt:
      print("\n Bromista")
      orden_continuar1= input("\n Presione Enter para continuar")
      if orden_continuar1 == " ":
             os.system("cls")
             continue     






#ESTE PRIMERO DE CONSULTA POR CODIGO CREO QUE NO SIRVE PARA NADA Y ES INNECESARIO
    elif orden1 == 3:
        orden15 = input("Consultar código de: ")
        orden15 = orden15.lower()

        for grupo in estudiantes:
            if orden15 in estudiantes[grupo]["nombres"]:
                print("Código de " + orden15 + ":", estudiantes[grupo]["nombres"][orden15]["código"])
                break
        else:
            print(f'El estudiante {orden15} no se encuentra registrado en ningún grupo.Si desea con el indicativo número 5 lo puede realizar. ')

    elif orden1 == 4:
        orden16 = input("¿Qué estudiante desea eliminar de la base de datos? ")
        orden16 = orden16.lower()

        for grupo in estudiantes:
            if orden16 in estudiantes[grupo]["nombres"]:
                estudiantes[grupo]["nombres"].pop(orden16)
                print(f'El estudiante {orden16} ha sido eliminado correctamente.')
                break
        else:
            print(f'El estudiante {orden16} no se encuentra registrado en ningún grupo.')

    elif orden1 == 5:
        orden17 = input("¿Desea registrar a un nuevo estudiante?, escriba si, si así lo desea, o no, si es el caso contrario. ")
        if orden17 == "no":
            continue
        elif orden17 == "si":
            orden18 = input("Digite el nombre que desea registrar: ")
            orden18 = orden18.lower()
            orden19 = input(f'¿Desea registrar a {orden18}? ')
            if orden19 == "no":
                continue
            elif orden19 == "si":
                orden19 = input("¿Cuál es su código? ")
                orden20 = input("¿Cuál es su asignatura 01? ")
                if orden20.isalpha():
                  print("¡Bien hecho! Has ingresado la primera asignatura!")
                else:
                   print("Carácter inválido. Por favor, ingrese solo letras.")
                   break
                orden21 = input(f'¿Cuál es su nota en {orden20}? ')
                orden22 = input("¿Cuál es su asignatura 02? ")
                if orden22.isalpha():
                  print("¡Bien hecho! Has ingresado la segunda asignatura!")
                else:
                   print("Carácter inválido. Por favor, ingrese solo letras.")
                   break
                orden23 = input(f'¿Cuál es su nota en {orden22}? ')
                orden24 = input("¿Cuál es su asignatura 03? ")
                if orden24.isalpha():
                  print("¡Bien hecho! Has ingresado la tercera asignatura!")
                else:
                   print("Carácter inválido. Por favor, ingrese solo letras.")
                   break
                orden25 = input(f'¿Cuál es su nota en {orden24}? ')

                grupo = input("¿A qué grupo pertenece el estudiante? (grupo_01, grupo_02, grupo_03 o grupo_04): ")
                grupo = grupo.lower()

                if grupo in estudiantes:
                  estudiantes[grupo]["nombres"][orden18] = {"código": orden19, "asignatura 01": orden20,
                                                               "nota asignatura 01": orden21,
                                                               "asignatura 02": orden22, "nota asignatura 02": orden23,
                                                               "asignatura 03": orden24, "nota asignatura 03": orden25}
                else:
                   print(f'El grupo {grupo} no existe.')
    elif orden1 == 6:
        break
    else:
        print("Error: Por favor, introduzca un número de opción válido (1-6).")


# __________GUARDAR___________#
 save = json.dumps(js, indent=4)
# print(save)
 archivo = open("cursos.json", "w")
 archivo.write(save)
 archivo.close()














#       estudiantes = {
#     "grupo_01": {
#         "nombres": {
#             "juan castellanos": {"código": 101, "asignatura 01": "cálculo i", "nota asignatura 01": 2.3,
#                                  "asignatura 02": "física", "nota asignatura 02": 4.1,
#                                  "asignatura 03": "programación de computadores", "nota asignatura 03": 3.5},
#             "angel riveros": {"código": 102, "asignatura 01": "cálculo ii", "nota asignatura 01": 3.0,
#                               "asignatura 02": "materiales", "nota asignatura 02": 3.2,
#                               "asignatura 03": "problemas ambientales", "nota asignatura 03": 4.9},
#             "leo ayala": {"código": 103, "asignatura 01": "cálculo iii", "nota asignatura 01": 3.4,
#                           "asignatura 02": "fundamentos de química", "nota asignatura 02": 4.0,
#                           "asignatura 03": "gastronomía i", "nota asignatura 03": 4.7}
#         }
#     },
#     "grupo_02": {
#         "nombres": {
#             "damian montañez": {"código": 201, "asignatura 01": "cálculo iii", "nota asignatura 01": 1.9,
#                                 "asignatura 02": "física", "nota asignatura 02": 3.1,
#                                 "asignatura 03": "dibujo básico", "nota asignatura 03": 3.0},
#             "alejandra rodriguez": {"código": 202, "asignatura 01": "cálculo i", "nota asignatura 01": 3.0,
#                                     "asignatura 02": "fundamentos de química", "nota asignatura 02": 2.8,
#                                     "asignatura 03": "ecología", "nota asignatura 03": 4.3},
#             "veronica lopez": {"código": 203, "asignatura 01": "matemáticas básicas", "nota asignatura 01": 3.9,
#                                "asignatura 02": "álgebra lineal", "nota asignatura 02": 5.0,
#                                "asignatura 03": "gastronomía ii", "nota asignatura 03": 4.0}
#         }
#     },
#     "grupo_03": {
#         "nombres": {
#             "diego camargo": {"código": 301, "asignatura 01": "cálculo ii", "nota asignatura 01": 3.8,
#                                "asignatura 02": "programación de computadores", "nota asignatura 02": 2.1,
#                                "asignatura 03": "problemas ambientales", "nota asignatura 03": 4.8},
#             "paula montenegro": {"código": 302, "asignatura 01": "matemáticas básicas",
#                                   "nota asignatura 01": 5.0, "asignatura 02": "álgebra lineal",
#                                   "nota asignatura 02": 3.9, "asignatura 03": "dibujo básico",
#                                   "nota asignatura 03": 3.0},
#             "dilan velasquez": {"código": 303, "asignatura 01": "cálculo i", "nota asignatura 01": 3.1,
#                                 "asignatura 02": "materiales", "nota asignatura 02": 3.5,
#                                 "asignatura 03": "ecología", "nota asignatura 03": 4.0}
#         }
#     },
#     "grupo_04": {
#         "nombres": {
#             "maria olmos": {"código": 401, "asignatura 01": "cálculo iii", "nota asignatura 01": 2.0,
#                             "asignatura 02": "física", "nota asignatura 02": 2.9,
#                             "asignatura 03": "astronomía i", "nota asignatura 03": 3.4},
#             "francisca suarez": {"código": 402, "asignatura 01": "cálculo i", "nota asignatura 01": 3.4,
#                                  "asignatura 02": "programación de computadores", "nota asignatura 02": 4.9,
#                                  "asignatura 03": "gastronomía i", "nota asignatura 03": 3.7},
#             "valentina gomez": {"código": 403, "asignatura 01": "cálculo i", "nota asignatura 01": 3.2,
#                                 "asignatura 02": "fundamentos de química", "nota asignatura 02": 4.5,
#                                 "asignatura 03": "dibujo básico", "nota asignatura 03": 4.1}
#         }
#     }
# }
'''
