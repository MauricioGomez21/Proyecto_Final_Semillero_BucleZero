# Mesa de Ayuda IA con Agentes Especializados para el Área de Marketing

**Proyecto Final del Semillero de Inteligencia Artificial — Patito S.A.**  
**Grupo:** BucleZero  
**Integrantes:**
- Alvarado Barbosa Damian Alejandro
- Avilez Castro Anthony José
- Gomez Moreira Mauricio Alejandro

---

## 📌 Descripción del Proyecto

El presente proyecto implementa un prototipo funcional de una **Mesa de Ayuda de IA** coordinada por un **Orquestador Multi-agente con Memoria**, diseñado para resolver consultas del Departamento de Marketing de Patito S.A. 

El sistema combina el patrón **RAG (Retrieval-Augmented Generation)**, capacidades **Multimodales (Visión Computacional)** y **Agentes de Acción con Control Estricto**, utilizando el stack oficial de **LangChain** y **Google Gemini**.

---

## 🏗️ Arquitectura y Funcionamiento

El ecosistema está dividido en 5 agentes especializados coordinados por un agente central (Orquestador):

```text
                        +----------------------------+
                        |   Orquestador Principal    |
                        | (create_agent + Memoria)   |
                        +--------------+-------------+
                                       |
     +-----------------+---------------+---------------+-----------------+
     |                 |               |               |                 |
     v                 v               v               v                 v
+----------+     +-----------+   +---------------+  +------------+   +------------+
|  Agente  |     |  Agente   |   |    Agente     |  |   Agente   |   |   Agente   |
|  Marca   |     | Campañas  |   | Cumplimiento  |  | Visión/Img |   |  Registro  |
|  (RAG)   |     |  (RAG)    |   |    (RAG)      |  | (Multimodal|   |  (Acción)  |
+----+-----+     +-----+-----+   +-------+-------+  +-----+------+   +-----+------+
     |                 |                 |                |                |
  ChromaDB          ChromaDB          ChromaDB         Gemini          Archivos
(Base Marca)      (Base Camp.)      (Base Cump.)       Vision           (.txt)

```
## 🚀 Requisitos e Instalación

### Requisitos Previos
* Python 3.10+
* API Key de **Google Gemini**

### Instalación de Librerías
```bash
pip install langchain langchain-google-genai langchain-community langchain-chroma chromadb pillow pandas ipywidgets

```

⚙️ Configuración y Uso
1. Clonar el repositorio y abrir el Jupyter Notebook:
```bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
jupyter notebook

```
2. Configurar la clave de API de Google Gemini:
Dentro del notebook, asigna tu API Key en la celda correspondiente:
```bash
import os
os.environ["GOOGLE_API_KEY"] = "TU_API_KEY_AQUI"

```
##🖥️ Demostración de Interfaz y Uso
Interfaz Interactiva en Jupyter Notebook
El proyecto incluye un Dashboard interactivo diseñado con ipywidgets y CSS estilizado:
```text
+-----------------------------------------------------------------------+
| 🚀 Consola de Asistencia de Marketing - Patito S.A. | ● Sistema en Línea|
+-----------------------------------------------------------------------+
| 🤖 ASISTENTE PATITO S.A.                                             |
| ¡Hola! Soy el orquestador de Marketing. ¿En qué te puedo ayudar hoy?   |
|                                                                       |
| 👤 USUARIO                                                            |
| Quiero lanzar una campaña de email para leads, ¿qué KPIs debo medir?  |
|                                                                       |
| 🤖 ASISTENTE PATITO S.A.                                             |
| De acuerdo a la Guía de Campañas, debes medir: CPL, MQL, CTR y ROAS...|
+-----------------------------------------------------------------------+
| [ Escribe tu consulta aquí...                           ] [ Enviar ]  |
+-----------------------------------------------------------------------+

```
##📂 Estructura del Repositorio
├── Proyecto_Final_Semillero.ipynb   # Notebook principal con todo el código fuente
├── 01_Manual_de_Marca.txt           # Base de conocimiento de Marca
├── 02_Guia_Campanas_KPIs.txt        # Base de conocimiento de Campañas
├── 03_Cumplimiento_Publicitario.txt # Base de conocimiento de Cumplimiento
├── registro_campanas.txt            # Base de datos persistente de solicitudes
└── README.md                        # Documentación del proyecto

