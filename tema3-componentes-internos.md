# Tema 3: Componentes Internos de un Ordenador

## 1. La Placa Base

La **placa base** (mainboard o motherboard) es el **elemento principal del ordenador**. A ella se conectan todos los demás dispositivos (disco duro, memoria, microprocesador) y hace que todos funcionen en equipo.

De ella dependerán los componentes que podremos instalar y las posibilidades de ampliación del ordenador.

Físicamente es una placa de material sintético con un circuito impreso que contiene:
- Chipset
- BIOS
- Puertos del ratón y teclado
- Conectores IDE y SATA
- Zócalo del microprocesador
- Zócalos de memoria
- Puertos paralelo y serie

### Componentes principales de una placa base

| Nº | Componente |
|----|-----------|
| 1 | Zócalo procesador |
| 2 | Zócalos de memoria |
| 3 | Zócalo gráfico (PCIe) |
| 4 | Conectores SATA (HDD/SSD) |
| 5 | USB interno |
| 6 | BIOS/UEFI |
| 7 | Pila CMOS |
| 8 | Chipset |
| 9 | Sonido integrado |
| 10 | Puerto ratón/teclado |

---

## 2. Factor de Forma

El **factor de forma** determina el tamaño y orientación de la placa, el tipo de fuente de alimentación necesaria y los periféricos integrables.

### Evolución histórica

| Factor | Año | Descripción |
|--------|-----|-------------|
| **IBM PC** | 1981 | Primera placa base para PC |
| **FullSize AT** | 1984 | Evolución del IBM PC, procesador de 16 bits (Intel 286). Mayor tamaño |
| **LPX** | Finales 90 | Los slots de expansión están en una riser card, no directamente en la placa. Tamaño 9×13 pulgadas |
| **ATX** | 1995 | Introducida por Intel. La más popular actualmente |
| **Micro-ATX** | - | Versión reducida de ATX, menos ranuras de expansión |
| **Mini-ATX** | - | Versión aún más pequeña, compatible con ATX |
| **WTX** | Finales 90 | Para servidores. Soporta 2 procesadores. Mejor disipación de calor |
| **BTX** | 2004 | Introducida por Intel para mejorar refrigeración. Poco éxito en el mercado |
| **Mini-ITX** | - | Muy pequeña, para PCs compactos y sistemas embebidos |

### Ventajas del formato ATX

- Mejor ubicación de CPU y memoria, cerca del ventilador de la fuente.
- Conectores de alimentación con un único conector no reversible.
- Conectores para discos duros más cercanos (cables más cortos).

> ⚠️ **Micro-ATX y Mini-ATX** son compatibles con ATX: se puede sustituir una placa Mini/Micro por una ATX sin problemas de compatibilidad con el hardware o la fijación a la torre.

---

## 3. Zócalo del Microprocesador

Conector en el que se inserta el microprocesador. Ha evolucionado mucho desde los primeros PC.

### Tipos de zócalos

#### PGA (Pin Grid Array)
Interfaz de conexión a nivel físico. Los pines están en el procesador.
- Usado en: Intel 80386, Intel 80486.

#### ZIF (Zero Insertion Force)
El micro se inserta sin necesidad de hacer presión. Una palanca permite insertarlo y liberarlo sin doblar patillas.

#### Slot 1
Tipo de conexión para procesadores de Intel: Celeron, Pentium II y Pentium III. Actualmente obsoleto.

#### LGA (Land Grid Array)
Los **pines están en la placa base** en lugar de en el procesador; el micro tiene contactos planos en su parte inferior.
- Ventajas: mejor distribución de energía y mayores velocidades de bus.
- Desventaja: fragilidad de los pines de la placa.
- Usado actualmente por Intel.

#### BGA (Ball Grid Array)
El chip se suelda directamente a la placa. No es reemplazable. Común en portátiles y dispositivos móviles.

> ⚠️ No confundir el **formato** del zócalo (PGA, ZIF, LGA) con el **modelo** del procesador que va insertado.

---

## 4. Bancos de Memoria RAM

Ranuras (slots) para instalar los módulos de memoria principal del ordenador.

### Evolución de los módulos

#### SIMM (Single In-line Memory Module)
- 30 pines: primeros ordenadores.
- 72 pines: sucesor. Las memorias se inclinaban para insertarse.

