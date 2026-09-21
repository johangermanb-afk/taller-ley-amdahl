Markdown
# Taller: Ley de Amdahl y Validación de Recursos

**Curso:** Fundamentos de Computación Paralela y Distribuida  
**Autor:** Johan Germán Beltrán Acevedo  
**Fecha:** 20 de septiembre de 2026  

## Descripción
Este repositorio contiene los códigos fuente en lenguaje C utilizados para el taller práctico sobre la **Ley de Amdahl**. El objetivo de estos programas es validar el uso de los recursos de hardware (cores físicos y procesadores lógicos) comparando los tiempos de ejecución de un algoritmo de búsqueda de números primos en su versión secuencial y su versión paralela utilizando la API de OpenMP.

## Archivos en el Repositorio
* `primes_number_sequential.c`: Código base que realiza la búsqueda de números primos hasta 50.000.000 de forma estrictamente secuencial utilizando un solo núcleo.
* `primes_number_parallel.c`: Código optimizado con directivas `#pragma omp parallel for` de OpenMP para dividir la carga de trabajo entre los distintos hilos lógicos del procesador.

## Compilación y Ejecución
Para compilar y ejecutar estos archivos correctamente, es necesario contar con un compilador (como GCC) configurado con soporte para OpenMP.

### 1. Versión Secuencial
**Compilación:**
```bash
gcc primes_number_sequential.c -o primes_number_sequential
Ejecución en Windows:

PowerShell
.\primes_number_sequential.exe
2. Versión Paralela (OpenMP)
Compilación:

Bash
gcc -fopenmp primes_number_parallel.c -o primes_number_parallel
Ejecución variando hilos (Windows PowerShell):
Para cambiar la cantidad de hilos lógicos asignados a la ejecución del programa, se debe modificar la variable de entorno antes de la ejecución:

PowerShell
$env:OMP_NUM_THREADS=4; .\primes_number_parallel.exe
(Nota: Reemplazar el número 4 por la cantidad de hilos que se deseen evaluar, por ejemplo: 1, 2, 4, 6 o 12).