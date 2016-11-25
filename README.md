# FinalProject
<b>Intrgrantes:</b> <br> 
* Melisa García Peña - 13103005 <br>
* Andrés Felipe Piñeros González - 12204032 <br>
* Johan David Ballesteros Salgado - 13103036 <br>

<b>Repositorio:</b> https://github.com/MelisaGP/FinalProject

-----
## Configuración Máquina Virtual

Primero se procede a configurar los parámetros iniciales de la máquina virtual, desde la herramienta Virtual Box. Se tiene como supuesto, haber descargado el ISO de CentOS 7 minimal. 

### Configuración del Sistema

Se configura el sistema las siguientes caraterísticas:

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/A1CapturaProcesamiento.PNG)

<p align="justify">
En la enterior imagen se establece que el orden de arranque sea primero disco duro y después óptica, el cual la primera vez que se ejecute reconocerá que el disco se encuentra vacío y procederá a leer la óptica. Las otras veces que se ejecute leerá directamente el disco duro y cargará el CentOS 7 ya instalado.
</p>

Ahora se configura el procesador de la máquina virtual asignandole dos procesadores, límite de ejecución del 100% y habilitando PAE/NX.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/A2Process.PNG)

### Configuración de Almacenamiento

Se procede a cargar el ISO de CentOS 7 minimal como IDE.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/A3Disco.PNG)

### Configuración Red

Se configura las dos adaptadores de red:

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/A4NAT.PNG)

El adaptador de red NAT que permite acceder a internet.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/A5Bridge.PNG)

El adaptador de red Bridge que permite acceder a la red local.

## Instalación de CentOS 7

Empieza la instalación del CentOS 7:

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/1CapturaCentos7.PNG)

### Configuración Disco

Se procede a seleccionar el disco donde se almacenará el CentOS 7.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/2Configuraci%C3%B3nDisco.PNG)

### Configuración Teclado

Se configura el idioma del teclado.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/3ConfiguracionTeclado.PNG)

### Configuración Red

Se procede a configurar las dos interfaces de red y el nombre del host.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/4ConfiguracionRed1.PNG)

Se selecciona la opción marcada en la imagén, para configurar automáticamente las interfaces (ONBOOT = yes).

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/5ConfiguracionRed2.PNG)

### Configuración Usuario

Se crea un nuevo usuario con el nombre de python_user, este usuario ejecutará los servicios de python y las pruebas de los mismos. Como se puede ver en la imagen, el usuario no es un administrador.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/6configuracionUsuario.PNG)

### Configuración Contraseña

Se ingresa una contraseña para el usuario root del sistema.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/7configuracionContrasena.PNG)

### Instalación Completa

Se finaliza la configuración del CentOS 7 y se procede a reiniciar la máquina virtual.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/8instalacionCompleta.PNG)

## Configuración CentOS 7

### Visualización Ip a

Se verifica la configuración de las interfaces de red con el comando:

```{python}
# ip a
```

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/9PrimerIP_a.PNG)

### Instalación Ip Tables

Se realiza la instalación del servicio ip tables.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/10InstalacionIpTables.PNG)

Se verifica la instalación del servicio en el directorio de red.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/14VerificacionInstalacionIpTables.PNG)

Se verifica la existencia de las interfaces de red, en el directorio de red.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/12VerificacionInterfazRed1.PNG)

Se verifica que las interfaces tengan el ONBOOT en yes.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/13VerificacionInterfazRed2.PNG)

### Abrir Puertos Ip Tables

Se abren los puertos en los que se desplegará los servicios de python. En este caso se desplegará en el puerto 8081.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/15AbrirPuertosEnIptables.PNG)

### Reiniciar Servicios IP Tables

Se reinicia el servicio de ip tables para que los cambios surjan efecto sobre el sistema.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/16ReiniciarServiciosIpTables.PNG)

### Verificar Estado Ip Tables

Se verifica que los puertos se hayan abierto correctamente.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/17VerificarEstadoServiciosIpTables.PNG)

### Descargar Servicio Netstat

Se descarga el servicio de Netstat, que permitirá comprobar que los servicios de Flask estén corriendo por los puertos correspondientes.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/18DescargaServicioNetstat.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/19PrimeraVisualizacionNetstatPuertos.PNG)

## Configuración Python User

### Agregar a Sudoers

Se le da permisos de administrador al usuario python_user, para que pueda leer, escribir y ejecutar archivos en el sistema.

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/20Python_UserComoSUDOER1.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/21Python_UserComoSUDOER2.PNG)

## Instalar Entorno y Flask

Se instala un entorno virtual por medio de la librería virtualenv, esta librería permite crear un entorno para la aplicación de Flask, la cual prestará los servicios Rest.

```{python}
$ mkdir enviroments
$ cd enviroments
$ virtualenv flask_env
$ cd ~/envs
$ . flask_env/bin/activate
```

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/25DescargasVirtualEnv.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/26CreacionEntornoFlask.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/27InstalarFlaskEnEntornoVirtual.PNG)

##Creación de los servicios

Para la creación de servicios se describe los siguientes contratos.

URIs.

|   |POST   |GET   |PUT   |DELETE   |
|---|---|---|---|---|
| /files  | Crear archivo  | Obtener listado de archivos  | No aplica | Elimina todos los archivos  |
| /files/recently_created  | No aplica  | Retorna los archivos que se crearon recientemente  | No aplica | No aplica  |

Formatos de envío de las solicitudes.