#### DIMM (Dual In-line Memory Module)
Cada contacto de una cara está **separado** del opuesto (a diferencia del SIMM). La disposición duplica el número de contactos con el bus.

| Tipo | Contactos | Velocidad máxima | Capacidad máxima |
|------|-----------|-----------------|------------------|
| SDR SDRAM | 168 | PC133 | — |
| DDR SDRAM | 184 | DDR-600 | 1 GiB/módulo |
| DDR2 SDRAM | 240 | DDR2-1200 | 4 GiB/módulo |
| DDR3 SDRAM | 240 | DDR3-2400 | 16 GiB/módulo |
| DDR4 SDRAM | 288 | DDR4-3200 | 64 GiB/módulo |
| DDR5 SDRAM | 288 | DDR5-6200 | 256 GiB/módulo |

#### LPDDR (Low-Power DDR)
Memoria DDR de **bajo consumo** para dispositivos con batería (móviles, portátiles).

---

## 5. Chipset

Conjunto de circuitos lógicos que ayudan al procesador y a los componentes del PC a **comunicarse y controlarse entre sí**.

### Funciones

- Controla la transmisión de datos, instrucciones y señales entre la CPU y el resto del sistema.
- Determina la velocidad de transferencia entre CPU, memoria y periféricos.
- Ofrece soporte para el bus de entrada/salida.

### Puente Norte (Northbridge)

Responsable de la conexión del bus frontal (FSB) con componentes de **alta velocidad**:
- Memoria RAM
- Slot AGP o PCI Express

Controla:
- Tipo y número de microprocesadores soportados
- Velocidad del microprocesador y del bus frontal (FSB)
- Tipo y cantidad máxima de RAM
- Controladora gráfica integrada

> ℹ️ En la actualidad, el puente norte ha desaparecido como chip separado y sus funciones se han **integrado dentro del procesador**.

### Puente Sur (Southbridge)

Responsable de la conexión con componentes **más lentos**:
- Buses de expansión: PCI, ISA.
- Controladores: IDE, SATA, Ethernet, sonido.
- Puertos USB, FireWire.
- Gestión de energía.
- Controlador de teclado, interrupciones, DMA.

#### DMA (Direct Memory Access)
Permite a ciertos componentes acceder a la memoria del sistema para **leer o escribir independientemente de la CPU**, liberando al procesador de esta tarea.

---

## 6. Ranuras de Expansión (Slots)

Ranuras con conectores eléctricos donde se insertan las **tarjetas de expansión** (gráfica, sonido, red, etc.).

### Evolución

#### ISA (8/16 bits)
- Una de las ranuras más antiguas.
- Frecuencia: 4,77 MHz.
- Para Intel 8086/8088. Completamente obsoleta.

#### AGP (Accelerated Graphics Port)
- Desarrollada por Intel en 1996.
- Exclusivamente para **tarjetas gráficas**.
- Solo puede aparecer una por placa base.
- Velocidades: AGP 1x (264 MB/s) hasta AGP 8x (2128 MB/s).

#### PCI (Peripheral Component Interconnect)
- Apareció a principios de los 90.
- Capacidad inicial de transferencia: 133 MB/s.
- Existe en 32 bits (124 clavijas) y 64 bits (188 clavijas).
- Voltaje: 3,3V (portátiles) o 5V (sobremesa).

#### PCI-X (PCI Extended)
- Desarrollada en 1998. Mejora el bus PCI de 32 bits.
- Mayor ancho de banda. Similar en aplicación eléctrica al PCI.
- Sustituida por PCIe en diseños modernos.

#### PCI Express (PCIe)
- Desarrollada por Intel en 2004.
- No solo para gráficos, sino para cualquier tarjeta de expansión.
- Se define por el número de **lanes (carriles)**: x1, x4, x8, x16.
- Transmisión **serie punto a punto** (más eficiente que el bus compartido de PCI/PCI-X).

| Versión PCIe | Por carril | En 16x |
|-------------|-----------|--------|
| 1.0 | 250 MB/s | 4 GB/s |
| 2.0 | 500 MB/s | 8 GB/s |
| 3.0 | 984,6 MB/s | 16 GB/s |
| 4.0 | 1969,2 MB/s | 32 GB/s |

> **PCI/PCI-X vs PCIe**: PCI y PCI-X usan transmisión **paralela** en bus compartido (el rendimiento baja al agregar dispositivos). PCIe usa transmisión **serie punto a punto** (cada dispositivo tiene su propio bus, más eficiente).

