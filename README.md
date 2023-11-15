# Chatgpt-en-Python
A continuacion se presenta varios pasos para usar Chatgpt en Python.
## Por medio de codigo en Python, Jupyter Notebook o VSCode
Se hablara de la version de openai 1.2.4 y de los pasos que se toman en la pagina de [openai](https://platform.openai.com/docs/quickstart?context=python). Si no se tiene una cuenta sera necesario crear una en la pagina de [openai](https://openai.com/). Para verificar la version utilice: 
```python
import openai
print(openai.__version__)
```
Se asumira que ya tiene instalado Python y esta utilizando el sistema opeativo de Windows.
1. El primer paso es instalar la bibloteca de openai en alguna terminal con la siguiente linea de comando:
```
pip install openai
```
o actualizar la libreria con:
```
pip install --upgrade openai
```
2. Luego es obtener una API KEY la cual puede ser encontra en la pagina de [openai](https://platform.openai.com/api-keys) dando click en `+ Create new secret key`, despues de darle nombre al API dar click a `Create secret key`. Copiar y pegar la llave en algun lugar porque a continuacion se ocupara.
3. Luego utilizar la linea de codigo siguiente en Python:
```python
import os
os.environ['OPENAI_API_KEY'] = 'Tu llave aqui'
```
Remplazar `'Tu llave aqui'` con tu llave que guardaste en el paso 2. Esto fija tu llave API KEY cuando utilices Chatgpt en Python.
4. Por ultimo utiliza este codigo y correlo:
```python
from openai import OpenAI
client = OpenAI()

response = client.chat.completions.create(
  model="gpt-3.5-turbo",
  messages=[{"role": "system", "content": "You will be provided with statements, and your task is to convert them to standard English."},
            {"role": "user", "content": "She no went to the market."}
           ],
  temperature=0,
  max_tokens=256
)
print(response.choices[0].message)
```
La respuesta tiene que ser **She did not go to the market**
Una breve descripcion del codigo anterior, en *model* puede variar a la cantidad de modelos que tiene disponible en [openai](https://platform.openai.com/docs/models). En *messages* se le provee al modelo su rol y el contenido que el usuario desee. La *temperature* va de 0 a 1 y cuando es 0 el modelo responde sin rodeos la actividad y pregunta, y con 1 abunda o profundiza mas con la respuesta. Y *max_tokens* es la cantidad maxima de tokens a usar, por ejemplo: Hello, how are you? contiene 6 tokens.
## Extensiones en VSCode
En este caso VSCode tiene una forma mas sencilla de utlizar Chatgpt, por lo regular depende de la extension a descargar pero los pasos a utilizar por lo regular son 2.
1. Estando en VSCode, la barra vertical de la parte izqquierda, esta un opcion llamada *Extensiones* dar click en esta opcion.
2. Luego poner en el buscador *Chatgpt* e instalar alguna extension.
3. Luego es obtener una API KEY la cual puede ser encontra en la pagina de [openai](https://platform.openai.com/api-keys) dando click en `+ Create new secret key`, despues de darle nombre al API dar click a `Create secret key`. Copiar y pegar la llave en algun lugar porque a continuacion se ocupara.
4. Presionando *F1* y poner Set API KEY y colocar la llave en ese apartado y listo.
