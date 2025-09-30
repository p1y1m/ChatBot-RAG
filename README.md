# Chatbot RAG – Pedro Yáñez

Este proyecto implementa un **chatbot basado en Retrieval Augmented Generation (RAG)** que permite consultar de manera inteligente un corpus documental extenso. Como caso de prueba, se utilizó el libro *Handbook of Conflict Resolution* (959 páginas).

## Objetivo
Construir un sistema de consulta que:
- Transforme documentos extensos en un corpus vectorizado.
- Permita búsquedas semánticas mediante embeddings.
- Genere respuestas contextualizadas con base en la información del corpus.

## Descripción del Funcionamiento
1. Conversión del PDF original en múltiples archivos `.txt` de menor tamaño (300 líneas cada uno), debido a restricciones de tokens.
2. Carga incremental de los archivos y vectorización controlada (máximo 2 archivos por minuto con `sleep(30)`).
3. Indexación del corpus con embeddings mediante **LangChain** y **OpenAI**.
4. Ejecución de queries sobre el corpus:
   - Antes de cargar el corpus: respuestas vacías (“I don’t know”).
   - Después de cargar y vectorizar: respuestas correctas basadas en el contenido.

## Tecnologías Utilizadas
- Python 3
- LangChain
- OpenAI Embeddings
- Google Colab (para almacenamiento y ejecución)
- Vector stores para recuperación semántica

## Ejemplo
- Pregunta: *Who is Ellen Raider?*  
  - Respuesta antes de cargar el corpus: *I don’t know.*  
  - Respuesta después de cargar el corpus: Descripción obtenida desde el texto vectorizado.  

## Repositorio
Este notebook muestra un caso práctico de **RAG aplicado a un corpus académico** para construir chatbots especializados en dominios de conocimiento.
