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


## 🚀 Requisitos e Instalación

### Requisitos Previos
* Python 3.10+
* API Key de **Google Gemini**

### Instalación de Librerías
```bash
pip install langchain langchain-google-genai langchain-community langchain-chroma chromadb pillow pandas ipywidgets