|   |POST   |GET   |PUT   |DELETE   |
|---|---|---|---|---|
| /files  | JSON  | No aplica  | No aplica  | No aplica  |
| /files/recently_created  | No aplica  | No aplica  | No aplica  | No aplica  |

Formatos de respuesta de las solicitudes.

|   |POST   |GET   |PUT   |DELETE   |
|---|---|---|---|---|
| /files  | HTTP 201 CREATED | JSON | HTTP 404 NOT FOUND | HTTP 200 OK |
| /files/recently_created  | HTTP 404 NOT FOUND | JSON  | HTTP 404 NOT FOUND | HTTP 404 NOT FOUND |

Se procede a crear un directorio donde se alojarán los archivos .py con los métodos de los servicios que cumplan los anteriores contratos.

##Crear scripts para servicios REST
e.py contendrá todos los servicios rest

ec.py contendrá todos los métodos de apoyo de python.

e.py importa los métodos de ec.py para responder a las solicitudes REST.

```python
cd ..
cd flaskExam
touch e.py
touch ec.py
```


###Archivo de funciones REST:
files GET -> Obtiene todos los archivos de la carpeta home de filesystem_user. Excluye archivos ocultos y carpetas.

files POST -> Agrega un nuevo archivo. Obtiene los parámetros de un objeto JSON (filename, content).

files DELETE -> Elimina todos los archivos de la carpeta. Aprovecha files GET para esto. No elimina los archivos ocultos ni las
carpetas.

files PUT -> 404

files/recently_created GET -> Obtiene los dos archivos más recientemente modificados o creados.

files/recently_created POST -> 404

files/recently_created PUT -> 404

files/recently_created DELETE  -> 404

```python
from flask import Flask, abort, request
import json

from ec import get_all_files, create_file, get_recent_files, remove_one_file

app = Flask(__name__)
api_url = '/v1.0'

@app.route(api_url+'/files',methods=['GET'])
def read_all_files():
  list = {}
  list["files"] = get_all_files()
  return json.dumps(list), 200

@app.route(api_url+'/files/recently_created',methods=['GET'])
def read_recent_file():
  list = {}
  list["files"] = get_recent_files()
  return json.dumps(list), 200

@app.route(api_url+'/files',methods=['POST'])
def read_create_file():
  cont = request.get_json(silent=True)
  file = cont['file']
  content = cont['content']
  if not file or not content:
    return "empty file or content", 404
  if create_file(file, content):
    return "CREATED", 200
  else:
    return "error while creating file", 400

@app.route(api_url+'/files',methods=['DELETE'])
def delete_all_files():
  list = {}
  list["files"] = get_all_files()
  for idx, val in enumerate(list["files"]):
    if not remove_one_file(val)
      return "Error while deleting files", 400
  return "DELETED ALL HOME FILES", 200

if __name__ == "__main__":
  app.run(host='0.0.0.0',port=8081,debug='True')

```
En la última línea del script se puede ver que la aplicación de Flask atenderá las solicitudes desde el puerto 8081.

###Archivo de comandos de apoyo de python

create_file -> Sirve para crear una archivo con un contenido específico.
Params: file: nombre del archivo.    content: contenido (texto) del archivo.

get_all_files -> Sirve para visualizar todos los archivos. Excluye archivos ocultos y carpetas.

get_recent_files -> Muestra los últimos 2 archivos creados o modificados.

remove_all_files -> Elimina un archivo de /home/filesystem_user.

``` python

from subprocess import Popen, PIPE

def create_file(file, content):
  result1 = Popen(["touch",'/home/filesystem_user/'+file], stdin=PIPE, stdout=PIPE, stderr=PIPE)
  log = open('/home/filesystem_user/'+file, 'w')
  log.write(content)
  log.flush()
  return True

def get_all_files():
  result1 = Popen(["ls","/home/filesystem_user","-p"], stdin=PIPE, stdout=PIPE, stderr=PIPE)
  result2 = Popen(["grep", "-v", "/"], stdin=result1.stdout, stdout=PIPE, stderr=PIPE)
  return result2.communicate()[0].split('\n')

def get_recent_files():
  result1 = Popen(["ls","/home/filesystem_user","-Art"], stdin=PIPE, stdout=PIPE, stderr=PIPE)
  result2 = Popen(["tail", "-n", "2"], stdin=result1.stdout, stdout=PIPE, stderr=PIPE)
  return result2.communicate()[0].split('\n')

def remove_one_file(file):
  process = Popen(["rm", "/home/filesystem_user/"+file], stdin=PIPE, stdout=PIPE, stderr=PIPE)
  process.wait()
  return True

```
## Pruebas en POSTMAN
A continuación se verificará con un flujo de acciones el funcionamiento de los servicios REST.

### Verifico con el files GET que no hayan archivos.
![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaA.PNG)

### Agrego 3 archivos con el file POST

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaB.PNG)

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaC.PNG)

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaD.PNG)

### Verifico el nombre y el contenido desde la consola.

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaE.PNG)

### Verifico la existencia con files GET

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaF.PNG)

### Verifico los ultimos últimos 2 archivos/carpetas modificados con file/recently_created GET

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaG.PNG)

### Elimino los archivos con files DELETE

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaH.PNG)

### Verifico que se hayan eliminado con files GET

![alt text](https://github.com/AndresPineros/microservicesAFP/blob/master/imagenesandres/CapturaI.PNG)

## Pruebas de Flask con Netstat 

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/Netstat1.PNG)
