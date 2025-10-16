Algoritmo TestCourseNevette
    Definir CantidadParticipantes, Participante, Edad, Nivel, Etapa Como Entero
    Definir Nombre, CondicionFisica Como Caracter
    Definir VelocidadFinal, TotalMetros, Vo2Max, Como Real
    

    // Ingreso de la cantidad de participantes
    Escribir "Ingrese la cantidad de participantes: "
    Leer CantidadParticipantes

    // Bucle para cada participante
    Para Participante Desde 1 Hasta CantidadParticipantes Hacer
        
        // Ingreso de datos
        Escribir "Ingrese el Nombre del participante ", Participante, ": "
        Leer Nombre

        Escribir "Ingrese la Edad del participante ", Participante, ": "
        Leer Edad

        Escribir "Ingrese el Nivel alcanzado por ", Nombre, ": "
        Leer Nivel

        Escribir "Ingrese las Etapas completadas dentro del nivel por ", Nombre, ": "
        Leer Etapas

        // Cálculo de la velocidad final
        VelocidadFinal = 8 + (0.5 * (Nivel - 1))

        // Cálculo de la distancia total recorrida
        TotalMetros = (Nivel - 1) * 7 * 20 + (Etapas * 20)

        // Cálculo del VO₂máx estimado
        Vo2Max = 31.025 + (3.238 * VelocidadFinal) - (3.248 * Edad / 100) - (0.1536 * Edad)

        // Evaluación de la condición física
        Si Vo2Max >= 50 Entonces
            CondicionFisica = "Excelente"
        Sino
            Si Vo2Max >= 40 Entonces
                CondicionFisica = "Buena"
            Sino
                Si Vo2Max >= 30 Entonces
                    CondicionFisica = "Regular"
                Sino
                    CondicionFisica = "Baja"
                Fin Si
            Fin Si
        Fin Si

        // Salida de resultados
        Escribir "RESULTADOS DEL TEST COURSE NAVETTE"
        Escribir "Participante: ", Nombre
        Escribir "Edad: ", Edad, " años"
        Escribir "Nivel alcanzado: ", Nivel
        Escribir "Etapas: ", Etapas
        Escribir "Velocidad final: ", VelocidadFinal, " km/h"
        Escribir "Distancia total: ", TotalMetros, " m"
        Escribir "VO₂máx estimado: ", Vo2Max, " ml/kg/min"
        Escribir "Condición física: ", CondicionFisica
        Escribir "---------------------------------------------"

    Fin Para

FinAlgoritmo
