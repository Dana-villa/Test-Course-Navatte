Algoritmo TestCourseNevette
    Definir CantidadParticipantes, Participante, Edad, Nivel, Etapa Como Entero
    Definir Nombre, CondicionFisica Como Caracter
    Definir VelocidadFinal, TotalMetros, Vo2Sim, Vo2Max, SumaVo2Sim, SumaVo2Max, PromVo2Sim, PromVo2Max Como Real

    SumaVo2Sim <- 0
    SumaVo2Max <- 0
    PromVo2Sim <- 0
    PromVo2Max <- 0

// Ingreso de la cantidad de participantes
Escribir "Ingrese la cantidad de participantes: "
Leer CantidadParticipantes

// Validación de la cantidad de participantes
Mientras CantidadParticipantes <= 0 Hacer
    Escribir "La cantidad de participantes debe ser mayor a 0. Intente nuevamente: "
    Leer CantidadParticipantes
Fin Mientras

// Bucle para cada participante
Para Participante Desde 1 Hasta CantidadParticipantes Hacer
    
    // Ingreso de datos
    Escribir "Ingrese el Nombre del participante ", Participante, ": "
    Leer Nombre

    Escribir "Ingrese la Edad del participante ", Participante, ": "
    Leer Edad
    // Validación de la edad
    Mientras Edad < 0 Hacer
        Escribir "La edad no puede ser negativa. Intente nuevamente: "
        Leer Edad
    Fin Mientras

    Escribir "Ingrese el Nivel alcanzado por ", Nombre, ": "
    Leer Nivel
    // Validación del nivel
    Mientras Nivel < 1 O Nivel > 10 Hacer
        Escribir "El nivel debe estar entre 1 y 10. Intente nuevamente: "
        Leer Nivel
    Fin Mientras

    Escribir "Ingrese los Shuttle completadas dentro del nivel por ", Nombre, ": "
        Leer Etapas
    // Validar de etapas
    Mientras Etapas < 0 O Etapas > Nivel Hacer
        Escribir "El Shuttle debe estar entre 1 y el nivel. Intente nuevamente: "
        Leer Etapas
    Fin Mientras

    // Cálculo de la velocidad final
    VelocidadFinal = 8 + (0.5 * Nivel)

    // Cálculo del VO₂máx simple
    Vo2Sim = (3.46*VelocidadFinal)+12.2

    // Cálculo del VO₂máx considerando la edad
    Vo2Max = 31.025 + (3.238 * VelocidadFinal) - (3.248 * Edad/100) - (0.1536 *VelocidadFinal* Edad)

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

    PromVo2Sim = (Vo2Sim+SumaVo2Sim)/CantidadParticipantes 
    PromVo2Max = (Vo2Max+ sumaVo2Max)/CantidadParticipantes
    
    // Salida de resultados
    Escribir "RESULTADOS DEL TEST COURSE NAVETTE"
    Escribir "Participante: ", Nombre
    Escribir "Edad: ", Edad, " años"
    Escribir "Nivel alcanzado: ", Nivel
    Escribir "Shuttle alcanzado: ", Etapas
    Escribir "Velocidad final: ", VelocidadFinal, " km/h"
    Escribir "Distancia total: ", TotalMetros, " m"
    Escribir "VO₂Sim: ", Vo2Sim, " ml/kg/min"
    Escribir "VO₂máx estimado: ", Vo2Max, " ml/kg/min"
    Escribir "Condición física: ", CondicionFisica
    Escribir "---------------------------------------------"

Fin Para

    Escribir "Promedio VO₂Sim: ", PromVo2Sim, " ml/kg/min"
    Escribir "Promedio VO₂máx estimado: ", PromVo2Max, " ml/kg/min"

FinAlgoritmo
