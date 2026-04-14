# Tema 2: Funcionamiento de un Ordenador

## Objetivos de la unidad

- Conocer los inicios de la informática y cómo se llegó a los ordenadores actuales.
- Conocer y explicar el funcionamiento de una arquitectura Von Neumann.
- Describir los bloques funcionales de un ordenador.
- Explicar los pasos que se realizan al ejecutar un programa.
- Identificar los tipos de software de un ordenador.
- Distinguir la función del sistema operativo.

---

## 1. Historia de los Ordenadores

### Prehistoria

**Ábaco chino** (3500–2600 a.C.)
Utilizado para realizar operaciones matemáticas en base 10. Aún se usa en ciertos países asiáticos.

**Quipu andino** (1430–1550 d.C.)
Sistema nemotécnico mediante cuerdas de lana o algodón y nudos. Su principal uso era la contabilidad.

### Generación 0: Era Mecánica

- **Máquina de Turing** (1936): Fundamentos teóricos de la computación.
- **Enigma**: Máquina de cifrado alemana de la Segunda Guerra Mundial.
- **Mark I**: Primera computadora electromecánica.

### Generación 1: Era Electrónica

**ENIAC** (1946)
- Primer computador electrónico de la historia.
- Incorporó el primer elemento electrónico: las **válvulas de vacío**.
- Velocidad de cálculo muy superior al Mark I.

> 💡 **¿Qué es una válvula de vacío?**  
> Componente electrónico utilizado para amplificar, conmutar o modificar una señal eléctrica mediante el control del movimiento de los electrones en un espacio vacío a muy baja presión.

**John Von Neumann** (1944): Desarrolló la idea del **programa almacenado** y escribió el fundamento teórico de construcción de un ordenador electrónico que ha perdurado hasta nuestros días.

### Generación 2: Era Electrónica

**EDVAC**
- Considerado por muchos el primer ordenador de la historia.
- Fue el primero en trabajar con un programa almacenado.
- Introdujo el concepto de **memoria** y **programa almacenado (software)**.

**UNIVAC-1** (1951)
- Primer ordenador comercial (para empresas).
- Usaba cintas magnéticas en lugar de tarjetas perforadas.

**IBM 1401** (1955–1964)
- Sustituyó la válvula de vacío por el **transistor**.
- Supuso una reducción notable en tamaño, potencia y fiabilidad.
- Se introdujeron los **lenguajes de alto nivel**: COBOL, FORTRAN y ALGOL.

> 💡 **El transistor**  
> Dispositivo electrónico semiconductor que cumple funciones de amplificador, oscilador, conmutador o rectificador.

### Generación 3

**IBM 370** (1964–1974)
- Aparecieron los **circuitos integrados**, que supusieron la miniaturización de los ordenadores.
- Evolucionó el software y aparecieron los primeros **sistemas operativos**.

### Cuarta Generación

**Intel 4004** (1974–1983)
- Intel presentó la primera CPU en un único circuito integrado.
- En 1981 aparecieron los primeros **PC (Personal Computer)**.
- Alto perfeccionamiento de las unidades de almacenamiento.
- Sentó las bases de los ordenadores modernos.

### Quinta Generación

- Japón lanzó el programa de quinta generación de computadores.
- Máquinas capaces de comunicarse en lenguaje cotidiano (**PROLOG**).
- Se implementó el procesado en **paralelo**.
- Gran aumento en la velocidad de los circuitos.
- Sistemas de **inteligencia artificial**.

---

## 2. Unidades de Medida

| Unidad | Equivalencia |
|--------|-------------|
| 1 bit | 0 ó 1 |
| 1 Byte | 8 bits |
| 1 KB (Kilobyte) | 1.024 Bytes |
| 1 MB (Megabyte) | 1.024 KB |
| 1 GB (Gigabyte) | 1.024 MB |
| 1 TB (Terabyte) | 1.024 GB |
| 1 PB (Petabyte) | 1.024 TB |

---

## 3. Arquitectura Von Neumann

Von Neumann describió el fundamento teórico de construcción de un ordenador electrónico con programa almacenado. La idea era conectar permanentemente las unidades del ordenador, de manera que su funcionamiento estuviese coordinado bajo un **control central**.

