# RAG con LangChain y Pinecone

Este proyecto implementa un sistema de Recuperación Aumentada por Generación (RAG) utilizando LangChain, OpenAI y Pinecone. La aplicación extrae información de Wikipedia, la indexa y permite realizar consultas en lenguaje natural sobre el contenido almacenado.

---

## 📌 Arquitectura del Proyecto

1. **Extracción de Datos**: Se usa `WebBaseLoader` de LangChain para extraer el contenido de la página de Wikipedia sobre la Segunda Guerra Mundial.
2. **Procesamiento del Texto**: Se divide el contenido en fragmentos usando `RecursiveCharacterTextSplitter`.
3. **Vectorización**: Se generan embeddings con `OpenAIEmbeddings`.
4. **Almacenamiento en Pinecone**: Se usa `PineconeVectorStore` para almacenar los embeddings.
5. **Recuperación y Generación de Respuestas**: Se utiliza `RetrievalQA` para responder preguntas en lenguaje natural basadas en los documentos indexados.

![Arquitectura del Proyecto](ruta/a/la/imagen.png)

---

## Dependencias

Antes de ejecutar el código, asegúrate de instalar las siguientes bibliotecas:

```sh
pip install langchain pinecone-client langchain-pinecone langchain-openai bs4
```
```sh
pip install -U langchain-community
```
```sh
%pip install --quiet --upgrade langchain-text-splitters langchain-community langgraph
```

---

## Instalación y Configuración

1. **Clonar el repositorio**
   ```sh
   git clone https://github.com/Mauricio-A-Monroy/AREP-Taller-8-RAC
   ```

2. **Configurar las claves de API**
   - **OpenAI**: Necesitarás una clave API de OpenAI.
   - **Pinecone**: Necesitarás una clave API y un entorno de Pinecone.
   
   Si no las has configurado previamente, el script te pedirá ingresarlas:
   ```python
   os.environ["OPENAI_API_KEY"] = getpass.getpass("Enter your OpenAI API key: ")
   os.environ["PINECONE_API_KEY"] = getpass.getpass("Enter your Pinecone API key: ")
   os.environ["PINECONE_ENV"] = input("Enter your Pinecone environment: ")
   ```

3. **Ejecutar el Script**
   ```sh
   python main.py
   ```

---

## 📊 Ejemplo de Uso

Ejemplo de consulta realizada:
```sh
Query: "Explain to me the World War 2"
```

**Respuesta obtenida:**

```sh
Respuesta: World War II, also known as the Second World War, was a global conflict that lasted from September 1, 1939, to September 2, 1945. It involved two main coalitions: the Allies and the Axis powers. Nearly all of the world's countries participated in the war, which mobilized vast resources in pursuit of total war.

The war was characterized by significant military innovations, including the use of tanks and aircraft, which played major roles in battles and enabled strategic bombing of cities. Notably, it was during this conflict that the first and only nuclear weapons were used in warfare.

World War II was the deadliest conflict in history, resulting in an estimated 70 to 85 million deaths, with more than half of the casualties being civilians. Many people died as a result of genocides, including the Holocaust, as well as from massacres, starvation, and disease.

After the Allied victory, several countries, including Germany, Austria, Japan, and Korea, were occupied, and leaders from Germany and Japan were tried for war crimes. The war had a profound impact on the world, transforming political, economic, and social structures, and establishing the foundation for international relations in the 20th century and beyond.

In the aftermath, the United Nations was created to promote international cooperation and prevent future conflicts, with the victorious great powers—China, France, the Soviet Union, the UK, and the U.S.—becoming permanent members of the UN Security Council. The Soviet Union and the U.S. emerged as rival superpowers, leading to the Cold War. The war also spurred the decolonization of many countries in Africa and Asia, as the influence of European powers waned.
```

**Documentos fuente utilizados:**

```sh
Documentos fuente: [Document(id='bc33d488-028b-43eb-b779-e961ffa62fbf', metadata={'source': 'https://en.wikipedia.org/wiki/World_War_II'}, page_content="ContentsWorld War II\nAsia-Pacific\nMediterranean and Middle East\nOther campaigns\nCoups\nWorld War\xa0II[b] or the Second World War ...
```

![image](https://github.com/user-attachments/assets/f0f80186-2afd-4cd8-834f-3b3dceda2d6f)

---

## 📂 Estructura del Proyecto

```
📦 tu-repo
├── 📜 main.py  # Código principal
├── 📜 README.md  # Documentación
└── 📜 requirements.txt  # Lista de dependencias
```

---

## 📌 Contribuciones

Si deseas mejorar este proyecto, por favor abre un issue o un pull request en el repositorio.

---

## 📜 Licencia

Este proyecto está bajo la licencia MIT.

---

¡Disfruta explorando el poder de RAG con LangChain! 🚀

