# Instalación de WSL2

Tradicionalmente, Windows ha proporcionado a sus usuarios una interfaz de línea de comandos que funciona bajo su propio sistema, heredado de MS-DOS y diferente a GNU/Linux, el cuál se basa en un sistema UNIX. Sin embargo, en Windows 10, con la irrupción de __Windows Subsystem for Linux__ (más comunmente denominado WSL), esto ha cambiado radicalmente.

Otros sistemas operativos como GNU/Linux o Mac, disponen de una interfaz de línea de comandos basada en UNIX, por lo que hasta el momento era bastante complejo tener compatibilidad entre sistemas. Con la adopción de WSL en Windows, Microsoft introduce una capa intermedia que funciona con un núcleo de Linux real (kernel) y en el que se pueden instalar distribuciones de GNU/Linux (desde la tienda oficial de Microsoft o de forma manual) como por ejemplo Ubuntu, Debian, Kali o incluso la distribución minimalista Alpine.

## Requisitos previos

Para poder disponer de una terminal de GNU/Linux en nuestro Windows, antes necesitamos asegurarnos que nuestro equipo cumple los siguientes requisitos:

-Necesitaremos tener Windows 10 o superior (cualquier versión salvo Windows S).

-La virtualización Hyper-V activada en la BIOS/UEFI (habitual en equipos nuevos).

-La característica Windows Subsystem for Linux activada.

-La característica Plataforma de Máquina Virtual activada.

-Se recomienda tener las actualizaciones de Windows al día para mayor compatibilidad.