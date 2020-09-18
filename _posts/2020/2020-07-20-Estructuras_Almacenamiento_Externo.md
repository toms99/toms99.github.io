---
layout: article
title: Estructuras de almacenamiento.
date: 2020-07-20 
author: Tomás Segura
coverPhoto: https://images.assetsdelivery.com/compings_v2/muslumstock/muslumstock1811/muslumstock181124895.jpg
---

En una computadora se llegan a almacenar hasta millones de archivos por lo que las estructuras para almacenarlos deben ser muy eficientes. Por este motivo es que es un tema muy estudiado.

Existe el almacenamiento primario y secundario. La principal diferencia es ...

#### Disco duro

 - Conocido como HDD.
 - **Discos de acceso directo**: requieren la misma cantidad de tiempo para acceder a cada archivo.
 - No volátil.
 - Discos mecánicos.
 - Almacena información en discos rígidos. 
 - **Es un cuello de botella para la memoria.**
 - Utiliza cabezales electromagnéticos que cumplen con leer y escribir sobre cada plato. Convierten los bits en impulsos magnéticos cuando deben escribir información y realizan el proceso inverso para leer.
![Imagen de HDD abierto](https://i.stack.imgur.com/ajAaNm.jpg)

La siguiente imagen describe el esquema de un HDD donde se muestran los cabezales y los discos.
![Esquema de un HDD](https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Cylinder_Head_Sector.svg/360px-Cylinder_Head_Sector.svg.png)

Los **platos** del disco duro:
- Piezas redondas y metálicas que almacenan la memoria dentro del HDD.
- Se acomodan varios platos en un eje motor para incrementar la memoria.
- Son hechos de aluminio o vidrio y cubiertos por aleaciones de hierro o cobalto.
- Cada plato se divide en círculos concéntricos llamados **pistas**:
  - Almacenan la información.
  - Existen pistas en ambos lados del disco.
  - Cada pista se divide en **sectores:**
    - Es la unidad básica de almacenamiento en un HDD.
    - Cada sector puede almcenar más 512 bytes.
    - Se afrupan en cluesters.
 
 **Arreglos de discos:**
 - Data striping: dividir lógicamente la data secuencial.
 - Mirroring: 
	 - Replicación de discos lógicos en discos físicos separados en tiempo real para asegurar la disponibilidad de la información.
	 - Trabajan como si estuvieran en un mismo lugar.
- Bit de paridad o chequeo:
	 - Bit agregado al final de un string en un código binario que indica si el número de unos en el string es par o impar.
	 - La forma más simple de detección de errores.
	 - Bit de paridad par: 1 si el número de unosen la cadena es impar.
	 - Bit de impar: 1 si el número de unos en la cadena es par.
----
Nota: definir mirroring, paridad, redundancia.

---

## RAID
Arreglo reduntante de discos independientes.

#### Raid 0
- Striping a nivel de bloques.
- No hay paridad.
- No hay mirroring.
- No hay redundancia.
- Performance improvement.
- Additional Storage.
- No hay tolerancia a fallos: falla de un disco y se muere el arreglo.
- Acceso en paralelo.
- Mínimo 2 discos.
- Mirroring vs redundancy:

|Mirroring | Redundancy |
|--|--|
|Capacidad de un sistema de replicar o copiar datos en otros discos|Capacidad de un sistema de reponerse a fallos.|
|Implica redundancia.|-|

### Raid 1.
- Hay mirroring.
- No hay paridad.
- No stripping.
- Los datos estás escritos idénticamente en dos discos.
- Hay redundancia.

### Raid 2.
- No es usado normalmente.
- Stripping a nivel de bit.
- Los discos rotan sincronizadamante.
- Almacenado en al menos una unidad de paridad.

### Raid 3.
- Stripping a nivel de byte.
- Paridad dedicada: un solo disco para el cálculo de paridad.
- Los discos rotan sincronizadamente.

### Raid 4.
- Raid 5, pero toda la paridad está en un solo disco.
- Trabajan de forma independiente.
- I/O en paralelo.

### Raid 5.
- Stripping a nivel de bloque.
- Paridad distribuida.
- Provee una tolerancia a fallo en al menos dos discos.
- Distribuye la paridad y los datos entre todos los dispositivos.
- Arreglo no se destruye por el fallo de un solo disco.
- Lectura rápida.
- Escritura lenta, porque se recalcula la paridad.
- Se utilizan los 4 discos de forma simultánea.
- El total de espacio disponible es el número de discos menos uno por el tamño del disco más pequeño. Se trabaja por filas, por eso el tamaño del array es así. Misma cantidad de filas y misma cantidad de columnas. 
- Dentro de más discos se utilice el espacio de almacenamiento es más eficiente sin perder redundancia.
- Puede sobrevivir sin un dispositivo, pero se vuelve lento.
- Utiliza XOR para reconstruir los datos y crear la cadena de paridad.

### Raid 10.
- Raido 1 + Raid 0.
- Mirroring stripping.
- Striping.
- Mínimo 4 discos.
- Excelente redundancia.
- Excelente rendimiento.
- Mejor opción para cosas críticas.

### Sistemas de archivos.

El sistema operativo da una abstracción del hardware. 

Archivos: Representación abstracta de la información en el disco
- Unidades lógicas de información creadas por procesos
- La información en los archivos debe ser persistente, no ser afectado por ningún proceso de creación o terminación.
- La parte del sistema operativo que gestiona archivos es el file
system.
- Los programadores utilizan un API para interactuar con el file
system.
- Existen varios file systems:
	- Ext2, Ext3 (Linux).
	- NTFS (Windows).
	- FAT, FAT32 (DOS, Windows).

**Requisitos de un file system:**
- Persistencia.
- Velocidad.
- Tamaño (que sea óptimo).
- Protección (personalizable).
- Que permita compartirlo con otros usuarios.
- Fácil de usar.
- Acceso Random.

**Terminología:**

- Disco: permanent storage
- Bloque o sector: la unidad más básica de un disco o un FS
(file system).
- Partición: subconjunto de bloques.
- Volumen: colección de bloques.
- Superbloque: donde el file system guarda la información
crítica.

Un archivo es un mecanismo de abstracción. Provee un camino para guardar información. Oculta al usuario los detalles de como y donde la información es almacenada (que son detalles de implmentación).

**Existen tres formas de para un file system:**

- Secuencia de bytes: Unix y Windows
	- El sistema operativo no ayuda pero tampoco estorba.
	- Almacena como una cadena de bytes, provee flexibilidad.
	- Normalmente llamados archivos planos.
- Récord de tamaño fijo.
	- Se trabaja un récord por completo, siempre. Se lee por completo aunque no sea necesario leer todas sus partes.
	- Se utiliza en mainframe y midframe.
- Árbol de récord.
	- Cada record tiene una llave.
	- El árbol se ordena por un key field para permitir una busqueda mas rapida por keys.
	- La operación básica es obtener un récord en específico.

**Tipos de acceso a archivos:**
- Acceso secuencial:
	- Implementado en sistemas operativos primitivos.
	- Un proceso puede leer únicamente todos los bytes que están contenidos.
- Random Access File
	- Puedo leer los bytes o records de un archivo en cualquier orden.
	- Acceso a los récords por llaves.

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)
