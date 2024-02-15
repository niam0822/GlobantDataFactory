# Globant DataFactory

Este repositorio busca crear una forma de cargue de archivos planos a una Base de Datos en Azure, usando la herramienta Azure DataFactory. 
También busca tener un backup de las tablas de la BD almacenandolas en un Storgae Account con el formato AVRO, lo cual va a permitir su recupración en caso de perdida.  

### Pre-requisitos 📋

- Tener una cuenta Azure
- Crear un Storage Account y subir los archivos que serán las fuentes para el cargue de información a la Base de Datos

## Ejecutando  ⚙️

El proyecto usa 3 pipelines:
- LoadData: Es el pipeline que va a cargar los archivos a la Base de Datos
- BackUp: Es un pipeline que recibe como argumento el nombre de una tabla y a partir de ella, crea un archivo .AVRO para guardar su backup en el StorageAccount
- RestoreTable: Es un pipeline que restaura una tabla a partir de un archivo .AVRO. El pipeline recibe como argumentos el nombre del archivo .AVRO y el nombre de la tabla que va a ser creada a partir de ese archivo en la Base de datos

### Analisis de resultados 🔩

Para el pipeline LoadData y RestoreTable, nos dirigimos a la base de datos para confirmar que las tablas han sido pobladas correctamente o si la tabla ha sido creada de forma exitosa. 
Para el pipeline BackUp, se dirige a el Storage Account creado y se verifica que el archivo se creó de forma exitosa. 


## Autores ✒️


* **Cristian Ibarra** - *Ingeniero de Telecomunicaciones* 

