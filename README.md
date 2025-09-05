# 🚀 Ejemplos de Retrieval-Augmented Generation (RAG) con Gemini

Este repositorio reúne **demos educativas y prácticas** sobre técnicas de **Retrieval-Augmented Generation (RAG)**, utilizando **Google Gemini** como modelo generativo principal.  

El material está diseñado para **estudiantes y entusiastas de la IA**, con implementaciones que van desde lo más básico hasta versiones avanzadas con grafos y múltiples recuperadores.  

---

## 📌 ¿Qué es RAG?

**Retrieval-Augmented Generation (RAG)** es una técnica que combina:  

1. **Recuperación de información** → Buscar datos relevantes en fuentes externas (bases vectoriales, grafos, buscadores, etc.).  
2. **Generación de lenguaje natural (LLM)** → Un modelo generativo responde usando tanto la información recuperada como su conocimiento interno.  

De esta manera:  
- El modelo **no se limita a lo que fue entrenado**.  
- Se pueden dar **respuestas más precisas y actualizadas**.  
- Es posible integrar conocimiento especializado (documentos, bases de datos, grafos).  

👉 En este repositorio mostramos **tres enfoques distintos de RAG** para entender sus fortalezas.  

---

## 🛠️ Preparación del entorno

Para correr los ejemplos en **Google Colab**, solo necesitas:  

- Una cuenta en [Google AI Studio](https://aistudio.google.com/) para obtener tu **API Key de Gemini**.  
- (Opcional) Una cuenta en [Neo4j AuraDB](https://neo4j.com/cloud/aura/) si quieres probar el ejemplo avanzado con grafos (**GraphRAG**).  

> 🔑 Si las credenciales ya configuradas en el código no funcionan, cada estudiante puede usar las suyas propias.  

---

## 📂 Estructura del repositorio
📦 RAG-Gemini-Examples
┣ 📂 Docuemntos # Documentos de prueba (.txt)
┃ ┣ cuantica.txt
┃ ┣ historia_colombia.txt
┃ ┣ historia_internet.txt
┃ ┣ innovadores.txt
┣ 📓 Tecnicas_De_Rag # Ejemplos en Google Colab
┣ README.md # Este archivo


---

## 📖 Ejemplos incluidos

### 1️⃣ BasicRAG (RAG con embeddings y vector DB)

En este ejemplo se:  
- Divide un documento en **chunks**.  
- Se crean **embeddings** con `sentence-transformers`.  
- Se almacenan en **ChromaDB**.  
- Gemini responde usando el contexto recuperado.  

📌 Ideal para **introducir el concepto de RAG**.  

**Ejemplo de uso:**  
- Subir `historia_colombia.txt`.  
- Preguntar: *“¿Qué evento marcó el inicio de la Independencia de Colombia?”*.  

<img width="761" height="360" alt="image" src="https://github.com/user-attachments/assets/098383ff-e731-4cdf-95e2-cbf8c4de1cd2" />


---

### 2️⃣ GraphRAG (RAG con grafos en Neo4j)

Aquí se da un paso más:  
- Gemini extrae **triples semánticos (sujeto, relación, objeto)** de un documento.  
- Se insertan en un **grafo de conocimiento en Neo4j**.  
- Se pueden hacer consultas con **Cypher**.  
- Gemini utiliza los resultados del grafo para dar respuestas con contexto.  

📌 Ideal para explorar **relaciones complejas entre entidades**.  

**Ejemplo de uso:**  
- Subir `innovadores.txt`.  
- Ejecutar una consulta Cypher:  
  ```
  cypher
  MATCH (p:Entidad)-[r:RELACION]->(c:Entidad)
  RETURN p.name, r.tipo, c.name
  ```
- Preguntar: “¿Cuáles son las empresas fundadas por Elon Musk y Steve Jobs?”.

<img width="1206" height="544" alt="image" src="https://github.com/user-attachments/assets/59728de0-ae88-41e5-adad-a8701da108ea" />

---

## 3️⃣ FusionRAG (Combinación de recuperadores)

Este ejemplo combina dos métodos de recuperación:

1. Vector search (con embeddings + ChromaDB).

2. BM25 (recuperador basado en palabras clave).

Luego, los resultados se fusionan para enriquecer el contexto.
Gemini responde con información más robusta.

📌 Ideal para mostrar cómo se pueden mejorar las respuestas al combinar técnicas.

**Ejemplo de uso:**

- Subir historia_internet.txt.

- Preguntar: “¿Quién desarrolló la primera versión de la World Wide Web y en qué año?”.

<img width="320" height="320" alt="image" src="https://github.com/user-attachments/assets/776558b6-1d93-4e14-87dc-75c0b80baed2" />


---

## 💡 Documentos incluidos

Se incluyen algunos documentos .txt para pruebas:

- cuantica.txt → Introducción a la física cuántica.

- historia_colombia.txt → Principales hechos de la independencia de Colombia.

- historia_internet.txt → Desarrollo de internet y la World Wide Web.

- innovadores.txt → Biografías de figuras como Steve Jobs, Elon Musk, etc.

Los estudiantes también pueden subir sus propios documentos para experimentar.

---

##⚡ Cómo usar los ejemplos

1. Abrir el notebook correspondiente en Google Colab.

2. Subir un documento .txt desde tu PC.

3. Modificar la pregunta en el código (comentado como # 👉 Cambia tu consulta aquí).

4. Ejecutar y analizar la respuesta de Gemini.

---

## 🎯 Objetivo educativo

Estos ejemplos permiten a los estudiantes:

- Comprender qué es RAG y por qué es útil.

- Explorar diferentes formas de recuperación de información.

- Ver cómo los LLM se pueden enriquecer con datos externos.

- Experimentar con sus propios documentos y consultas.

---