Los bloques funcionales son:
- Unidad Central de Proceso (CPU)
- Memoria Principal (RAM)
- Unidades de Entrada/Salida
- Buses de comunicación

---

## 4. Unidad Central de Proceso (CPU)

Es el **cerebro del ordenador**: controla y gobierna todo el sistema. Interpreta y ejecuta las instrucciones de los programas almacenados en memoria y procesa los datos.

La CPU está formada por:

### 4.1 Unidad de Control (UC)

Se encarga de **interpretar y ejecutar** las instrucciones máquina y generar las señales de control necesarias.

**Proceso de ejecución de una instrucción:**

1. Extrae de memoria la instrucción a ejecutar (usa el **Contador de Programa CP**).
2. Carga el código de la instrucción en el **Registro de Instrucción (RI)**.
3. Establece conexión con la ALU.
4. Si no tiene todos los datos, los obtiene de la memoria principal.
5. Ordena a la ALU que efectúe las operaciones necesarias.
6. El resultado se almacena en el **Registro Acumulador**.

**Componentes de la UC:**

| Componente | Función |
|------------|---------|
| Descodificador de instrucción (DI) | Extrae y analiza el código de operación del RI y genera las señales de control |
| Reloj | Proporciona impulsos eléctricos a intervalos constantes. Mide en GHz |
| Secuenciador | Genera órdenes elementales sincronizadas con el reloj para ejecutar instrucciones |

### 4.2 Unidad Aritmético-Lógica (ALU)

Su función es operar con los datos que recibe siguiendo las órdenes de la UC.

**Operaciones aritméticas:** Suma, Resta, Multiplicación, División.

**Operaciones lógicas:** AND, OR, XOR, NOT.

> 💡 **George Boole** (1815) fue el inventor del **Álgebra Booleana**, base de la aritmética computacional. El Álgebra de Boole esquematiza las operaciones lógicas Y, O, NO y SI (AND, OR, NOT, IF).

**Puertas lógicas:**

| Puerta | Descripción |
|--------|-------------|
| AND | La salida se activa **solo** cuando se activan **todas** las entradas |
| OR | La salida se activa si se enciende **cualquiera** de las entradas |
| NOT | La salida es la **inversa** de la entrada |
| XOR | La salida se activa cuando las entradas son **diferentes** |

**Coprocesador matemático (FPU - Floating-Point Unit):**
Parte importante de la ALU encargada de manejar operaciones en coma flotante: aritmética con números fraccionarios, operaciones trigonométricas y logarítmicas.

### 4.3 Registros Internos del Procesador

Celdas de memoria de **alta velocidad** dentro del procesador para almacenar datos temporalmente. Formados por un conjunto de bits (múltiplos de 8: 8, 16, 32, 64 bits).

Cuanto mayor sea el tamaño del registro, más potente será el procesador.

**Tipos de registros:**

| Registro | Descripción |
|----------|-------------|
| MAR (Memory Address Register) | Contiene la dirección del dato que se quiere leer o escribir. Conectado al bus de direcciones |
| MDR (Memory Data Register) | La CPU lee o escribe un dato a través de él. Conectado al bus de datos |
| CP (Contador de Programa) | Almacena la dirección de la próxima instrucción a ejecutar |
| RI (Registro de Instrucción) | Almacena la instrucción en ejecución |

**Secuencia de ejecución (Ejercicio 2):**
1. El CP tiene la dirección de la próxima instrucción → se pasa al MAR.
2. La instrucción apuntada por el MAR se carga en el MDR.
3. Desde el MDR pasa al RI.
4. El descodificador interpreta el RI y genera las órdenes oportunas.
5. El CP se incrementa en 1 para apuntar a la siguiente instrucción.

---

## 5. Buses de Comunicación

Las unidades del ordenador se comunican a través de **buses**: líneas eléctricas u ópticas a través de las cuales circula la información en forma de bits.

| Bus | Función |
|-----|---------|
| **Bus de datos** | Intercambio de datos entre CPU y el resto de unidades. Velocidad en MHz/GHz. Transmisión paralela (IDE) o serie (SATA) |
| **Bus de direcciones** | Transmite direcciones entre CPU y memoria. Determina el volumen de memoria accesible |
| **Bus de control** | Genera los impulsos eléctricos para gobernar el resto de elementos |

