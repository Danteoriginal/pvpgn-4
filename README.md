Player versus Player Gaming Network
=====
![](http://i.imgur.com/LfI3hXo.png)

Próxima generación de PvPGN &mdash; Battle.net<sup> v1.0</sup> Emulador de servidor de juegos.

*El proyecto aún está en desarrollo. Manténgase informado y reporte cualquier error!*

[Deleaker](http://www.deleaker.com/) Nos ayuda a encontrar fugas

[![Build Status](https://travis-ci.org/pvpgn/pvpgn-server.svg?branch=master)](https://travis-ci.org/pvpgn/pvpgn-server) [![Build status](https://ci.appveyor.com/api/projects/status/dqoj9lkvhfwthmn6)](https://ci.appveyor.com/project/HarpyWar/pvpgn)



Cambios en el código fuente (since v1.99)
--
* Soporte de secuencias de comandos Lua (WITH_LUA directiva cmake)
* Añadir iconos personalizados de visualización depende de una calificación de usuario, salida personalizada para el comando `/ stats`; Trabaja con Warcraft y Starcraft (ver [icons.conf](https://github.com/pvpgn/pvpgn-server/blob/master/conf/icons.conf.in)) <sup>commits [1](https://github.com/pvpgn/pvpgn-server/commit/c11af352603e18acc52102ba8574776425248331), [2](https://github.com/pvpgn/pvpgn-server/commit/368c4b9296d18a515af746b65fe69054ab6f4236), [3](https://github.com/pvpgn/pvpgn-server/commit/f1a96c392055a777b48dc4d77631c5e906161e28)</sup>
* Arreglo de enviao de inundación<sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/74f9e4faafe24699597e4be5bfda83bf255ba72e)</sup>
* Corregido error de compilación cuando el tamaño del puntero es mayor que int <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/1ea116434ce009bad4903ff72bd69bbb8987ce06)</sup>
* Repararado Warcraft 3 ICON SWITCH hack <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/84811bcfe875d6c42cd8271bbdae757f0b5d445b)</sup>
* Corregido los campos de ahorro de sql con los caracteres de encargo en el nombre <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/18713ffe35cbe9a12193e5c1f1caf5031d4c4731)</sup>
* Corregido los errores de salida status.xml y añadir un nuevo campo de identificación del juego
* Texto de bienvenida para Warcraft 3 se mueve desde el código en un nuevo archivo `bnmotd_w3.txt` ([ejemplo](http://img21.imageshack.us/img21/1808/j2py.png) Con texto coloreado incluido)
 <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/ff8ca941cd7942bab201607fbc31382837a35617)</sup>
* Característica para usar el carácter d2s como una plantilla para un nuevo personaje en newbie.save; Cada clase de personaje puede tener su propia plantilla <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/20)</sup>
* Localización completa <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/13)</sup>
* Ignorar la protección contra inundaciones para usuarios y bots reservados <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/49)</sup>
* Varias correcciones de errores que permiten a los hackers bloquear un servidor y un cliente de juego
* Registro de comandos de usuario <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/47)</sup>
* SID_READMEMORY implementacion <sup>[issue](https://github.com/pvpgn/pvpgn-server/pull/26)</sup>
* SID_EXTRAWORK implementacion <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/72)</sup>
* Mejorar el rendimiento del almacenamiento SQL <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/85)</sup>

