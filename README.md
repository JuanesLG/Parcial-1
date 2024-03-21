# Parcial-1

```python
from subprocess import call

call('cls', shell=True)

print(
    ("\t") * 8,
    '''  BIENVENIDO AL SISTEMA DE NOTAS. \n
    ¿Qué proceso desea realizar?\n  
    Utilice los siguientes números para realizar la acción que desee:\n
    1 = Información del estudiante\n
    2 = Consultar asignaturas del estudiante con su nota\n
    3 = Consultar el código de los estudiantes\n
    4 = Eliminar estudiante\n
    5 = Añadir estudiante\n
    6 = Finalizar'''
)

estudiantes={
    "G01": {
        "JUAN CASTELLANOS PEREZ": {
            "Asignaturas": 
                {
                    4.5: "CALCULO 1",
                    4.1: "FISICA 1",
                    3.1: "PROGRAMACION DE COMPUTADORES"
                }
            
        },
        "ANGEL RIVEROS AMAYA": {
            "Asignaturas": 
                {
                    4.1:"CALCULO 2" ,
                    3.8:"ECOLOGIA" ,
                    2.9: "FUNDAMENTOS DE QUIMICA"
                }
            
        },
        "LEO AYALA VERGARA": {
            "Asignaturas": 
                {
                    3.8: "MATERIALES",
                    4.0: "ASTRONOMIA 1",
                    3.0: "CALCULO 2"
                }
            
        }
    },
    "G02": {
        "DAMIAN MONTA\u00c3\u2018AZ ROMERO": {
            "Asignaturas": 
                {
                   2.9: "CALCULO 3",
                   3.1 : "PROGRAMACION DE COMPUTADORES",
                   4.0: "DIBUJO BASICO"
                }
            
        },
        "ALEJANDRA RODRIGUEZ PALACIO": {
             "Asignaturas": 
                {
                    5.0:"MATEMATICAS BASICAS",
                    4.5:"FISICA" ,
                    3.0:"ASTRONOMIA" 
                }
            
        },
       "VERONICA LOPEZ BENAVIDES": {
            "Asignaturas": 
                {
                    1.6:"ALGEBRA LINEAL",
                    3.0:"CALCULO 2" ,
                    4.0:"FISICA" 
                }
            
        }
    }
}

while True:
 orden0 = int(input("Selccione la accion que desea realizar, solo los numeros son validos: "))

 if orden0 == 1:
     os.system("cls")
     menu1 = print("¿QUÉ DESEA CONSULTAR?", "\n", "\n",
                   "1. Consulta completa", "\n",
                   "2. Consultar asignatuars del curso", "\n",
                   "3. Consultar notas por grupo", "\n",
                   "4. Consultar notas por asignatura", "\n",
                   "5. SALIR", "\n")
     orden51= int(input("Seleccione la accion que desea realizar: "))
     if orden51 == 1:
      orden52 = input("¿Cual es el nombre del estudiante?")
      orden52 = orden52.upper()
      os.system("cls")
      for k,v in js.items():                              #grupo=G01, G02         codigo_nombre=100001:{juan:{}}
       for grupo, codigo in v.items():                    #codigo=10001           nombre_asignaturas={juan}calculo   
        for codigo1, nombres in codigo.items():           #nombres=Juan           materia_nota={calculo: 4.2}
         if orden52 in codigo1:
          print(f"Estudiante: {orden52}")
          for materia, nota in nombres.items():           #materia=calculo        nota=3.0 4.5
           if orden52 in codigo1: 
            print(f"Asignatura: {materia} - nota: {nota}")

           
     elif orden51 == 2: 
       orden53 = input("Digite el grupo que desea consultar de la siguiente manedera: G01, G02, G03 etc")
       prueba = js[orden53]   #dentro de grupo 1
       print(" \n"f"Grupo {orden53}: \n")
       for codigo, nombres in prueba.items():
        for llamar, asignaturas in nombres.items():
         for apellidos, asig_not in asignaturas.items():
          print( f"Asignatura 1: {apellidos}")

     elif orden51 == 3:
      orden54=input("Digite el grupo que desea consultar, de la siguiente manera: G01, G02, G03 etc")
      for codigo, nombre_asig in js[orden54].items():           #codigo=10001                nombre_asig={'JUAN CASTELLANOS PEREZ': {'CALCULO 1': 4.5,    
       for nombre, asignatura in nombre_asig.items():        #nombre=juan           asignatura={'CALCULO 1': 4.5, 'FISICA 1': 4.1,
        print(f" Estudiante: {nombre}\n Codigo: {codigo}")
        for materia, promedio in asignatura.items():         #materia=calculo 1       promedio=4.5 3.6 2.0                         
         print(f"     Asignatura 1: {materia} - Nota: {promedio}")


     elif orden51 == 4:
       orden53=input("Digite la asignatura que desea consultar")
       for grupo,codigo_nombre in js.items():                         #grupo=g01 g02                       codigo_nombre=codigo{juan{...}}
        for codigo, nombre_materias in codigo_nombre.items():        #codigo=10001 10002                  nombre_materias={juan{4.5:calculo}}  
         for nombre, materias_nota in nombre_materias.items():       #nombre=juan                         materias_nota={calculo: 4.5}     
          for materias,nota in materias_nota.items():                #materias=todas las asignaturas      nota= todas las noats
           if materias==orden53 in materias_nota.keys():
            print(f" Materia: {orden53} \n"f"   Estudiante: {nombre} - Nota: {nota}")

     else:
       continue      






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
