# Tema 5: Dispositivos de Almacenamiento

## 1. Introducción

Los dispositivos de almacenamiento sirven para **contener información (software)**.

Se dividen en dos grandes grupos:

| Tipo | Descripción | Ejemplos |
|------|-------------|---------|
| **No volátiles** | Mantienen la información sin alimentación eléctrica | HDD, SSD, CD/DVD, USB |
| **Volátiles** | Necesitan alimentación eléctrica para mantener la información | RAM |

> Esta unidad se centra en los dispositivos **no volátiles**.

---

## 2. Evolución Histórica

```
Tarjeta perforada → Cinta magnética → Disquetera 5¼" → Disquetera 3½" 
→ CD-ROM → DVD → HDD → Pendrive → SSD
```

Los **discos duros (HDD o SSD)** constituyen el medio de almacenamiento **más importante** del ordenador. Permiten almacenar y recuperar gran cantidad de información.

---

## 3. Disco Duro HDD (Hard Disk Drive)

Forma parte de la **memoria secundaria** del ordenador (en oposición a la RAM).
- Gran capacidad de almacenamiento.
- No volátil.
- Acceso más lento que la RAM (aunque mejorando con conectores como M.2).

### 3.1 Estructura Física del HDD

| Componente | Descripción |
|------------|-------------|
| **Platos** | Discos magnéticos que almacenan la información. Giran a velocidad constante |
| **Cabezales** | Dispositivos de lectura/escritura. Cada cara del plato tiene uno |
| **Pista** | Circunferencia dentro de una cara. La pista 0 está en el borde exterior |
| **Cilindro** | Conjunto de pistas de la misma posición en todos los platos |
| **Sector** | División de una pista. Unidad mínima de almacenamiento (512 B o 4 KB) |

Los platos giran normalmente a **7.200 rpm** (o 5.400 rpm en portátiles).

### 3.2 Estructura Lógica del HDD

| Elemento | Descripción |
|----------|-------------|
| **MBR (Master Boot Record)** | Primer sector del disco (cabeza 0, cilindro 0, sector 1). Contiene la tabla de particiones y el master boot |
| **Espacio particionado** | Espacio asignado a alguna partición (C:, D:, etc.) |
| **Espacio sin particionar** | Espacio no asignado a ninguna partición (no aprovechable hasta particionarlo y formatearlo) |

### 3.3 Características de Rendimiento

| Característica | Descripción |
|---------------|-------------|
| **Modo de transferencia** | Cómo se transfieren los datos al RAM: PIO o DMA |
| **Tiempo de acceso** | Tiempo para colocar los cabezales sobre el sector (9–12 ms) |
| **Tiempo de búsqueda** | Tiempo para desplazar los cabezales entre pistas (8–12 ms) |
| **Velocidad de rotación** | Velocidad de giro: 5.400 rpm (portátil), 7.200 rpm (sobremesa), 10.000–15.000 rpm (SCSI) |
| **Latencia** | Tiempo de espera hasta que el sector deseado pasa bajo el cabezal |
| **Caché del disco** | Almacena lecturas previas para acelerar el acceso |
| **Interfaz** | ATA/IDE, SATA, SCSI, M.2 (sobremesa/portátil) |

**Modos de transferencia:**

| Modo | Velocidad |
|------|-----------|
| PIO Modo 1 | 5,2 MB/s |
| PIO Modo 4 | 16,6 MB/s |
| UDMA | 16,6 MB/s |
| UDMA33 | 33,3 MB/s |
| UDMA66 | 66,6 MB/s |
| UDMA100 | 100 MB/s |
| UDMA133 | 133 MB/s |

> **PIO** usa la CPU como intermediario. **DMA** transfiere datos entre RAM y disco sin intervención del microprocesador (más eficiente).

---

## 4. Disco SSD (Solid State Drive)

Utiliza **memorias de semiconductores** para almacenar toda la información → no tiene partes móviles.

### 4.1 Estructura

| Componente | Descripción |
|------------|-------------|
| **Memoria flash (NAND)** | Almacenamiento permanente de datos |
| **Memoria caché (DRAM)** | Zona temporal para acelerar el acceso. Es volátil |
| **Chip controlador** | Gestiona el acceso a las memorias y la comunicación con la CPU |

