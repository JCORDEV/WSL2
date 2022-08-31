<style>span{color: #3b63db;}</style>

# __Instalación de WSL2__

Tradicionalmente, Windows ha proporcionado a sus usuarios una interfaz de línea de comandos que funciona bajo su propio sistema, heredado de MS-DOS y diferente a GNU/Linux, el cuál se basa en un sistema UNIX. Sin embargo, en Windows 10, con la irrupción de __Windows Subsystem for Linux__ (más comunmente denominado WSL), esto ha cambiado radicalmente.

Otros sistemas operativos como GNU/Linux o Mac, disponen de una interfaz de línea de comandos basada en UNIX, por lo que hasta el momento era bastante complejo tener compatibilidad entre sistemas. Con la adopción de __WSL__ en Windows, Microsoft introduce una capa intermedia que funciona con un __núcleo de Linux real__ (kernel) y en el que se pueden instalar distribuciones de GNU/Linux (desde la tienda oficial de Microsoft o de forma manual) como por ejemplo __Ubuntu__, __Debian__, __Kali__ o incluso la distribución minimalista __Alpine__.

## __Requisitos previos__

Para poder disponer de una terminal de GNU/Linux en nuestro Windows, antes necesitamos asegurarnos que nuestro equipo cumple los siguientes requisitos:

- Necesitaremos tener __Windows 10 o superior__ (cualquier versión salvo Windows S).

- La __virtualización Hyper-V__ activada en la BIOS/UEFI (habitual en equipos nuevos).

- La característica __Windows Subsystem for Linux__ activada.

- La característica __Plataforma de Máquina Virtual__ activada.

- Se recomienda tener las __actualizaciones de Windows__ al día para mayor compatibilidad.

Recientemente, Microsoft ha añadido una forma automática de instalar __WSL__ en nuestro sistema WSL, por lo que te recomiendo echarle un vistazo a esta instalación automática antes de nada, para ahorrarnos pasos si es posible.

## __Instalación automática__
Desplegamos el menú de __Inicio__ y escribimos __Símbolo de Sistema__, pulsamos con botón derecho y seleccionamos __Ejecutar como Administrador__. Nos aparece una terminal de texto, donde escribiremos <span>__wsl --install -d Debian__</span>. Personalmente, prefiero Debian, pero en el caso de querer instalar Ubuntu, simplemente omitimos el <span>__-d Debian__</span> y escribimos simplemente <span>__wsl --install__</span>.

Una vez hecho esto, reiniciamos la máquina. Esto realizará los pasos necesarios para tener __WSL__:

- Habilitar las características opcionales necesarias.
- Descargar el último kernel de Linux más reciente.
- Establecer WSL2 como predeterminado.
- Instalar Debian (o Ubuntu) como distribución de Linux en WSL.

## __Instalación manual__

Si por alguna razón no te ha funcionado la __instalación automática__ (o no te sirve el comando <span>__wsl --install -d Debian__</span>) detallo a continuación los pasos que habría seguir para hacerla manualmente.

### __Virtualización Hyper-V__

En la BIOS/UEFI del equipo, debes tener activada la característica __Virtualización Hyper-V__ o __Hyper-threading virtualization__. Para comprobar si la tenemos activada, pulsamos <span>__CTLR__+__ALT__+__SUPR__</span> y vamos al __Administrador de tareas__, a la pestaña __Rendimiento__. Si marcamos __CPU__, en las opciones inferiores podremos ver un texto que dice __Virtualización: Habilitado__:

![Texto alternativo](/image/2.png)