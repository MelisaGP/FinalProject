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

En la enterior imagen se establece que el orden de arranque sea primero disco duro y después óptica, el cual la primera vez que se ejecute reconocerá que el disco se encuentra vacío y procederá a leer la óptica. Las otras veces que se ejecute leerá directamente el disco duro y cargará el CentOS 7 ya instalado.

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



![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/6configuracionUsuario.PNG)

### Configuración Contraseña

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/7configuracionContrasena.PNG)

### Instalación Completa

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/8instalacionCompleta.PNG)

## Configuración CentOS 7

### Visualización Ip a

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/9PrimerIP_a.PNG)

### Instalación Ip Tables

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/10InstalacionIpTables.PNG)

### Abrir Puertos Ip Tables

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/15AbrirPuertosEnIptables.PNG)

### Reiniciar Servicios IP Tables

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/16ReiniciarServiciosIpTables.PNG)

### Verificar Estado Ip Tables

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/17VerificarEstadoServiciosIpTables.PNG)

### Descargar Servicio Netstat

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/18DescargaServicioNetstat.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/19PrimeraVisualizacionNetstatPuertos.PNG)

## Configuración Python User

### Agregar a Sudoers

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/20Python_UserComoSUDOER1.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/21Python_UserComoSUDOER2.PNG)

## Instalar Entorno y Flask

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/25DescargasVirtualEnv.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/26CreacionEntornoFlask.PNG)

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/27InstalarFlaskEnEntornoVirtual.PNG)

## Pruebas de Flask con Netstat 

![alt text] (https://github.com/MelisaGP/FinalProject/blob/master/images/Netstat1.PNG)
