# Actividad-evaluable-diagramas-de-casos-de-uso


1. Crea el diagrama de uso haciendo uso de platuml, representado los actores y casos de uso que identifiques en los requisitos.

@startuml
' Definición del actor
actor Cliente

' Definición de los casos de uso
usecase "Validar Cliente" as UC1
usecase "Sacar dinero" as UC2
usecase "Transferir" as UC3
usecase "Ingresar dinero" as UC4

' Casos de uso para manejar errores en el retiro
usecase "Error: Saldo insuficiente" as UC5
usecase "Error: Excede límite diario" as UC6

' Relaciones entre el actor y los casos de uso
Cliente --> UC1
Cliente --> UC2
Cliente --> UC3
Cliente --> UC4

' Relación de inclusión: el caso de uso "Sacar dinero" requiere la validación del cliente
UC2 --> UC1 : <<include>>
UC3 --> UC1 : <<include>>
UC4 --> UC1 : <<include>>

' Relaciones de extensión para "Sacar dinero"
UC2 ..> UC5 : <<extend>>
UC2 ..> UC6 : <<extend>>
@enduml

![image](https://github.com/user-attachments/assets/3c00cd6b-a55e-4f50-80ec-e13b044d16f8)

2.Describe, haciendo uso de la plantilla, al menos el caso de uso "Sacar dinero", con las interacciones que tiene entre el actor y el caso de uso.

El actor puede validarse, transferir o ingresar dinero, lo cual le obligaria a validarse. Y para sacar dinero, sino tiene saldo insuficiente o excede el limite diario, se valida tambien

3. Responde a las siguiente pregunta:¿Para qué me sirve tener/realizar un diagrama de casos de uso modelando el sistema que se representa? ¿Qué aporta?

Visualizar interacciones entre actores y el sistema
Identificar funcionalidades clave y errores
Guiar el desarrollo