### 4.2 Tecnologías de celda NAND

| Tipo | Bits/celda | Resistencia | Velocidad | Precio |
|------|-----------|-------------|-----------|--------|
| **SLC** (Single Level Cell) | 1 bit | Máxima | Máxima | Máximo |
| **MLC** (Multi Level Cell) | 2 bits | Media | Media | Medio |
| **TLC** (Triple Level Cell) | 3 bits | Menor | Menor | Más bajo |

### 4.3 HDD vs SSD

| Característica | HDD | SSD |
|----------------|-----|-----|
| Velocidad | Baja (100–200 MB/s) | Alta (500 MB/s – varios GB/s) |
| Tiempo de acceso | ~10 ms | < 0,1 ms |
| Partes móviles | Sí | No |
| Ruido | Sí | No |
| Resistencia a golpes | Baja | Alta |
| Consumo | Mayor | Menor |
| Precio/GB | Más barato | Más caro |
| Capacidad | Hasta varios TB | Hasta varios TB |

---

## 5. Conectores para Discos Duros

### 5.1 IDE (PATA) – Maestro/Esclavo

- Cada conector IDE soporta **2 dispositivos**.
- Se diferencian con **jumpers**: maestro (master) o esclavo (slave).
- Cable plano de 40 pines.

**Configuraciones:**

| Jumper | Configuración |
|--------|--------------|
| Master with non-ATA slave | Maestro con un solo dispositivo |
| Slave | Esclavo |
| Master or single drive | Maestro en cable con dos unidades |
| Cable Select | El cable determina quién es maestro |

### 5.2 SATA

| Versión | Ancho de banda | Velocidad |
|---------|---------------|-----------|
| SATA 1.x | 1,5 Gb/s | 150 MB/s |
| SATA 2.x | 3 Gb/s | 300 MB/s |
| SATA 3.x | 6 Gb/s | 600 MB/s |

- Configuración **punto a punto** (sin maestro/esclavo).
- Cable de datos de 7 hilos. Cable de alimentación de 15 pines.

### 5.3 SCSI y SAS

**SCSI** (Small Computer System Interface): Estándar para dispositivos de alta velocidad y fiabilidad. Hasta 15.000 rpm. Usado hasta hace poco en servidores.

**SAS** (Serial Attached SCSI):
- Versión renovada de SCSI.
- Compatible físicamente con SATA.
- Hasta 6 GB/s (frente a los 600 MB/s de SATA3).
- Pensado para servidores.
- Mayor fiabilidad y rendimiento en uso intensivo.

---

## 6. RAID (Redundant Array of Independent Disks)

Sistema de almacenamiento que usa **múltiples discos** reconocidos como una sola unidad.

Requiere una **controladora RAID** (por hardware o software).

### Beneficios

- Mayor integridad de datos.
- Mayor tolerancia a fallos.
- Mayor rendimiento.
- Mayor capacidad.

### Tipos de configuración

| Tipo | Descripción |
|------|-------------|
| **Disk mirroring** | Busca redundancia de datos ante fallo de una unidad |
| **Disk stripping** | Busca mayores velocidades de transferencia (sin redundancia) |

### Niveles RAID

#### RAID 0 (Stripping / Volumen dividido)
- Distribuye los datos equitativamente entre 2 o más discos.
- Gran aumento de velocidad de lectura y escritura.
- **Sin redundancia**: si falla un disco, los datos son prácticamente irrecuperables.
- Mínimo 2 discos.

#### RAID 1 (Mirroring / Espejo)
- Crea una **copia exacta** de los datos en 2 o más discos.
- Alta seguridad: si falla un disco, el otro tiene la misma información.
- **Desventaja**: se aprovecha solo el 50% del espacio total.
- La velocidad de escritura baja, pero la de lectura aumenta.
- Mínimo 2 discos.

#### RAID 5
- Divide los datos en bloques con un bloque de **paridad** distribuido entre todos los discos.
- Permite el fallo de **un disco a la vez** sin pérdida de datos.
- Mínimo 3 discos.

#### RAID 0+1
- Combinación de RAID 0 y RAID 1.
- Busca tanto velocidad como redundancia.

### Cabinas de Discos Duros

