[⬅️ Volver a "Conceptos de Ladder"](https://github.com/SantiagoBaeza/Conceptos-importantes-de-Ladder/tree/main)

# Uso de flancos positivos y negativos en PLC – Enclavamiento de motores

Este proyecto muestra cómo utilizar las funciones de **flanco positivo (|P|)** y **flanco negativo (|N|)** en programación de PLCs para controlar salidas de manera más precisa.  
A diferencia de las bobinas normales, los flancos permiten detectar **cambios de estado puntuales** (0→1 o 1→0) y ejecutar acciones únicas, evitando repeticiones en cada ciclo de scan del PLC.

---

## Contexto

En el [repositorio anterior](https://github.com/SantiagoBaeza/Uso-de-funciones-SET-y-RESET-en-PLC/tree/main) se trabajó con la repetición de bobinas de salida en distintos segmentos.  
En este nuevo ejercicio se retoma el mismo esquema de enclavamiento de motores, pero se incorpora el uso de **flancos positivos y negativos** junto con las instrucciones **SET (S)** y **RESET (R)**.  

Esto permite que el motor se active solo en el instante de presionar el botón (evento de flanco positivo), y se desactive con un botón de reset, evitando que la salida dependa del estado sostenido del botón.

---

## Capturas

- **Captura 01**: Seleccion de flanco positivo.  
  ![Segmento 1 – Enclavamiento clásico](https://github.com/SantiagoBaeza/Uso-de-flancos-positivos-y-negativos-en-PLC/blob/main/01%20captura%20de%20la%20opcion%20de%20flancos%20.jpg)

- **Captura 02**: Inicio de la simulacion.  
  ![Segmento 2 y 3 – Flanco positivo y Reset](https://github.com/SantiagoBaeza/Uso-de-flancos-positivos-y-negativos-en-PLC/blob/main/02%20captura%20inicio%20de%20simulacion%20.jpg)
La bobina de motor 3 aparece como encendida ya que (no lo mostre) al inicio de la simulacion realice la accion de presionar "start button" y dejar de presionarlo, para luego presionar "stop button".

---

## Funcionalidad

- **Flanco positivo (|P|):** detecta el cambio de 0→1 y dispara la acción una sola vez.  
- **Flanco negativo (|N|):** detecta el cambio de 1→0 y dispara la acción una sola vez.  
- **SET (S):** activa la salida y la mantiene energizada hasta que se ejecute un RESET.  
- **RESET (R):** desactiva la salida cuando se cumple la condición de apagado.  
- Permite convertir señales sostenidas en **eventos únicos**, evitando repeticiones en cada ciclo del PLC.  
- Simplifica el enclavamiento de motores y mejora la robustez de la lógica.

---

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)  
- Lógica en escalera (LAD)

---

## Comentarios finales

Este ejercicio demuestra cómo los **flancos positivos y negativos** pueden integrarse con las funciones **SET y RESET** para controlar motores de manera más profesional.  
El uso de flancos convierte una señal sostenida en un evento único, lo que evita repeticiones y facilita la sincronización de múltiples salidas.  

El profesor aclaró que aplicar directamente el flanco sobre la entrada es una **mala práctica**; se hizo aquí solo para fines didácticos. Más adelante se verá cómo implementarlo correctamente mediante bloques de flancos.  

El [archivo del proyecto](https://github.com/SantiagoBaeza/Uso-de-flancos-positivos-y-negativos-en-PLC/blob/main/06%20uso%20de%20flancos%20positivos%20y%20negativos.ap16) está incluido en este repositorio para que cualquier persona con acceso a **TIA Portal V16** pueda abrirlo y realizar la simulación.  
Este ejercicio tiene como objetivo servir de práctica y dejar registro de mis avances en programación de PLC.

---

> 🧩 Estos espacios están en construcción y se actualizan de forma frecuente.
