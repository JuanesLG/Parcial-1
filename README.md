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

estudiantes = {
    "grupo_01": {
        "nombres": {
            "juan castellanos": {"código": 101, "asignatura 01": "cálculo i", "nota asignatura 01": 2.3,
                                 "asignatura 02": "física", "nota asignatura 02": 4.1,
                                 "asignatura 03": "programación de computadores", "nota asignatura 03": 3.5},
            "angel riveros": {"código": 102, "asignatura 01": "cálculo ii", "nota asignatura 01": 3.0,
                              "asignatura 02": "materiales", "nota asignatura 02": 3.2,
                              "asignatura 03": "problemas ambientales", "nota asignatura 03": 4.9},
            "leo ayala": {"código": 103, "asignatura 01": "cálculo iii", "nota asignatura 01": 3.4,
                          "asignatura 02": "fundamentos de química", "nota asignatura 02": 4.0,
                          "asignatura 03": "gastronomía i", "nota asignatura 03": 4.7}
        }
    },
    "grupo_02": {
        "nombres": {
            "damian montañez": {"código": 201, "asignatura 01": "cálculo iii", "nota asignatura 01": 1.9,
                                "asignatura 02": "física", "nota asignatura 02": 3.1,
                                "asignatura 03": "dibujo básico", "nota asignatura 03": 3.0},
            "alejandra rodriguez": {"código": 202, "asignatura 01": "cálculo i", "nota asignatura 01": 3.0,
                                    "asignatura 02": "fundamentos de química", "nota asignatura 02": 2.8,
                                    "asignatura 03": "ecología", "nota asignatura 03": 4.3},
            "veronica lopez": {"código": 203, "asignatura 01": "matemáticas básicas", "nota asignatura 01": 3.9,
                               "asignatura 02": "álgebra lineal", "nota asignatura 02": 5.0,
                               "asignatura 03": "gastronomía ii", "nota asignatura 03": 4.0}
        }
    },
    "grupo_03": {
        "nombres": {
            "diego camargo": {"código": 301, "asignatura 01": "cálculo ii", "nota asignatura 01": 3.8,
                               "asignatura 02": "programación de computadores", "nota asignatura 02": 2.1,
                               "asignatura 03": "problemas ambientales", "nota asignatura 03": 4.8},
            "paula montenegro": {"código": 302, "asignatura 01": "matemáticas básicas",
                                  "nota asignatura 01": 5.0, "asignatura 02": "álgebra lineal",
                                  "nota asignatura 02": 3.9, "asignatura 03": "dibujo básico",
                                  "nota asignatura 03": 3.0},
            "dilan velasquez": {"código": 303, "asignatura 01": "cálculo i", "nota asignatura 01": 3.1,
                                "asignatura 02": "materiales", "nota asignatura 02": 3.5,
                                "asignatura 03": "ecología", "nota asignatura 03": 4.0}
        }
    },
    "grupo_04": {
        "nombres": {
            "maria olmos": {"código": 401, "asignatura 01": "cálculo iii", "nota asignatura 01": 2.0,
                            "asignatura 02": "física", "nota asignatura 02": 2.9,
                            "asignatura 03": "astronomía i", "nota asignatura 03": 3.4},
            "francisca suarez": {"código": 402, "asignatura 01": "cálculo i", "nota asignatura 01": 3.4,
                                 "asignatura 02": "programación de computadores", "nota asignatura 02": 4.9,
                                 "asignatura 03": "gastronomía i", "nota asignatura 03": 3.7},
            "valentina gomez": {"código": 403, "asignatura 01": "cálculo i", "nota asignatura 01": 3.2,
                                "asignatura 02": "fundamentos de química", "nota asignatura 02": 4.5,
                                "asignatura 03": "dibujo básico", "nota asignatura 03": 4.1}
        }
    }
}

while True:
    orden1 = int(input("¿Qué desea consultar? "))

    if orden1 == 1:
        orden2 = input("¿Cuál es el nombre del estudiante? ")
        orden2 = orden2.lower()

        for grupo in estudiantes:
            if orden2 in estudiantes[grupo]["nombres"]:
                print("Grupo:", grupo)
                print("Código:", estudiantes[grupo]["nombres"][orden2]["código"], "\n"
                      , "Asignatura 01:", estudiantes[grupo]["nombres"][orden2]["asignatura 01"], "\n"
                      , "Asignatura 02:", estudiantes[grupo]["nombres"][orden2]["asignatura 02"], "\n"
                      , "Asignatura 03:", estudiantes[grupo]["nombres"][orden2]["asignatura 03"], "\n")
                break
        else:
            print(f'El estudiante {orden2} no se encuentra registrado en ningún grupo.')

    elif orden1 == 2:
        orden14 = input("Asignaturas que cursa el: ")
        orden14 = orden14.lower()

        for grupo in estudiantes:
            if orden14 in estudiantes[grupo]["nombres"]:
                print(estudiantes[grupo]["nombres"][orden14]["asignatura 01"],
                      estudiantes[grupo]["nombres"][orden14]["nota asignatura 01"]
                      , "\n", estudiantes[grupo]["nombres"][orden14]["asignatura 02"],
                      estudiantes[grupo]["nombres"][orden14]["nota asignatura 02"],
                      "\n", estudiantes[grupo]["nombres"][orden14]["asignatura 03"],
                      estudiantes[grupo]["nombres"][orden14]["nota asignatura 03"])
                break
        else:
            print(f'El estudiante {orden14} no se encuentra registrado en ningún grupo. Si desea con el indicativo número 5 lo puede realizar. ')

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
                orden21 = input(f'¿Cuál es su nota en {orden20}? ')
                orden22 = input("¿Cuál es su asignatura 02? ")
                orden23 = input(f'¿Cuál es su nota en {orden22}? ')
                orden24 = input("¿Cuál es su asignatura 03? ")
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

```