Nuevos comandos
--
* `/save` Inmediatamente guardar los cambios de las cuentas y los clanes de la caché a un almacenamiento (útil para la prueba) <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/be8d65d16f910b2090b0db9e7eb2c043b816dae7)</sup>
* `/icon <add|del|list>` Icono implementación stash - cada usuario tiene su propio escondite con iconos, admin / operador puede agregar icono a los usuarios stash, puede configurar aliases para los iconos en config; Trabaja con Warcraft y Starcraft <sup>commits [1](https://github.com/pvpgn/pvpgn-server/commit/1ade081c6b10a3e710130b88613b71b880ba0cd7), [2](https://github.com/pvpgn/pvpgn-server/commit/36deb1179bca931bd6585c2b6dbf7d8ade08bc8e)</sup>
* `/find <substr of username>` Búsqueda de Cuenta  por parte del nombre - [patch #1526](http://developer.berlios.de/patch/?func=detailpatch&patch_id=1526&group_id=2291) de berlios <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/c229c6693b3dd55f02fe3a81403870044c0786b2)</sup>
* `/quiz` Trivia Quiz Game (implementacion en Lua) <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/ee04fdd23dfef90f0b852a6e90df23c7f5edc08e)</sup>
* `/language <name>` Cambia Tu Lenguaje
* `/log` Mostrar / buscar en el registro de usuario

Modificacion de comandos
--
* `/set` Exclusión para obtener / establecer una contraseña hash e id de usuario; Función de llave vacía con valor "nulo"; Más información en la salida del comando y ejemplos <sup>commits [1](https://github.com/pvpgn/pvpgn-server/commit/d96e1029478d92f67000761983e83ccfde2abbdf), [2](https://github.com/pvpgn/pvpgn-server/commit/1ade081c6b10a3e710130b88613b71b880ba0cd7#diff-ef576b6b7e90128c3718523eaaf1b894R4716)</sup>
* `/finger` Más información en la salida del comando - [patch #2859](http://developer.berlios.de/patch/?func=detailpatch&patch_id=2859&group_id=2291) from berlios <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/bdb450084704da1f33e28c9edd3d2d16b720a946)</sup>
* `/games lobby` Mostrar juegos sólo en el vestíbulo- [patch #3235](http://developer.berlios.de/patch/?func=detailpatch&patch_id=3235&group_id=2291) de berlios <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/5d27cece2c24b5fe779f1560162a31442bf02617)</sup>
* `/friends online` Mostrar solo amigos en línea - [patch #3236](http://developer.berlios.de/patch/?func=detailpatch&patch_id=3236&group_id=2291) de berlios <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/8762667276b535d3385d51941d41d780089a7049)</sup>
* `/topic` Función para configurar el texto en una nueva línea <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/6)</sup>
* `/ Alert <message>` like / announce pero muestra un cuadro de mensaje en lugar de un texto<sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/15)</sup>
* `/rehash <modo>` Función para onfiguaracion de reinicio por separado <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/ee04fdd23dfef90f0b852a6e90df23c7f5edc08e)</sup>


Cambios menores
-
* Añadir archivos MOTD originales con codificación UTF-8
* Añadir archivos de soporte v1.2, no hay necesidad de descargarlo por separado después de instalar
* Añadir soporte ODBC para CMake
* Añadir la última versioncheck.conf
* Skip_versioncheck, allow_bad_version está habilitado de forma predeterminada en bnetd.conf - para un inicio fácil
* El código fuente está formateado para una mejor lectura
* Los archivos no utilizados se eliminan, sólo pvpgn fuente aquí
* Los paquetes udp desconocidos se registran sólo con el modo de depuración habilitado (siempre bloquea un archivo de registro antes) <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/c39f9f03159b2edc8d2457d8134d84486378f9b1)
* Agregada una ubicación de archivo para todos los archivos de texto como MOTD (a menudo un administrador del servidor no sabe dónde se encuentra un archivo)
* Agregada opcion ignorar-version para los programas ** bnchat ** y ** bnstat ** - [patch #3184](http://developer.berlios.de/patch/?func=detailpatch&patch_id=3184&group_id=2291) from berlios <sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/a1fb914c30d9d69d062e8f698f7d0e9bacf41367)
* La ayuda para todos los comandos se muestra desde bnhelp.conf y el formato cambió para una mejor lectura, actualizó más mensajes de ayuda <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/5)</sup>
* Corregido error en el registro cuando el usuario envía un mensaje con longitud de texto de 255 símbolos<sup>[commit](https://github.com/pvpgn/pvpgn-server/commit/af2baccdb8a2b624627caa94eac5595ac8f76e07)</sup>
* Actualizar los servidores de seguimiento por defecto en la configuración, la traza está habilitada de forma predeterminada <sup>issues [1](https://github.com/pvpgn/pvpgn-server/issues/7), [2](https://github.com/pvpgn/pvpgn-server/issues/18)</sup>
* Corregida la identificación de la versión de Windows <sup>[issue](https://github.com/pvpgn/pvpgn-server/issues/60#issuecomment-49385463)</sup>
* Reorganizar las rutas de instalación de unix, añadir la función `make uninstall` <sup>[issue](https://github.com/pvpgn/pvpgn-server/pull/80)</sup>


Generar código fuente
--

#### Windows
Use [Magic Builder](https://github.com/pvpgn/pvpgn-server-magic-builder). 

#### Linux
[Русский](http://harpywar.com/?a=articles&b=2&c=1&d=74) | [English](http://harpywar.com/?a=articles&b=2&c=1&d=74&lang=en)

[![Vimeo](http://habrastorage.org/storage3/48c/5a9/4b1/48c5a94b1173242e311f8376be80a585.png)](https://vimeo.com/83763862)
