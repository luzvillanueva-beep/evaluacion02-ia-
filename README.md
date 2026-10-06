# Evaluacion 02: Laboratorio de Prompt Engineering

![ChatGPT](https://img.shields.io/badge/ChatGPT-4o-74aa9c?style=for-the-badge&logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-3.5_Sonnet-d97706?style=for-the-badge&logo=anthropic&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-Flash-8e44ad?style=for-the-badge&logo=googlegemini&logoColor=white)
![Estado](https://img.shields.io/badge/Estado-Completado-success?style=for-the-badge)

**Estudiante:** Luz Clarita Villanueva Mauricio  
**Programa:** Diseño y Desarrollo de Software  
**Institución:** Tecsup - Trujillo  

---

## Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Flujo de Trabajo](#flujo-de-trabajo)
- [Pregunta 1: Clasificación de Incidentes (ChatGPT)](#pregunta-1-clasificación-de-incidentes-chatgpt)
- [Pregunta 2: Optimización de Costos AWS (Claude)](#pregunta-2-optimización-de-costos-aws-claude)
- [Pregunta 3: Extracción JSON (Google Gemini)](#pregunta-3-extracción-json-google-gemini)
- [Lista de Entregables](#lista-de-entregables)
- [Tabla Comparativa de IAs](#tabla-comparativa-de-ias)
- [Conclusión Comparativa](#conclusión-comparativa)

---

## Descripción del Proyecto

Aplicación y evaluación práctica de técnicas de **Prompt Engineering** (Zero-Shot, Few-Shot, Role Prompting y Prompts Estructurados con Autocrítica) comparando los resultados de ChatGPT, Claude y Gemini en tareas informáticas reales.

---

## Flujo de Trabajo

```mermaid
graph TD
    A[Caso o Problema Técnico] --> B[Diseño del Prompt]
    B --> C[Ejecución en IA]
    C --> D[Verificación y Autocrítica]
    D --> E[Documentación en Markdown y GitHub]
---
## Pregunta 1: Clasificación de Incidentes (ChatGPT)
Prompt Inicial (Vago)

```TEX
Clasifica este problema de soporte: No puedo entrar al sistema y sale un error raro.
````
---
## Prompt Final (Estructurado / Role Play)
---
Actúa como un Ingeniero Senior de Mesa de Ayuda IT. Analiza el siguiente incidente y devuelve la respuesta únicamente en formato JSON con la siguiente estructura:
- id_incidente
- categoria
- prioridad (Alta, Media, Baja)
- causa_probable
- pasos_resolucion (lista de pasos)

Incidente: "No puedo entrar al sistema y sale un error 500 en el login."
```
{
  "id_incidente": "INC-001",
  "categoria": "Autenticación / Servidor",
  "prioridad": "Alta",
  "causa_probable": "Error interno del servidor (Internal Server Error 500) en el servicio de autenticación.",
  "pasos_resolucion": [
    "Revisar logs del servidor web y base de datos.",
    "Reiniciar el servicio de login.",
    "Validar conectividad entre la API y la BD."
  ]
}
```
###Pregunta 2: Optimización de Costos AWS (Claude)
Prompt Inicial (Directo)

## Respuesta recibida:
```
Costo total estimado mensual: $516.10 USD aprox.
````
## 2. Prompt Final (Estructurado con Autocrítica)
```
Actúa como un Arquitecto de Soluciones Cloud especializado en FinOps AWS. 

Tu tarea es calcular el costo mensual (720 horas) del siguiente escenario y proponer la opción de optimización indicada.

Paso 1: Calcula el costo actual por componente (Servidores EC2 y BD RDS).
Paso 2: Suma el costo mensual total sin descuento.
Paso 3: Aplica un descuento del 20% ÚNICAMENTE a los servidores EC2.
Paso 4: Realiza una autocrítica paso a paso verificando los cálculos aritméticos antes de dar la respuesta final.

Infraestructura:
- 4 instancias EC2 t3.large a $0.0832/hora.
- 2 instancias RDS db.m5.large a $0.192/hora.
```
````
Calcula el costo total de esta infraestructura AWS: 4 servidores t3.large a 0.0832 USD/hora cada uno (24/7) y 2 bases de datos db.m5.large a 0.192 USD/hora cada una (24/7). Aplica un 20% de descuento a las instancias.
```
```
Respuesta recibida:Paso 1 (EC2): $4 \times 0.0832 \times 720 = \$239.616$Paso 1 (RDS): $2 \times 0.1920 \times 720 = \$276.480$Paso 2 (Total sin descuento): $\$239.616 + \$276.480 = \$516.096$Paso 3 (Descuento 20% en EC2): $\$239.616 \times 0.80 = \$191.6928$Paso 4 (Autocrítica y Total Final): RDS mantiene su costo $(\$276.48)$. Total optimizado: $\$191.6928 + \$276.48 = \$468.1728 \approx \$468.17$ USD.
```
---
## Pregunta 3: Extracción JSON (Google Gemini)
Prompt Inicial (Zero-Shot)

````
Extrae los datos de los correos en un JSON con nombre, puesto, anios_experiencia, tecnologias, disponibilidad y pretension_soles.
````
### Prompt Final (Few-Shot)
---
````
Actúa como un extractor de datos estructurados. Convierte la información de postulantes a JSON respetando el siguiente esquema:
- nombre
- puesto
- anios_experiencia (número)
- tecnologias (lista)
- disponibilidad
- pretension_soles (número o null)

Ejemplo:
Correo: "Soy Juan Perez, Desarrollador Backend con 2 años en Python. Disponible ya."
JSON: {"nombre": "Juan Perez", "puesto": "Desarrollador Backend", "anios_experiencia": 2, "tecnologias": ["Python"], "disponibilidad": "Inmediata", "pretension_soles": null}

Correos a procesar:
[Lista de correos reales]
`````

## Tabla Comparativa de IAs

| Criterio | ChatGPT | Claude | IA libre: Google Gemini |
| :--- | :---: | :---: | :---: |
| Calidad de la respuesta (1-5) | 5 | 5 | 5 |
| Precisión (aciertos / total verificado) | 3/3 | 3/3 | 3/3 |
| Precio del plan o de la API (US$) | Gratis / $20 mes | Gratis / $20 mes | Gratis |
| N.° de prompts hasta un resultado útil | 2 | 2 | 2 |
| Tokens aproximados y costo estimado ||

## Conclusión
````
En conclusión, al comparar las tres herramientas de Inteligencia Artificial Generativa: ChatGPT, Claude y Google Gemini, pude notar que cada una tiene diferentes fortalezas y que la calidad de las respuestas también depende mucho de la forma en que se realiza el prompt. Durante esta actividad aprendí que mientras más claras y específicas sean las indicaciones, mejores resultados se pueden obtener.

También pude observar que ChatGPT fue muy útil para organizar respuestas y seguir diferentes roles, mientras que Claude destacó en ejercicios donde era necesario razonar paso a paso y revisar los resultados. Por otro lado, Google Gemini me pareció bastante práctico para extraer información y reconocer datos de manera rápida.

Finalmente, entendí que las técnicas de Prompt Engineering, como Few-Shot y la autocrítica, ayudan a reducir errores y obtener respuestas más precisas y ordenadas. Esta actividad me permitió conocer mejor cómo utilizar estas herramientas de IA y cómo puedo aplicarlas en diferentes actividades relacionadas con el desarrollo de software.
