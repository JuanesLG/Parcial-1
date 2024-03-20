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
    orden1 = int(input("¿Qué desea consultar? "))

    if orden1 == 1:
        orden2 = int(input('''   Seleccione una opción de consulta
       1 = Consulta completa
       2 = Consultar asignaturas del grupo
       3 = Consultar notas por grupo
       4 = Consultar notas por asignatura'''))
        if orden2 == 1:
            orden50 = input("¿cual es el nombre del estudiante?")
            orden50=orden50.upper()
            
            
            for k,v in estudiantes.items():    #k=grupo     v=juan{asignatura{4.5}}
             for estudiante, asignaturas in v.items():   #estudiante=Juan     asignaturas=asignatura{4.5. CALCULO}
              for notas, materias in asignaturas.items():    #notas="Asignaturas"      #materias=4.5:calculo
               if orden50 in estudiante:
                print(f"Estudiante: {orden50} \n") 
                for notas1, materias1 in materias.items():  #notas1=4.5 2.0          #materias1=calculo, fisica
                 if orden50 in estudiante:     
                  print(f" Asignatura: {materias1} - Nota: {notas1}")
             break
            else:
             print(f'El estudiante {orden50} no se encuentra registrado en ningún grupo. Si desea agregarlo puede digitar el número 5. ')

        elif orden2==2:
            orden51 = input("Digite el grupo que desea consultar de la siguiente manedera: G01, G02, G03 etc")
            asignaturas_grupo_01 = estudiantes[orden51]
            asignaturas = []
            for materias in asignaturas_grupo_01.values():
             asignaturas.extend(materias['Asignaturas'].values())
             asignaturas_unicas = list(set(asignaturas))
            print("\n""Las asignaturas que estan cursando los estudiantes del Grupo 1 son:"+("\n")*2+"-\n- \t".join(asignaturas_unicas).lower()) #el primero no sale con guion y el guion sale alejado de la materias
        elif orden2==3:
            orden52=input("Digite el grupo que desea consultar, de la siguiente manera: G01, G02, G03 etc")
            for key, valor in estudiantes[orden52].items():
                print(f"Estudiante: {key}")
                for nota, asignatura in valor["Asignaturas"].items():
                 print(f"Asignatura 1: {asignatura} - Nota: {nota}")
            
        elif orden2==4:
         orden53=input("Digite la asignatura que desea consultar")
         for k,v in estudiantes.items(): #k=grupo    v=nombre{asignatura{...}}
          for estudiante, asignaturas in v.items():     #estudiante=nombre  asignatura={asignatura{4.5:calculo}}
           for notas, materias in asignaturas.items():    #notas="asignaturas"     materias={4.5: calculo}
            for numero,letras in materias.items():         #numeros=todas las notas     letras= todas las asignaturas 
             if letras==orden53 in materias.values():
              print(f"Estudiante: {estudiante} - Nota: {numero}")





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
