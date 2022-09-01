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

En ese caso, tenemos la virtualización __Hyper-V__ activada en la BIOS y podemos saltar al siguiente punto. En caso contrario, quizás no se encuentre habilitada y debamos activarla en la BIOS. Dicha característica puede encontrarse en un menú diferente, dependiendo de la marca y modelo de la placa.

> Es posible activar esta característica desde el __Símbolo de sistema__ de Windows como administrador, escribiendo el comando __bcdedit /set hypervisorlaunchtype auto__. Para volverla a desactivar, el comando sería __bcdedit /set hypervisorlaunchtype off__.

## __Activación de características__

Por otro lado, para activar las características mencionadas anteriormente en Windows, accedemos a Inicio y buscamos __Activar o desactivar características de Windows__, donde encontraremos un menú de selección para activar las casillas __Subsistema de Windows para Linux__ y __Plataforma de máquina virtual__:

![Texto alternativo](/image/3.png)

La primera de ellas es absolutamente necesaria, puesto que es el propio __WSL__. La segunda de ellas es necesaria para utilizar __WSL2__, y es posible que no aparezca si no tienes Windows 10 actualizado. Puedes comprobarlo, accediendo a Inicio y abriendo una terminal de Windows escribiendo __CMD__ o __Símbolo de sistema__ y escribiendo lo siguiente:

```
> ver
Microsoft Windows [Versión 10.0.22000.856]
```

El comando __ver__ nos mostrará la versión instalada de Windows 10. Si es igual o superior a __10.0.19041__, podremos utilizar __WSL2__, en caso contrario, es posible que no podamos utilizar WSL (*o sólo podamos usar __WSL1__*). Para solucionarlo, revisa las actualizaciones de Windows e instala las que tengas pendientes.

> __Nota__: También es posible comprobar que versión tenemos instalada pulsando __Win+R__ y escribiendo __winver__. Si tenemos la versión 2004 o superior, podremos utilizar __WSL2__.

## __¿Qué distribuciones tengo en WSL?__
__Windows Subsystem for Linux__ funciona de modo que podemos tener varias distribuciones instaladas en nuestro sistema y utilizar la que queramos. Para ver que distribuciones tenemos instaladas, abrimos una terminal de Windows (__CMD__) y escribimos __wsl --list__:

```
> wsl --list

Distribuciones de subsistema de Windows para Linux:
Ubuntu (predeterminado)
```

> Si en lugar de aparecernos el mensaje anterior nos muestra un error por no encontrar el comando __wsl__, muy probablemente no tengamos instalada la característica __Windows Subsystem for Linux__ que mencionamos en el apartado anterior.

## __Instalar una distribución de Linux__

El primer paso que deberíamos realizar es instalar una distribución de GNU/Linux en nuestro __WSL__. Existen muchas de ellas para elegir. Personalmente suelo elegir __Debian__, aunque también hay otras distribuciones:

| Distribución  | Página oficial                        |Enlace a tienda Microsoft                                                              |Descarga manual (.appx) (MXN)                        |
|---------------|---------------------------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------|
| Debian Linux  | [Debian](https://www.debian.org/)     |[Debian MS Store](https://www.microsoft.com/es-es/p/debian/9msvkqc78pk6)               |[Debian.appx](https://aka.ms/wsl-debian-gnulinux)    |
| Ubuntu Linux  | [Ubuntu](https://ubuntu.com/)         |[Ubuntu MS Store](https://www.microsoft.com/es-es/p/ubuntu-2004-lts/9n6svws3rx71)      |[Ubuntu 20.04.appx](https://aka.ms/wslubuntu2004)    |
| Kali Linux    | [Kali](https://www.kali.org/)         |[Kali MS Store](https://www.microsoft.com/es-es/p/kali-linux/9pkr34tncv07)             |[Kali Linux.appx](https://aka.ms/wsl-kali-linux-new) |
| Open Suse     | [Open Suse](https://www.opensuse.org/)|[Open Suse MS Store](https://www.microsoft.com/es-es/p/opensuse-leap-15-1/9njfzk00fgkv)|[Open Suse.appx](https://aka.ms/wsl-opensuse-42)     |
| Alpine Linux ¹| [Alpine](https://alpinelinux.org/)    |[Alpine MS Store](https://www.microsoft.com/es-es/p/alpine-wsl/9p804crf0395)           |                                                     |

Las distribuciones se pueden instalar automáticamente desde la __tienda oficial de Microsoft__, o manualmente, ejecutando un archivo __.appx__ que contiene la distribución de Linux a instalar. Si lo hacemos de la primera forma, se instalará de forma transparente, si lo hacemos de la segunda forma, nos mostrará una ventana similar a la siguiente:

![Texto alternativo](/image/4.png)

Una vez instalada la distribución de Linux en nuestro sistema, tras esperar un corto espacio de tiempo, al iniciarla por primera vez nos aparecerá una ventana parecida a esta:

```
Installing, this may take a few minutes...
Please create a default UNIX user account. The username does not need to match your Windows username.
For more information visit: https://aka.ms/wslusers
Enter new UNIX username: juan
New password:
Retype new password:
passwd: password updated successfully
Installation successful!
juan@JUANC:~$
```

En ella, se nos preguntará el __nombre de usuario__ y su correspondiente __contraseña__ para utilizar en nuestra distribución de Linux de WSL. El nombre de usuario __debe estar en minúsculas__ y no es necesario que coincida con el nombre que tengamos en nuestra cuenta de Windows.

> Ten en cuenta que el __nombre de usuario__ que escribas va a ser el que utilizarás en WSL de forma habitual. Por ejemplo, si utilizamos el nombre de usuario __Juan__, nuestra carpeta de usuario será __/home/Juan__.

Una vez hecho esto, escribimos __exit__ (*o cerramos la ventana y volvemos a abrir un __símbolo del sistema__*). Vamos a comprobar que todo ha ido bien y tenemos una distribución instalada:

```
> wsl --list
Distribuciones de subsistema de Windows para Linux:
Ubuntu (predeterminado)
Debian
```

Como se puede ver, en nuestro caso nos aparece una distribución __Debian__ (*marcada como predeterminada*). Si instalasemos varias distribuciones las veríamos en esta lista, y podríamos seleccionar una como predeterminada escribiendo __wsl --set-default Debian o wsl -s Debian__.

## __COMANDOS__

| Distribución                                | Descripción                      
|---------------------------------------------|---------------------------------------
| __wsl__ --list --online                     | muestra una lista de las distribuciones válidas que se pueden instalar. Abreviación(__wsl__ -l -o)
| __wsl__ --list --verbose                    | muestra la lista de distribuciones con su estado actual y versión. Abreviación(__wsl__ -l -v)
| __wsl__ --update                            | Actualiza manualmente la versión de su kernel WSL Linux. También puede usar el comando: __wsl__ --update rollback para retroceder a una versión anterior del kernel de WSL Linux.  
| __wsl__ --install --distribution kali linux | ejecuta la instalación de una distribucion de linux, en este caso kali linux