---

## 6. Memoria Principal (RAM)

La **RAM (Random Access Memory)** almacena el programa en ejecución y los datos que maneja.

- Formada por casillas o posiciones de memoria, cada una con capacidad de **1 byte (8 bits)**.
- Cada casilla tiene una **dirección de memoria** única.
- Es **volátil**: cuando se apaga el ordenador, su contenido desaparece.

### Jerarquía de memorias

Las memorias se organizan en niveles según capacidad, velocidad y coste:

| Nivel | Tipo | Velocidad | Capacidad | Coste |
|-------|------|-----------|-----------|-------|
| 1 | Registros CPU | Máxima | Mínima | Máximo |
| 2 | Caché L1, L2, L3 (512KB–varios MB) | Muy alta | Pequeña | Alto |
| 3 | RAM (2GB–32GB en PC) | Alta | Media | Medio |
| 4 | Disco duro (8GB–2TB) | Baja | Grande | Bajo |

---

## 7. Unidades de Entrada/Salida (Periféricos)

Dispositivos que se conectan al ordenador para almacenar información y comunicarse con el exterior.

| Tipo | Ejemplos |
|------|----------|
| **Entrada** | Teclado, ratón, escáner, micrófono |
| **Salida** | Monitor, impresora, altavoces |
| **Almacenamiento** | Disco duro, USB, SSD |
| **Comunicación** | Tarjeta de red, módem |

---

## 8. Arranque del Ordenador y BIOS

**BIOS** (Basic Input/Output System): Sistema básico de entrada/salida.

- Su función principal es **inicializar el hardware** del sistema antes de cargar el sistema operativo.
- Implementada en memoria **ROM (Read Only Memory)**: puede leerse y configurarse, pero no sobrescribirse directamente.

---

## 9. Software de un Ordenador

Según el estándar 729 del IEEE, el software es *"el conjunto de los programas de cómputo, procedimientos, reglas, documentación y datos asociados que forman parte de las operaciones de un sistema de computación"*.

### Tipos de software

- **Software de sistema**: Sistema operativo, drivers.
- **Software de aplicación**: Programas para el usuario (ofimática, juegos, etc.).
- **Software de programación**: Compiladores, editores de código.

### Tipos de licencia

- **Freeware**: Gratuito.
- **Shareware**: Gratuito con limitaciones; pago para versión completa.
- **Software propietario**: De pago, con restricciones de uso.
- **Software libre / Open Source**: Código abierto.

---

## 10. Sistema Operativo

Es el programa (o conjunto de programas) que controla el funcionamiento del hardware y ofrece al usuario un modo sencillo de acceso al ordenador.

### Componentes

| Componente | Función |
|------------|---------|
| **Kernel (núcleo)** | Funciones básicas: arranque, planificación de CPU, gestión de memoria, periféricos y archivos |
| **Shell (intérprete de comandos)** | Interfaz entre el usuario y el SO (línea de comandos o GUI) |
| **Sistema de archivos** | Permite registrar archivos en una estructura arbórea |

### Funciones del Sistema Operativo

1. **Simplificar el uso del hardware** al usuario mediante una interfaz.
2. **Administrar la información**: gestión del sistema de archivos y autorizaciones.
3. **Gestión de interrupciones**: prioridades entre programas e instrucciones.
4. **Administrar la memoria**: asigna espacio a aplicaciones; crea **memoria virtual** en disco si la RAM es insuficiente.
5. **Gestionar eficientemente los recursos**: reconoce componentes hardware, controla el acceso mediante drivers y asigna recursos.

---

## Ejercicios

**Ejercicio 1**: Investiga y define:
1. ¿Qué es un elemento semiconductor?
2. ¿Qué es un amplificador?
3. ¿Qué es un oscilador?
4. ¿Qué es un conmutador?

**Ejercicio 2**: Indica la secuencia a seguir al ejecutar una instrucción para los registros CP, RI, MAR y MDR.

**Ejercicio 3 (Software)**: Para los programas indicados en clase, investiga: plataforma, tipo de licencia y compañía desarrolladora.
