---
lang: es-ES
---

# Mi Cuaderno

Cuaderno del profesor para organizar grupos y alumnado, actividades, calificaciones, asistencia e informes. Autor: **Juan Luis Palmés Martín**.

## Descargar

- **[Windows x64 — descargar Mi Cuaderno 2.4.4 (.exe)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.4.4/Mi-Cuaderno-2.4.4-Windows-x64-Setup.exe)**.
- **[Mac Apple Silicon — descargar Mi Cuaderno 2.4.4 (.dmg)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.4.4/Mi-Cuaderno-2.4.4-Mac-arm64.dmg)**. Requiere M1 o posterior y macOS 11 o posterior; no es compatible con Mac Intel.
- [Ver la publicación principal, fuentes y licencias](https://github.com/JLPalmes/mi-cuaderno/releases/latest).

Windows y Mac se actualizan a **2.4.4** con las correcciones de dependencias. Ambas versiones incluyen Pincel por evaluación, observaciones, recuperaciones, registros sin ponderación y asistencia por sesiones, y admiten copias JSON de formato 3. **Las nuevas copias JSON de formato 3 no pueden importarse en Mac 2.0.2 ni en Windows hasta 2.2.1.** Se aceptan las copias antiguas y se conserva un respaldo SQLite antes de actualizar.

El instalador de Windows no tiene firma de editor. **Antes de actualizar, exporta una copia JSON externa y cierra la aplicación.** Si 2.0.3 no se cierra, exporta primero la copia y finaliza Mi Cuaderno desde el Administrador de tareas.

## Novedades de 2.4.4 para Windows y Mac

- Corregidas las dependencias DOMPurify y Tinypool; Vite actualizado a 8.1.6 y source-map-js a 1.2.2.
- Retirada la herramienta shadcn y sus dependencias indirectas. Se conserva su CSS original 4.18.0 y licencia MIT; el CSS compilado es idéntico al anterior.
- Auditoría npm sin vulnerabilidades detectadas. La alerta Cargo de glib afecta al destino Linux, que no se distribuye en estos instaladores.
- 561 pruebas automatizadas y comprobaciones de código/build. No cambian las reglas de cálculo ni el formato SQLite/JSON 3.
- Instalación y recorrido manual de los instaladores 2.4.4 pendientes del usuario. Windows sin firma de editor; Mac con firma ad hoc, sin Developer ID ni notarización.

## Novedades de Windows 2.4.3

- Comandos de arranque y compilación compatibles con Windows y Mac, sin configuración temporal para Windows.
- Un único motor de evaluación, también en las pruebas: se elimina la referencia matemática TypeScript.
- Pruebas directas de módulos de carga/guardado, grupos y deshacer; retirada la extracción AST de funciones.
- 558 pruebas correctas, TypeScript, lint, formato Rust, Clippy y empaquetado Windows verificados. Instalación manual y nuevo comando en Mac pendientes.
- Sin cambios en reglas de cálculo, datos ni formato SQLite/JSON 3. El instalador de Mac 2.4.2 continúa disponible.

## Novedades de 2.4.2 para Windows y Mac

- Formularios, edición, copias, importación y ordenación de grupos separados por responsabilidad.
- Pruebas de interfaz organizadas por flujos, conservando los casos existentes y las 553 pruebas correctas del mantenimiento.
- Versiones de PDF fijadas y comprobaciones automáticas de GitHub actualizadas.
- Se mantienen los cálculos, Pincel, recuperaciones y el formato JSON/SQLite 3 de 2.4.1. La prueba en Mac 2.4.1 fue confirmada por el usuario.
- Windows 2.4.2: 553 pruebas correctas, TypeScript, lint, formato Rust, Clippy y empaquetado NSIS verificados. Instalación y prueba manual pendientes del usuario. Windows 2.4.1 sigue en su publicación original.

## Novedades de 2.4.1 para Windows y Mac

- Motor de evaluación único en Rust, fuera del hilo principal. Retirados los restos web y la compilación Electron; se conservan sus publicaciones históricas.
- Los alumnos sin notas no cuentan como suspensos en las estadísticas; los ceros explícitos sí cuentan. Sin actividades ni un histórico acreditado se muestra «—».
- En evaluación única se ve un punto en el gráfico; con varias evaluaciones consecutivas se dibuja la evolución. Los periodos pendientes no se convierten en ceros.
- Se mantienen Pincel manual, recuperaciones, R/AP, asistencia por sesiones, PDF, copias automáticas y deshacer.
- 553 pruebas correctas, TypeScript, lint, formato Rust, Clippy, compilación y empaquetado verificados en Mac y Windows. Las pruebas manuales de Windows y Mac 2.4.1 fueron confirmadas por el usuario.

Se conserva el formato JSON/SQLite 3 de 2.3.0. Se admiten copias antiguas. **Mac 2.0.2 y Windows hasta 2.2.1 no pueden abrir las nuevas copias.** Mac 2.4.4 y Windows 2.4.4 están disponibles en sus respectivas publicaciones. Desde Windows 2.4.3 también se retira la referencia TypeScript de las pruebas; no existe un motor alternativo en la aplicación.

Las copias automáticas son opcionales, periódicas y sin cifrar. Elige una carpeta privada, preferiblemente en otro disco. No hay sincronización automática entre equipos. Exporta una copia antes de actualizar y cierra la aplicación.

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

Los cuadernos se guardan en el dispositivo. Windows 2.4.4 y Mac 2.4.4 utilizan SQLite; la copia JSON exportable permite intercambiar datos entre versiones compatibles. Las copias nuevas de formato 3 requieren versiones actualizadas en ambos equipos. Tras migrar, el almacenamiento antiguo se conserva como rescate inicial y deja de actualizarse. Esta versión no sincroniza automáticamente los datos entre equipos. Permite importar alumnado, guardar y restaurar copias y exportar informes PDF.

## Licencia y fuentes

Copyright (C) 2026 Juan Luis Palmés Martín. Software libre bajo **GNU AGPL versión 3 exclusivamente (AGPL-3.0-only)**, sin garantía en los términos de la licencia. Consulta [LICENSE](LICENSE), [COPYRIGHT.md](COPYRIGHT.md) y [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt). Las bibliotecas de terceros conservan sus propias licencias.

Este repositorio es el canal público de distribución. **El código completo de cada versión se adjunta a su publicación** en `Mi-Cuaderno-2.4.4-Mac-codigo-fuente.tar.gz` para Mac (publicación 2.4.4) y en `Mi-Cuaderno-2.4.4-Windows-codigo-fuente.tar.gz` para Windows (publicación 2.4.4), con los recursos, scripts, archivos de bloqueo y fuentes de las dependencias incorporadas. Dentro encontrarás `SOURCE_CODE.md` con las instrucciones de compilación y `SOURCE-MANIFEST.json` para identificar los archivos utilizados.

También puedes guardar esas mismas fuentes sin conexión desde **Ayuda → Licencia y código fuente → Guardar código fuente** en la aplicación.

Los archivos `SHA256SUMS-windows.txt` (Windows) y `SHA256SUMS-mac.txt` (Mac) permiten comprobar la integridad de cada distribución. `manifest-windows.json` y `manifest-mac.json` identifican sus respectivos archivos de fuentes y revisiones de base. Los avisos de dependencias de Mac están en [THIRD_PARTY_NOTICES-mac.txt](THIRD_PARTY_NOTICES-mac.txt); los de Windows se conservan en [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt).

Las licencias adjuntas se identifican como LICENSE-AGPL-3.0-windows.txt y LICENSE-AGPL-3.0-mac.txt: el texto coincide, con los finales de línea de cada plataforma.
