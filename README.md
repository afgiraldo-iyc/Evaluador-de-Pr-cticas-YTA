# 📦 Repositorio: Evaluador GPT para la Práctica YTA Plata

Este repositorio contiene todo lo necesario para implementar un **agente GPT evaluador** de ejercicios técnicos del programa **YTA Plata**, enfocados en la localización de averías mecánicas.

---

## 📋 Descripción del proyecto
Este agente está diseñado para analizar ejercicios diligenciados por técnicos o estudiantes en formato texto, Word, Excel o PDF, y evaluarlos **paso a paso** utilizando una rúbrica detallada (incluida en este repositorio).

El sistema puede ser usado como:
- Agente GPT personalizado
- Herramienta de revisión automatizada en plataformas educativas
- Asistente de evaluación en talleres o capacitaciones técnicas

---

## 🔧 Estructura del repositorio

```plaintext
📁 yta-plata-evaluator-gpt/
├── README.md              # Este documento
├── rubrica_yta_plata.md  # Rúbrica completa en formato Markdown
├── prompt_agente_gpt.md  # Prompt para crear el agente GPT evaluador
├── formulario_php/       # Prototipo de formulario digital (opcional)
│   └── ytaplata_form_friendly.php
└── ejemplos/
    ├── ejercicio_resuelto_ejemplo.pdf
    └── resultado_evaluado_ejemplo.md
```

---

## 📊 ¿Qué evalúa el agente?

El agente GPT califica 11 pasos fundamentales del proceso de diagnóstico técnico:

1. Consulta con el cliente (aplica metodología 5W+H)
2. Reproducción del fenómeno
3. Identificación del fenómeno
4. Juicio de si es avería o no (con confirmación al cliente)
5. Diagrama de causa-efecto
6. Determinación de la causa
7. Inspección
8. Identificación final de la causa
9. Reparación y sustitución de piezas
10. Inspección final
11. Explicación al cliente

Cada paso se califica con tres niveles de desempeño: **Excelente**, **Adecuado**, o **Insuficiente**, y se acompaña de observaciones y sugerencias de mejora.

---

## 🧠 Prompt para el agente GPT

El prompt completo para construir el agente inteligente está en el archivo:
```bash
prompt_agente_gpt.md
```
Incluye instrucciones claras, formato de salida esperado y consideraciones para interpretación objetiva del desempeño técnico.

---

## 📘 Rúbrica completa

La rúbrica completa se encuentra en `rubrica_yta_plata.md`, pero también está incluida en este documento para consulta directa.

👉 Por razones de espacio, el contenido completo de la rúbrica se genera a continuación en el mismo formato markdown.

---
### 📝 PASO 1: CONSULTA CON EL CLIENTE (5 minutos)
**Objetivo:** Obtener información clara y estructurada del cliente utilizando la metodología 5W+H.

| Dimensión                | Excelente                                   | Adecuado                                  | Insuficiente                             |
|--------------------------|----------------------------------------------|--------------------------------------------|-------------------------------------------|
| **Qué sucedió**          | Describe con precisión los eventos según cliente | Describe parcialmente el evento            | Registro vago o confuso                   |
| **Quién intervino**       | Identifica correctamente a quien actuó o manipuló | Menciona sin claridad                     | No se recoge esta información             |
| **Cuándo ocurrió**        | Indica momento exacto o aproximado del suceso | Menciona día o contexto general           | No especifica el tiempo                   |
| **Dónde ocurrió**         | Sitio especificado con contexto (ej. lugar, entorno) | Lugar genérico sin detalles        | No se menciona                            |
| **Por qué cree que ocurrió** | Recoge percepción del cliente (hipótesis propia) | Hipótesis vaga o incompleta              | No se considera                           |
| **Cómo ocurrió**         | Explica acción paso a paso antes/durante el fallo | Describe acción parcialmente              | Incompleto o ausente                      |

### 🧪 PASO 2: REPRODUCCIÓN DEL FENÓMENO (15 minutos)
**Objetivo:** Confirmar el fenómeno descrito por el cliente.

| Criterio                  | Excelente                                   | Adecuado                                  | Insuficiente                             |
|--------------------------|----------------------------------------------|--------------------------------------------|-------------------------------------------|
| Preparación y seguridad | Evalúa entorno, herramientas y condiciones   | Algunas verificaciones                     | Sin verificación previa                   |
| Reproducción de la avería| Sigue paso a paso lo relatado por el cliente| Reproduce parcialmente                     | No se intenta o falla sin registro        |
| Observación técnica       | Anota síntomas observados claramente         | Describe parcialmente                      | Registro pobre o inexistente             |
| Preguntas de aclaración | Hace nuevas preguntas si el fenómeno no aparece| Pregunta de forma limitada                | No hay seguimiento verbal al cliente      |
| Conclusión               | Indica si el fenómeno fue confirmado y por qué| Conclusión poco clara                     | No se concluye nada                       |

### 🔍 PASO 3: IDENTIFICACIÓN DEL FENÓMENO (20 minutos)
**Objetivo:** Traducir la queja en un fenómeno técnico concreto.

| Criterio                  | Excelente                                   | Adecuado                                  | Insuficiente                             |
|--------------------------|----------------------------------------------|--------------------------------------------|-------------------------------------------|
| Definición del fenómeno  | Precisa, técnica y comprensible              | General o poco clara                        | Ausente o incorrecta                      |
| Confirmación             | Argumenta por qué sí o no es un fenómeno     | Determina sin mucha base                   | No hay decisión o es ambigua             |
| Uso de datos previos     | Vincula con la información recolectada       | Usa parte de la información               | Ignora información inicial               |