### Fórmula tasa de transferencia

```
Tasa de transferencia = (Ancho del bus / 8) × Frecuencia del bus
```

---

## 7. Conectores Internos

### Puerto IDE (PATA)
- Interfaz de transmisión en **paralelo**.
- Tamaño de palabra: 16 bits.
- Ancho de banda: 16 MB/s – 166 MB/s.
- Cable plano de 40 pines.
- Configuración **multipunto**: maestro/esclavo por jumpers.

**Configuraciones IDE:**

| Config | Descripción |
|--------|-------------|
| Master with non-ATA slave | Maestro en cable de una sola unidad |
| Slave | Esclavo |
| Master or single drive | Maestro en cable de dos unidades |
| Cable Select | La posición en el cable determina maestro/esclavo |

### Puerto SATA (Serial ATA)
Interfaz de transferencia de datos en **serie** entre la placa base y dispositivos de almacenamiento.

| Versión | Frecuencia | Velocidad real |
|---------|-----------|----------------|
| SATA I | 1500 MHz | 150 MB/s |
| SATA II | 3000 MHz | 300 MB/s |
| SATA III | 6000 MHz | 600 MB/s |

- Configuración **punto a punto**: cada dispositivo se conecta directamente a un controlador SATA (no hay maestro/esclavo).
- Cable de datos de 7 hilos (10 mm de ancho).
- Cable de alimentación de 15 conectores.

### Conector M.2 – SATA vs NVMe

#### M.2 SATA
- Misma velocidad que SATA III (600 MB/s).
- Más económico.
- Capacidad máxima ~2 TB.

#### M.2 NVMe
- Usa la interfaz **PCI Express**.
- Velocidades de lectura/escritura mucho más altas que SATA.
- Capacidad máxima ~4 TB.
- La nueva generación de almacenamiento rápido.

### USB (Universal Serial Bus)
Interfaz que soporta dispositivos periféricos de baja y alta velocidad.

**Características:**
- **Plug & Play**: se pueden conectar/desconectar dispositivos sin reiniciar (en caliente).
- El sistema operativo los reconoce automáticamente e instala los drivers.

### FireWire (IEEE 1394)
Estándar para bus serie de alta velocidad. Tasa de transferencia de hasta 1,2 GB/s. Usado principalmente para cámaras de vídeo y fotografía digital.

### Puertos de vídeo

| Puerto | Tipo | Descripción |
|--------|------|-------------|
| VGA (DB-15) | Analógico | El estándar durante años. Obsoleto |
| DVI | Digital | Digital Visual Interface |
| HDMI | Digital | High-Definition Multimedia Interface, también transmite audio |
| DisplayPort | Digital | Estándar actual de alta velocidad |

---

## 8. Conectores de Energía

Conectan los cables de la fuente de alimentación a la placa base.

| Conector | Descripción |
|----------|-------------|
| ATX 24 pines | Conector principal de alimentación de la placa |
| ATX 12V 4/8 pines | Alimentación adicional para la CPU |
| PCIe 6/8 pines | Alimentación para tarjetas gráficas |
| SATA de alimentación | Para discos duros y unidades ópticas |
| MOLEX (4 pines) | Conector antiguo de alimentación IDE |

---

## Tareas y Ejercicios

**Tarea 1**: Investigar los factores de forma LPX, NLX, BTX, Mini-ITX, Nano-ITX, Pico-ITX. Para cada uno: fecha de lanzamiento, tamaño, disposición de elementos, ventajas, desventajas y foto.

**Tarea 4**: Busca en internet dos memorias (la mejor y la peor) para DIMM SDRAM, DDR, DDR2, DDR3 y DDR4. Incluye foto, precio y comparativa.

**Tarea 5**: Busca las especificaciones de los chipsets Intel Z690 e Intel H370. Encuentra dos placas del mercado que usen cada uno.

**Tarea 6**: Calcula las velocidades de:
- AGP 2.0 (Bus 8 bytes, Frecuencia 133 MHz) → **1.064 MB/s**
- AGP 3.0 (Bus 16 bytes, Frecuencia 133 MHz) → **2.128 MB/s**
- PCI 1.0 (Bus 8 bits, Frecuencia 66 MHz) → **66 MB/s**

**Tarea 9**: Busca una placa madre actual, descarga su manual e identifica todos los componentes sobre la foto de la placa.
