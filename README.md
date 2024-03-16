# Parcial-1

```python
from subprocess import call

call ('cls', shell=True)

print(  ("\t")*8,'''  BIENVENIDO AL SISTEMA DE NOTAS. \n
      
      ''',
      "¿Qué proceso desea realizar?\n"  
      "Utilice los siguientes números para realizar la acción que desee:\n"
      "1 = Información del estudiante\n"
      "2 = Consultar asignaturas del estudiante con su nota\n"
      "3 = Consultar el código de los estudiante\n"
      "4 = Eliminar estudiante\n"
      "5 = Añadir estudiante\n"
      "6 = Finalizar" )


estudiantes={"nombres":
             {"juan":{"codigo":1000," asignatura1":" Calculo I","nota asig1":2.3," asignatura2":"Fisica","nota asig2":4.1," asignatura3":"Programacion de computadores","nota asig3":3.5},
              "angel":{"codigo":2000," asignatura1":" Calculo II","nota asig1":3.0," asignatura2":"Materiales","nota asig2":3.2," asignatura3":"Problemas ambientales","nota asig3":4.9},
              "Leo":{"codigo":3000," asignatura1":" Calculo III", "nota asig1":3.4, " asignatura2":"Mecánica","nota asig2":4.0 ," asignatura3":"Gastronomía", "nota asig3":4.7}}
              }
while True:
 orden1=int(input("¿Qué desea consultar? "))

 if orden1 ==1:     
       orden2=input("¿Cuál es el nombre del estudiante? ")
       orden2=orden2.lower()
       
       if orden2==orden2 and orden2 in estudiantes["nombres"]:
        print("código:",estudiantes["nombres"][orden2]["codigo"], "\n"
              ,"Asignatura No 1:" ,estudiantes["nombres"][orden2][" asignatura1"] ,"\n"
              ,"Asignatura No 2:" ,estudiantes["nombres"][orden2][" asignatura2"] ,"\n"
              ,"Asignatura No 3:" ,estudiantes["nombres"][orden2][" asignatura3"] ,"\n")
        continue
       if orden2!="juan""leo""angel":
        print(f'El estudiante {orden2} no se encuentra registrado, si desea, con el indicativo 5 lo puede realizar. ')
       continue
 if orden1>6:
        print("Error de código, digitelo nuevamente. ")
        continue

    
 if orden1 ==2: 
       orden14=input("Asignaturas que cursa el: ")
       orden14=orden14.lower()
       if orden14==orden14 and orden14 in estudiantes["nombres"]:
        print(estudiantes["nombres"][orden14][" asignatura1"], estudiantes["nombres"][orden14]["nota asig1"] 
           ,"\n",estudiantes["nombres"][orden14][" asignatura2"], estudiantes["nombres"][orden14]["nota asig2"], 
           "\n",estudiantes["nombres"][orden14][" asignatura3"] ,estudiantes["nombres"][orden14]["nota asig3"])
        continue
       if orden14!="juan""leo""angel":
        print(f'El estudiante {orden14} no se enceuntra registrado, si desea, con el indicativo 5 lo puede realizar. ')
        continue
 

 if orden1 ==3:
      orden15=input("Consultar código de: ")
      orden15=orden15.lower()
      if orden15==orden15 and orden15 in estudiantes["nombres"]:
       print(" codigo de " +orden15+ ":", estudiantes["nombres"][orden15]["codigo"])
       continue
      if orden15!="juan""leo""angel":
        print(f'El estudiante {orden15} no se enceuntra registrado, si desea, con el indicativo 5 lo puede realizar. ')
        continue


 if orden1==4:
       orden16=input("¿Qué estudiante desea eliminar de la base de datos? ")
       orden16=orden16.lower()
       estudiantes["nombres"].pop(orden16)
       print(f'El estudiante {orden16} ha sido eliminado correctamente. ')

 if orden1==5:
       orden17=input("¿Desea registrar a un nuevo estudiante?, escriba si, si asi lo desea, o no, si es el caso contrario. ")
       if orden17=="no":
        continue
       if orden17=="si":
        orden18=input("Digite el nombre que desea registrar: ")
       orden19=input(f'¿Desea registrar a {orden18}? ')
       if orden19=="no":
          continue
       if orden17=="si":
           orden19=input("¿Cuál es su código? ")
           orden20=input("¿Cuál es su asignatura No1? ")
           orden21=input(f'¿Cuál es su nota en {orden20}? ')
           orden22=input("¿Cuál es su asignatura No2? ")
           orden23=input(f'¿Cuál es su nota en {orden22}? ')
           orden24=input("¿Cuál es su asignatura No3? ")
           orden25=input(f'¿Cuál es su nota en {orden24}? ')
           estudiantes["nombres"][orden18]={"codigo":orden19, " asignatura1":orden20,"nota asig1":orden21,
                                           " asignatura2":orden22,"nota asig2":orden23,
                                           " asignatura3":orden24,"nota asig3":orden25}
 if orden1==6:
     break



```
