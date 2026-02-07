# 🧠 Stussy AI – Intelligent E-commerce Assistant

Stussy AI es un asistente inteligente para comercio electrónico que permite 🔍 **buscar**, 🧠 **recomendar** y 💬 **interactuar** con un catálogo de productos mediante **lenguaje natural**.  
El sistema combina técnicas de **recomendación por contenido**, **búsqueda semántica** y un **asistente conversacional**, integrándose tanto en una interfaz web como en **ChatGPT mediante Actions**.

🎯 El objetivo del proyecto es demostrar cómo la **Inteligencia Artificial aplicada al NLP** puede mejorar la experiencia de compra digital, reduciendo el tiempo de búsqueda y ofreciendo recomendaciones personalizadas y coherentes.

---

## 🚀 Funcionalidades principales

- 🔍 Búsqueda de productos mediante lenguaje natural  
- 🧠 Recomendación inteligente basada en:
  - TF-IDF  
  - Similaridad coseno  
  - Búsqueda semántica con embeddings (opcional)  
- 💬 Asistente conversacional con mantenimiento de contexto  
- 🛒 Filtrado por categoría, color, precio y stock  
- 📊 Registro de eventos y consultas para análisis  
- 🤖 Integración con ChatGPT mediante API (Actions)  

---

## 🧩 Arquitectura de la solución

El proyecto sigue una **arquitectura modular cliente-servidor**, compuesta por:

- ⚙️ **Backend (FastAPI – Python)**
  - Motor de recomendación  
  - Motor semántico  
  - Lógica de chat y filtrado  
- 🎨 **Frontend (HTML, CSS, JavaScript)**
  - Visualización del catálogo  
  - Interacción con la API  
- 🧠 **IA y NLP**
  - TF-IDF y cosine similarity  
  - Embeddings semánticos (FAISS)  
- 🌐 **Integración externa**
  - ChatGPT (Actions + OpenAPI)  
  - Exposición pública mediante ngrok (entorno de desarrollo)  

---

## 🛠️ Tecnologías utilizadas

- 🐍 Python  
- ⚡ FastAPI  
- 📊 Pandas  
- 🧠 Scikit-learn (TF-IDF, cosine similarity)  
- 🔎 Embeddings semánticos (FAISS)  
- 🎨 HTML, CSS, JavaScript  
- 🧩 Jinja2  
- 📘 OpenAPI 3.1  
- 🤖 ChatGPT Actions  
- 🌍 ngrok  

---

## ⚙️ Instalación y ejecución

### 📥 Clonar el repositorio
git clone https://github.com/tu-usuario/stussy-ai.git
cd stussy-ai

### 📦 Instalar dependencias
pip install -r requirements.txt

### ▶️ Ejecutar el servidor
uvicorn main:app --reload

La aplicación estará disponible en:
- 🌐 http://localhost:8000
- 📘 Documentación de la API: http://localhost:8000/docs

---

## 🤖 Integración con ChatGPT

El backend del proyecto se expone mediante una **API REST documentada con OpenAPI**, lo que permite su consumo tanto desde una interfaz web propia como desde agentes externos, en este caso **ChatGPT**.

Durante la fase de desarrollo, para permitir que ChatGPT pudiera acceder al backend local, se utilizó **ngrok**, herramienta que expone el servidor local mediante una **URL pública temporal**. Esta URL se emplea dentro de la configuración del agente de ChatGPT para realizar llamadas directas a la API.

La integración con ChatGPT se realiza mediante **Actions**, importando el esquema OpenAPI generado por FastAPI y definiendo las acciones disponibles (búsqueda, recomendación, chat). De este modo, el asistente puede llamar directamente a la API y generar respuestas utilizando **únicamente los datos devueltos por el sistema**, sin inventar información.

En un entorno de producción, esta integración se realizaría mediante un **despliegue cloud**, eliminando la necesidad de ngrok y mejorando la seguridad, estabilidad y escalabilidad del sistema.

---

## 🔄 Flujo de funcionamiento

1. 👤 El usuario introduce una consulta (desde la web o desde ChatGPT).
2. 🧠 El sistema interpreta la intención del usuario y los filtros implícitos.
3. 🔍 Se aplica búsqueda semántica o recomendación por contenido.
4. 🛒 Los resultados se filtran y ordenan según precio, categoría y stock.
5. 💬 Se devuelve una respuesta coherente, contextualizada y consistente.

---

## 🧪 Estado del proyecto

El proyecto se encuentra en **estado de beta funcional**, cumpliendo los objetivos definidos en el anteproyecto.  
La arquitectura es **estable, modular y preparada para futuras ampliaciones**, tanto a nivel de funcionalidades como de integración cloud.
