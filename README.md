---
lang: es-ES
---

# Mi Cuaderno

Cuaderno del profesor para organizar grupos y alumnado, actividades, calificaciones, asistencia e informes. Autor: **Juan Luis Palmés Martín**.

## Descargar

- **[Windows x64 — descargar Mi Cuaderno 2.3.0 (.exe)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.3.0/Mi-Cuaderno-2.3.0-Windows-x64-Setup.exe)**.
- **[Mac Apple Silicon — descargar Mi Cuaderno 2.0.2 (.dmg)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.0.2/Mi-Cuaderno-2.0.2-arm64.dmg)**. Requiere M1 o posterior y macOS 11 o posterior; no es compatible con Mac Intel.
- [Ver la publicación principal, fuentes y licencias](https://github.com/JLPalmes/mi-cuaderno/releases/latest).

Windows está actualizado a **2.3.0**, con Pincel por evaluación, observaciones, recuperaciones y registros sin ponderación. Mac continúa en **2.0.2**, sin cambios. **Las nuevas copias JSON de formato 3 no pueden importarse en Mac 2.0.2 ni en Windows hasta 2.2.1.** Se aceptan las copias antiguas y se conserva un respaldo SQLite antes de actualizar.

El instalador de Windows no tiene firma de editor. **Antes de actualizar, exporta una copia JSON externa y cierra la aplicación.** Si 2.0.3 no se cierra, exporta primero la copia y finaliza Mi Cuaderno desde el Administrador de tareas.

## Novedades de Windows 2.3.0

- Copias automáticas opcionales en una carpeta elegida, al abrir y cada 15 minutos si hay cambios guardados. Conserva las 30 últimas gestionadas por la aplicación; no borra copias manuales, ajenas o modificadas. Un fallo no impide guardar el cuaderno.
- AP muestra las actividades suspensas y sus notas vigentes al pulsarlo, también con teclado.
- Deshacer notas, Pincel y pegados completos, sin sobrescribir otras modificaciones. La primera calificación de un campo vacío no muestra aviso; al modificar una existente, incluido cero, aparece Deshacer y **✓ OK**, sin X.
- Las faltas requieren una sesión registrada, por defecto la última introducida. Varias sesiones del mismo día son independientes y la asistencia se calcula por sesiones. Los registros antiguos sin vínculo se conservan sin computar hasta asignarlos expresamente.
- El desplegable de recuperaciones sólo ofrece actividades con alguna nota válida (incluido cero), ordenadas por evaluación, fecha y nombre.
- Ayuda con R, AP, colores, recuperaciones, Pincel y copias. Pegados en una sola actualización y optimización de estadísticas de las rutas alternativas.
- Conserva Pincel manual por evaluación (el de tercera es también el final y nunca calcula medias), observaciones por evaluación, recuperaciones y actividades sin ponderación.
- Se mantienen los colores: rojo por debajo de 5, amarillo y AP en media aprobada con actividades suspensas, verde si aprueba sin ellas. R y AP aparecen en línea, también en medias acumuladas.
- 540 pruebas correctas: 143 generales, 359 de interfaz/dominio y 38 Rust, más el benchmark Rust aparte. TypeScript y lint correctos. Sólo datos sintéticos durante la preparación, sin abrir bases reales ni ejecutar el instalador.
- Pendiente prueba manual de Windows 2.3.0: edición, OK y deshacer, carpeta externa, copia/restauración, sesiones y faltas, conservación de notas, copia/restauración, cierre y reapertura.

No cambian las fórmulas de evaluación. SQLite y JSON pasan al formato 3 con respaldo previo verificado. Las copias automáticas están desactivadas hasta elegir una carpeta en «Copia y restauración». Son periódicas, no continuas, y sólo funcionan con la aplicación abierta. Elige una carpeta privada, preferiblemente en otro disco; una carpeta de red o sincronizada puede llevar datos fuera del equipo. Los archivos contienen datos personales sin cifrar.

Mac conserva su versión 2.0.2 y no admite las copias nuevas de formato 2. Para intercambiarlas con Mac se necesita una compilación compatible, todavía pendiente. Se conservan las publicaciones anteriores. Exporta una copia manual externa antes de actualizar.

## Novedades de 2.0.2

- Actualización de seguridad del lector de hojas de cálculo a SheetJS 0.20.3, desde su distribución oficial.
- Excel y PDF se cargan al utilizarlos, aligerando la carga inicial.
- Guardado inmediato optimizado: evita volver a procesar grupos sin cambios y reescribir datos idénticos.
- Cálculos compartidos, formularios separados y más pruebas para facilitar el mantenimiento.
- Conserva las correcciones de medias, ponderaciones, Pincel e instalaciones nuevas sin alumnado de ejemplo incorporadas en 2.0.1.

## Aviso de seguridad de macOS

**Esta aplicación no dispone de una firma Developer ID de Apple ni está notarizada por Apple. Al abrirla por primera vez, macOS puede bloquearla y avisar de que no puede verificar el desarrollador o comprobar si contiene software malicioso.** La firma local utilizada para construirla no equivale a una certificación de Apple.

Consulta las [instrucciones oficiales de Apple](https://support.apple.com/es-es/102445). Si has descargado el archivo de esta página oficial y decides abrirlo, después del primer intento puedes acudir a **Ajustes del Sistema → Privacidad y seguridad → Abrir igualmente**. No es necesario desactivar globalmente las protecciones del Mac.

## Instalar

1. Si ya utilizas Mi Cuaderno, exporta y conserva una copia de tus datos antes de actualizar.
2. En Windows, ejecuta el instalador EXE. En Mac, abre el DMG y arrastra **Mi Cuaderno** a **Aplicaciones**.
3. Abre Mi Cuaderno desde el menú Inicio en Windows o desde Aplicaciones en Mac.

Si vienes de Electron 1.x, conserva su aplicación como respaldo y pasa tus datos exportando e importando una copia. Los cuadernos de ambas aplicaciones son independientes. La versión 2 conserva los datos del antiguo prototipo Tauri.

## Datos y funcionamiento

Los cuadernos se guardan en el dispositivo. Windows 2.3.0 utiliza SQLite; la copia JSON exportable permite intercambiar datos entre versiones compatibles. Las copias nuevas de formato 3 requieren versiones actualizadas en ambos equipos. Tras migrar, el almacenamiento antiguo se conserva como rescate inicial y deja de actualizarse. Esta versión no sincroniza automáticamente los datos entre equipos. Permite importar alumnado, guardar y restaurar copias y exportar informes PDF.

## Licencia y fuentes

Copyright (C) 2026 Juan Luis Palmés Martín. Software libre bajo **GNU AGPL versión 3 exclusivamente (AGPL-3.0-only)**, sin garantía en los términos de la licencia. Consulta [LICENSE](LICENSE), [COPYRIGHT.md](COPYRIGHT.md) y [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt). Las bibliotecas de terceros conservan sus propias licencias.

Este repositorio es el canal público de distribución. **El código completo de cada versión se adjunta a su publicación** en `Mi-Cuaderno-2.0.2-codigo-fuente.tar.gz` para Mac (publicación 2.0.2) y en `Mi-Cuaderno-2.3.0-codigo-fuente.tar.gz` para Windows (publicación 2.3.0), con los recursos, scripts, archivos de bloqueo y fuentes de las dependencias incorporadas. Dentro encontrarás `SOURCE_CODE.md` con las instrucciones de compilación y `SOURCE-MANIFEST.json` para identificar los archivos utilizados.

También puedes guardar esas mismas fuentes sin conexión desde **Ayuda → Licencia y código fuente → Guardar código fuente** en la aplicación.

El archivo `SHA256SUMS.txt` permite comprobar la integridad de los archivos publicados. `manifest-windows.json` en Windows y `manifest.json` en Mac identifican el archivo de fuentes y su revisión de base.
