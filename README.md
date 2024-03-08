# Windows10_Debloater
Elimina todas las app que vienen por default al instalar win10
Debloatador de Windows10
hecho con powershell Licencia: MIT

Script/Utilidad/Aplicación para desbloquear Windows 10, eliminar aplicaciones innecesarias preinstaladas de Windows, detener algunas funciones de telemetría, evitar que Cortana se use como índice de búsqueda, deshabilitar tareas programadas innecesarias y más...

Dona una taza de café
Cómprame un café

Asegúrese de consultar los GitHubs de los contribuyentes para ver si también tienen patrocinio de GitHub, ya que han contribuido a este proyecto de código abierto. ( https://github.com/Sycnex/Windows10Debloater/graphs/contributors )

Descargo de responsabilidad
ADVERTENCIA: ¡ NO me hago responsable de lo que pueda sucederle a su sistema! ¡Ejecute scripts bajo su propia responsabilidad! Además, otras variantes de este repositorio no son técnicamente versiones "nuevas" de este, pero son diferentes en sus respectivas formas. Hay algunos sitios que dicen que otros proyectos son versiones "nuevas" de esto, pero eso es inexacto.

Cómo ejecutar los archivos Windows10Debloater.ps1 y Windows10DebloaterGUI.ps1
Existen diferentes métodos para ejecutar el script de PowerShell. Los métodos son los siguientes:

Primer método
Descargue el archivo .zip en la página principal de GitHub y extraiga el archivo .zip a la ubicación deseada
Una vez extraído, abra PowerShell (o PowerShell ISE ) como administrador
Habilitar la ejecución de PowerShell Set-ExecutionPolicy Unrestricted -Force
Cuando se le solicite, cambie al directorio donde extrajo los archivos: por ejemplo, -cd c:\temp
A continuación, para ejecutar cualquiera de los scripts, ingrese lo siguiente: por ejemplo, -.\Windows10DebloaterGUI.ps1
Segundo método
Descargue el archivo .zip en la página principal de GitHub y extraiga el archivo .zip a la ubicación deseada
Haga clic derecho en el archivo PowerShell que desea ejecutar y haga clic en "Ejecutar con PowerShell".
Esto permitirá que el script se ejecute sin tener que realizar los pasos anteriores, pero Powershell le preguntará si está seguro de que desea ejecutar este script.
Recuerde que este script NECESITA ejecutarse como administrador para funcionar correctamente.

Cómo ejecutar el archivo Windows10SysPrepDebloater.ps1
Para el archivo WindowsSysPrepDebloater.ps1, hay un par de parámetros que puede ejecutar para especificar qué funciones se utilizan. Los parámetros son -SysPrep: -Debloaty -Privacy.

Para ejecutar esto con parámetros, haga lo siguiente:

Descargue el archivo .zip en la página principal de GitHub y extraiga el archivo .zip a la ubicación deseada
Una vez extraído, abra PowerShell (o PowerShell ISE ) como administrador
Cuando se le solicite, cambie al directorio donde extrajo los archivos: por ejemplo, -cd c:\temp
A continuación, para ejecutar cualquiera de los scripts, ingrese lo siguiente:
p.ej -.\Windows10SysPrepDebloater.ps1 -Sysprep -Debloat -Privacy

Aplicación Sysprep, interactiva y GUI
Ahora hay 3 versiones de Windows10Debloater : hay una versión interactiva, una versión de aplicación GUI y una versión puramente silenciosa.

Windows10SysPrepDebloater.ps1-> La versión silenciosa ahora utiliza los parámetros de cambio: -Sysprep, -Debloat -Privacy. La versión silenciosa puede ser útil para implementar imágenes MDT/sysprepping o cualquier otra forma de implementar Windows 10. Esto funcionará para eliminar el bloatware durante el proceso de implementación.

Windows10Debloater.ps1-> Esta versión interactiva es lo que implica: un script Windows10Debloater con indicaciones interactivas. Éste no debe usarse para implementaciones que requieran un script silencioso con parámetros opcionales. Este script le ofrece opciones con indicaciones a medida que se ejecuta para que pueda elegir lo que hace el script.

Windows10DebloaterGUI.ps1-> Ahora hay una aplicación GUI llamada Windows10DebloaterGUI.ps1 con botones para realizar todas las funciones que realizan los scripts. Esto es mejor para el usuario promedio que no quiere trabajar con código o si prefiere simplemente ver la pantalla de una aplicación.

Cambiar parámetros
Hay 3 parámetros de cambio en el Windows10SysPrepDebloater.ps1script.

-SysPrep, que ejecuta el comando dentro de una función: get-appxpackage | eliminar-appxpackage. Esto es útil ya que algunos administradores necesitan que ese comando se ejecute primero para que las máquinas puedan aprovisionar correctamente las aplicaciones para su eliminación.

-Debloat, cambie el parámetro que hace lo que sugiere. Ejecuta las siguientes funciones: Iniciar-Desbloat, Quitar claves y Proteger-Privacidad. Remove-Keys elimina las claves de registro sobrantes que están asociadas con las aplicaciones de bloatware enumeradas anteriormente, pero que no se eliminan durante la función Start-Debloat.

-Privacy, agrega y/o cambia claves de registro para detener algunas funciones de telemetría, evita que Cortana se use como índice de búsqueda, desactiva tareas programadas "innecesarias" y más.

Este script eliminará el bloatware de Windows 10 cuando se use Remove-AppXPackage/Remove-AppXProvisionedPackage y luego eliminará claves de registro específicas que no se eliminaron de antemano. Para obtener mejores resultados, este script debe ejecutarse antes de configurar un perfil de usuario; de lo contrario, es probable que vea que las aplicaciones que deberían haberse eliminado permanecerán y, si se eliminan, encontrará mosaicos rotos en el menú de inicio.

Estas claves de registro son
EclipseManager, ActiproSoftwareLLC, Microsoft.PPIProjection, Microsoft.XboxGameCallableUI

Puede elegir entre 'Desinflar' o 'Revertir'. Dependiendo de su elección, cualquiera de los dos ejecutará un código específico para desbloquear su máquina con Windows 10.

La opción del interruptor Debloat ejecuta las siguientes funciones
Desbloat, Remove-Keys, Protect-Privacy, Stop-EdgePDF (si se elige)

La opción Revertir interruptor ejecuta las siguientes funciones
Revertir cambios, habilitar EdgePDF

La opción Revertir reinstala el bloatware y cambia las claves de registro a las predeterminadas.

Las tareas programadas que están deshabilitadas son
XblGameSaveTaskLogon, XblGameSaveTask, Consolidator, UsbCeip, DmClient

Estas tareas programadas que están deshabilitadas no tienen ningún impacto en el funcionamiento del sistema operativo.

Bloaware que se elimina
3DBuilder , ActiproSoftware , Alarmas , Appconnector , Asphalt8 , Autodesk SketchBook , MSN Money , Comida y bebida , Salud y bienestar , Microsoft News , MSN Sports , MSN Travel , MSN Weather , BioEnrollment, Windows Camera , CandyCrush, CandyCrushSoda, Caesars Slots Free Casino, ContactSupport, CyberLink MediaSuite Essentials, DrawboardPDF, Duolingo, EclipseManager, Facebook, FarmVille 2 Country Escape, Flipboard, Fresh Paint, Primeros pasos, iHeartRadio, King apps, Mapas, March of Empires, Mensajería, Microsoft Office Hub, Microsoft Solitaire Collection, Microsoft Sticky Notas, Minecraft, Netflix, Prueba de velocidad de red, Crucigrama del NYT, Office Sway, OneNote, OneConnect, Pandora, Personas, Teléfono, Phototastic Collage, PicsArt-PhotoStudio, PowerBI, Royal Revolt 2, Shazam, Skype para escritorio, SoundRecorder, TuneInRadio, Twitter , aplicaciones de comunicaciones de Windows, comentarios de Windows, centro de comentarios de Windows, lista de lectura de Windows, XboxApp, Xbox Game CallableUI, proveedor de identidad de Xbox, Zune Music, Zune Video.

enlace de descarga rápida
iwr -useb https://git.io/debloat|iex

Lista de permitidos y lista de bloqueo
Puede haber cierta confusión, pero cuando se utiliza la lista de permitidos/lista de bloqueo, la marca de verificación significa que está en la lista de bloqueo y que se eliminará.

Créditos
Gracias a a60wattfish , abulgatz , xsisbest , Damian , Vikingat-RAGE , usuario de Reddit /u/GavinEke y a todos los contribuyentes ( https://github.com/Sycnex/Windows10Debloater/graphs/contributors ) por las sugerencias, el código, cambios y correcciones en las que todos ustedes han trabajado arduamente y compartido amablemente. ¡Todos habéis hecho un trabajo fantástico!