Sistemas de almacenamiento formados por **múltiples discos físicos** con tecnología RAID para alta disponibilidad.

Protocolos de red de área de almacenamiento (SAN):
- **iSCSI** (SAN Internet SCSI)
- **FC** (Fibre Channel)

---

## 7. Almacenamiento Óptico (CD, DVD)

Las unidades ópticas leen y escriben datos mediante un **láser**.

**Interfaces:** IDE (PATA) o SATA.

---

## 8. Tarjetas de Memoria Flash

Dispositivos portátiles de pequeño tamaño, alta capacidad, resistentes a golpes y de bajo consumo. Usadas en móviles, cámaras, consolas, etc.

Fabricadas con **puertas lógicas NOR y NAND** para almacenar los bits.

### Tipos de tarjetas

| Tipo | Estado | Notas |
|------|--------|-------|
| **CompactFlash (CF)** | Obsoleta | Hasta 137 GB, velocidades CF 1.0–4.0 |
| **SmartMedia (SMC)** | Obsoleta | Hasta 128 MB |
| **Memory Stick (Sony)** | Poco usada | Propietaria de Sony; hasta 16 GB |
| **MMC (MultiMediaCard)** | Obsoleta | Desplazada por SD |
| **SD / Mini SD / Micro SD** | En uso | Estándar actual |

### Tarjetas SD

**Por capacidad:**

| Tipo | Capacidad |
|------|-----------|
| SDSC (Standard Capacity) | Hasta 2 GB |
| SDHC (High Capacity) | 2 GB – 32 GB |
| SDXC (Extended Capacity) | 32 GB – 2 TB |

> Las tarjetas son **retrocompatibles** hacia arriba (una tarjeta mejor funciona en lectores de tarjetas menos exigentes).

**Por clase de velocidad de escritura:**

| Clase | Velocidad mínima | Uso recomendado |
|-------|-----------------|-----------------|
| Clase 2 | 2 MB/s | Fotos y vídeo baja resolución |
| Clase 4 | 4 MB/s | Vídeo HD 720p |
| Clase 6 | 6 MB/s | Vídeo HD 720p |
| Clase 10 | 10 MB/s | Fotos HD consecutivas, vídeo FullHD 1080p |
| UHS U1 | 10 MB/s | Vídeo FullHD 1080p largo |
| UHS U3 | 30 MB/s | Vídeo 4K |

**Por clase de velocidad de vídeo:**

| Clase vídeo | Para |
|-------------|------|
| V6 | Vídeo HD 720p |
| V10 | Fotos HD, FullHD 1080p |
| V30 | Vídeo 4K a 24/30 fps |
| V60 | Vídeo 4K a 60/120 fps |
| V90 | Vídeo 4K a 60/120 fps u 8K |

---

## Ejercicios y Tareas

**Tarea 1**: Explica en tus propias palabras qué es el sistema de traducción LBA (Logical Block Addressing). ¿Qué pasaría si no dispusiéramos de este sistema?

**Tarea 2**: Calcula la capacidad de un disco con los siguientes datos (cada sector = 512 B):
- Cilindros = 6.253 / Discos = 8 / Sectores por pista = 63
- **Solución**: 6.253 × 16 × 63 × 512 = **3.227.148.288 B ≈ 3 GB**

**Tarea 3**: Investiga y explica en tus propias palabras:
1. Arquitectura interna de un SSD: NAND Flash y DRAM.
2. Tecnologías: SLC, MLC y TLC.

**Tarea IDE**: Preguntas sobre configuración IDE:
1. ¿Se puede instalar un disco IDE en cualquier ordenador? ¿Por qué?
2. ¿Cuántos conectores tiene el cable plano y para qué se usan?
3. ¿Cuáles son las tres configuraciones básicas con jumpers?
4. Verdadero/Falso:
   - a) Puedes conectar todas las unidades que quieras en cada canal IDE → **Falso** (máximo 2)
   - b) En un mismo canal podemos poner dos discos duros esclavos → **Falso**
   - c) En un mismo canal podemos poner un disco duro master y una unidad de CD → **Verdadero**
   - d) Los discos IDE deben conectarse a la placa base y a la fuente → **Verdadero**

**Tarea SAN**: Investiga los protocolos iSCSI y Fibre Channel.
