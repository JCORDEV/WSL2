### **¿Cuáles son exactamente las diferencias con la versión anterior?**

La diferencia fundamental entre WSL2 y su versión anterior se encuentra en la arquitectura del software. Mientras que WSL1 cuenta con una capa de compatibilidad para la transferencia de la ejecución del código entre Windows y Linux, WSL2 está basado en la virtualización de un sistema operativo Linux. La máquina virtual que se utiliza se ejecuta en el hipervisor nativo de Windows Hyper-V, que ofrece un rendimiento especialmente alto.

Mientras que el abanico de funciones de la interfaz Linux de WSL1 era limitado, WSL2 utiliza un núcleoLinux completo. Se trata de núcleo optimizado especialmente para WSL2 en cuanto a tamaño y a rendimiento, basado en el código original estable de “kernel.org”. En la práctica, este planteamiento se traduce en una aceleración de la ejecución del código por un factor de entre dos y veinte. Además, WSL2 requiere menos capacidad de memoria que la versión previa. Para los usuarios resulta especialmente útil que en el núcleo se realicen las tareas de mantenimiento como parte de las actualizaciones regulares de Windows.

Puesto que WSL1 utiliza una capa de traducción para gestionar los accesos a Linux y a Windows, algunos tipos de software especializado de Linux no pueden incluirse. Por el contrario, la virtualización del núcleo de WSL2 ofrece compatibilidad completa con los accesos al sistema. En la práctica, esto significa que los elementos de software complejo como Docker también se pueden ejecutar con WSL2. Además, desde el entorno Linux se obtiene acceso a la tarjeta gráfica, lo que resulta ventajoso sobre todo en aplicaciones con grandes conjuntos de datos, como las que se usan para el machine learning o en contextos de data science.

Aunque se recomienda la utilización de WSL2 en sistemas modernos, ambas versiones pueden funcionar en paralelo. En cada distribución Linux es posible determinar qué versión WSL se debe utilizar para el control.

### **Comparación final de las características de WSL2 y WSL1**

Como ya hemos visto, la utilización de WSL2 ofrece numerosas ventajas frente a su versión anterior. La siguiente tabla resume los puntos en común y las diferencias entre las dos versiones:

![Texto alternativo](/image/1.png)