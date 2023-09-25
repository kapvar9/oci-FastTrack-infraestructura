# Explorar un compartimento en OCI

## Aprendamos un poco sobre la arquitectura de OCI

<p align="justify">
La arquitectura de OCI está compuesta de 3 partes: Regiones, Dominios de Disponibilidad o Availability Domains (AD) y Fault Domain o Dominio de Fallo (FD). Esta arquitectura está diseñada para lograr un alta disponibilidad y confiabilidad de las cargas de trabajo críticas de los clientes. 

![imagen](../Lab1-Compartimentos/Imagenes/lab1-1.png)

Veamos un poco más en que consiste cada una 🤓⤵️

### Regiones
Oracle Cloud Infrastructure se encuentra alojado en regiones y dominios de disponibilidad. Una región es un área geográfica específica. Cada región está compuesta por uno o más dominios de disponibilidad. La mayoría de los recursos de Oracle Cloud Infrastructure son específicos de la región, como una red de nube virtual (VCN), o específicos del dominio de disponibilidad, como una instancia de cómputo.

Las regiones son completamente independientes de otras regiones y pueden estar separadas por grandes distancias, incluso entre países o continentes. Por lo general, desplegaría una aplicación en la región donde se utiliza más, ya que utilizar recursos cercanos es más rápido que utilizar recursos distantes. Sin embargo, también puede desplegar aplicaciones en diferentes regiones para:

- Mitigar el riesgo de eventos en toda la región, como grandes sistemas climáticos o terremotos.
- Cumplir con diversos requisitos legales, fiscales y otros criterios comerciales o sociales en distintas jurisdicciones.

### Dominios de Disponibilidad o Availability Domains (AD)

En una región, puede haber hasta tres dominios de disponibilidad (ADs).

Los dominios de disponibilidad en la misma región están interconectados mediante una red de baja latencia y alta capacidad, lo que permite proporcionar conectividad de alta disponibilidad a Internet y a las instalaciones del cliente, así como construir sistemas replicados en varios dominios de disponibilidad para lograr alta disponibilidad y recuperación ante desastres.

Los dominios de disponibilidad están aislados entre sí, son tolerantes a fallos y es muy poco probable que fallen simultáneamente. Dado que los dominios de disponibilidad no comparten infraestructura, como energía o refrigeración, ni la red interna de dominio de disponibilidad, una falla en un dominio de disponibilidad en una región probablemente no afectará la disponibilidad de otros en la misma región.

### Fault Domain o Dominio de Fallo (FD)

Un dominio de fallos es una agrupación de hardware e infraestructura en un dominio de disponibilidad. Cada AD está compuesto de 3 FDs. Los dominios de fallo le permiten distribuir las instancias de modo que no se encuentren en el mismo hardware físico dentro de un único dominio de disponibilidad. Como resultado, un fallo de hardware o mantenimiento de hardware que afecta un dominio de fallos no afecta a las instancias de otros dominios de fallos.

### Trabajar con compatimentos (Compartments)

</p>
