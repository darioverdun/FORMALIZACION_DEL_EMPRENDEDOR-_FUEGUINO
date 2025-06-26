# Sistema Experto para la Formalización de Emprendedores en Tierra del Fuego

## Materia  
Desarrollo de Sistemas de Inteligencia Artificial  

**Profesor:** Martín Mirabete  
**Alumno:** Dario Emmanuel Verdun  
**Experto entrevistado:** Contador Público Nacional matriculado  

---

## Título del dominio  
Formalización del emprendedor local en Tierra del Fuego

---

## Objetivo del proyecto

Este proyecto tiene como finalidad el desarrollo de un sistema experto que brinde orientación a emprendedores en el proceso de formalización de sus actividades económicas. Mediante un enfoque basado en reglas, el sistema simula el conocimiento de un profesional en ciencias económicas, ayudando a los usuarios a identificar el régimen fiscal más adecuado según sus características individuales, actividad económica, ingresos estimados y otras variables clave.

El sistema actúa como una herramienta de apoyo al asesoramiento, permitiendo a los emprendedores comprender sus obligaciones fiscales y los pasos necesarios para regularizar su situación.

---

## Contexto del problema

Muchos emprendedores comienzan su actividad de manera informal debido a la falta de información clara sobre los trámites requeridos y los organismos involucrados. Esta informalidad puede limitar su acceso a créditos, generar sanciones involuntarias y dificultar su crecimiento a largo plazo.

Este proyecto busca aportar una solución a esta problemática a través de una herramienta automatizada y accesible.

---

## Relevancia

La implementación de este sistema puede generar un impacto positivo en distintos aspectos:

- Mejora el acceso a información contable y fiscal confiable.
- Reduce errores comunes en la elección del régimen tributario.
- Favorece la inclusión de nuevos emprendimientos en el sistema formal.
- Contribuye al desarrollo económico local mediante la regularización de actividades.

---

## Aporte del Sistema Experto

- Asesoramiento tributario personalizado a través de preguntas y respuestas.
- Simulación del razonamiento de un contador público.
- Sugerencias sobre trámites ante organismos nacionales y provinciales.
- Advertencias sobre incompatibilidades con planes sociales o situaciones laborales.
- Mejora del cumplimiento fiscal inicial y prevención de errores frecuentes.

---

## Representación y Organización del Conocimiento

La estructura del conocimiento se basa en **reglas de producción (si-entonces)**, organizadas modularmente por jurisdicción (nacional y provincial).

### Hechos considerados

- Tipo de persona (física o jurídica)
- Actividad económica
- Ingresos anuales estimados
- Domicilio fiscal
- Situación laboral (relación de dependencia, autónomo)
- Inscripciones previas
- Condición social (beneficios o subsidios)
- Actividades de comercio exterior

### Reglas de ejemplo

SI la persona es física
Y los ingresos son menores al límite del régimen simplificado
ENTONCES sugerir inscripción en el régimen simplificado

SI la persona es jurídica
ENTONCES excluir del régimen simplificado y sugerir régimen general

SI el usuario recibe ayuda social
ENTONCES advertir sobre posibles incompatibilidades


---

## Criterios de Decisión

- Límite de ingresos
- Tipo de actividad (permitida o excluida del régimen simplificado)
- Jurisdicción fiscal (local o multilateral)
- Situación laboral y condición social
- Actividades de importación/exportación
- Ente otros

---

## Estructura del Conocimiento

### Módulo Nacional

- Monotributo vs Régimen General
- Exclusiones del Monotributo
- Obligaciones nacionales: IVA, Ganancias

### Módulo Provincial

- Inscripción en Ingresos Brutos
- Régimen Simplificado vs General
- Convenio Multilateral si corresponde

---

## Método de Inferencia

Se utilizará **encadenamiento hacia adelante**, permitiendo que el sistema evalúe automáticamente los datos proporcionados por el usuario y aplique las reglas correspondientes en cascada, generando una recomendación precisa y personalizada.

---

## Arquitectura del Sistema

- **Base de Conocimiento**: reglas y hechos generales
- **Base de Hechos**: datos ingresados por el usuario
- **Motor de Inferencia**: evalúa condiciones y aplica reglas
- **Interfaz de Usuario**: facilita la interacción con el sistema

---

## 🛠️ Guía de Instalación y Configuración

### Requisitos Previos

- Python 3.10 o superior
- pip (gestor de paquetes de Python)
- Navegador web moderno

### Estructura de Archivos

```
/
├── data/               # Archivos JSON con datos del sistema
│   ├── aref.json      # Datos de AREF
│   ├── categorias.json # Categorías del monotributo
│   └── pagos.json     # Información de pagos
├── static/            # Archivos estáticos
│   └── img/          # Imágenes del sistema
├── templates/         # Plantillas HTML
│   └── index.html    # Interfaz principal
├── src/              # Código fuente
│   ├── api.py        # API principal (FastAPI)
│   └── sistema_experto_5_cop_json.py  # Lógica del sistema
├── arbol de decision/  # Documentación técnica
│   ├── Arbol_Nacional_Arca_Categorización_Emprendedor_Completo.pdf
│   └── Arbol_Nacional_Arca_Categorización_Emprendedor_Simplificado.pdf
└── entregas/         # Documentación adicional
```

### Pasos de Instalación

1. Clonar el repositorio:
```bash
git clone [URL del repositorio]
cd [nombre del repositorio]
```

2. Crear y activar un entorno virtual:
```bash
python -m venv venv
# En Windows:
venv\Scripts\activate
# En Linux/Mac:
source venv/bin/activate
```

3. Instalar las dependencias:
```bash
pip install -r requirements.txt
```

### Ejecución del Sistema

1. Iniciar el servidor:
```bash
uvicorn api:app --reload
```

2. Abrir el navegador y acceder a:
```
http://localhost:8000
```

### Actualización de Datos

El sistema puede actualizar automáticamente los datos de categorías y pagos:
- Acceder a `/actualizar_datos` en la API
- Los datos se guardarán en los archivos JSON correspondientes

### Documentación Adicional

Para más detalles sobre el funcionamiento del sistema, consultar:
- `arbol de decision/Arbol_Nacional_Arca_Categorización_Emprendedor_Completo.pdf`
- `arbol de decision/Arbol_Nacional_Arca_Categorización_Emprendedor_Simplificado.pdf`

---

## Conclusión

Este sistema experto combina inteligencia artificial y conocimiento contable para brindar una herramienta útil y accesible. Su objetivo es reducir la informalidad, promover el cumplimiento fiscal y apoyar el desarrollo de pequeños emprendimientos, especialmente en contextos donde el asesoramiento profesional no está siempre al alcance de todos.

