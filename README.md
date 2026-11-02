---
lang: es-ES
---

# Mi Cuaderno

Cuaderno del profesor para organizar grupos y alumnado, actividades, calificaciones, asistencia e informes. Autor: **Juan Luis Palmés Martín**.

## Descargar

- **[Windows x64 — descargar Mi Cuaderno 2.4.1 (.exe)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.4.1/Mi-Cuaderno-2.4.1-Windows-x64-Setup.exe)**.
- **[Mac Apple Silicon — descargar Mi Cuaderno 2.0.2 (.dmg)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.0.2/Mi-Cuaderno-2.0.2-arm64.dmg)**. Requiere M1 o posterior y macOS 11 o posterior; no es compatible con Mac Intel.
- [Ver la publicación principal, fuentes y licencias](https://github.com/JLPalmes/mi-cuaderno/releases/latest).

Windows está actualizado a **2.4.1**, con Pincel por evaluación, observaciones, recuperaciones y registros sin ponderación. Mac continúa en **2.0.2**, sin cambios. **Las nuevas copias JSON de formato 3 no pueden importarse en Mac 2.0.2 ni en Windows hasta 2.2.1.** Se aceptan las copias antiguas y se conserva un respaldo SQLite antes de actualizar.

El instalador de Windows no tiene firma de editor. **Antes de actualizar, exporta una copia JSON externa y cierra la aplicación.** Si 2.0.3 no se cierra, exporta primero la copia y finaliza Mi Cuaderno desde el Administrador de tareas.

## Novedades de Windows 2.4.1

- Motor de evaluación único en Rust, fuera del hilo principal. Retirados los restos web y la compilación Electron; se conservan sus publicaciones históricas.
- Los alumnos sin notas no cuentan como suspensos en las estadísticas; los ceros explícitos sí cuentan. Sin actividades ni un histórico acreditado se muestra «—».
- En evaluación única se ve un punto en el gráfico; con varias evaluaciones consecutivas se dibuja la evolución. Los periodos pendientes no se convierten en ceros.
- Se mantienen Pincel manual, recuperaciones, R/AP, asistencia por sesiones, PDF, copias automáticas y deshacer.
- 553 pruebas correctas, TypeScript, lint, Clippy, compilación y empaquetado Windows verificados. Prueba manual Windows confirmada por el usuario.

Se conserva el formato JSON/SQLite 3 de 2.3.0. Se admiten copias antiguas. **Mac 2.0.2 y Windows hasta 2.2.1 no pueden abrir las nuevas copias.** Mac no se actualiza en esta entrega. La referencia TypeScript queda sólo en pruebas; no existe un motor alternativo en la aplicación.

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

Los cuadernos se guardan en el dispositivo. Windows 2.4.1 utiliza SQLite; la copia JSON exportable permite intercambiar datos entre versiones compatibles. Las copias nuevas de formato 3 requieren versiones actualizadas en ambos equipos. Tras migrar, el almacenamiento antiguo se conserva como rescate inicial y deja de actualizarse. Esta versión no sincroniza automáticamente los datos entre equipos. Permite importar alumnado, guardar y restaurar copias y exportar informes PDF.

## Licencia y fuentes

Copyright (C) 2026 Juan Luis Palmés Martín. Software libre bajo **GNU AGPL versión 3 exclusivamente (AGPL-3.0-only)**, sin garantía en los términos de la licencia. Consulta [LICENSE](LICENSE), [COPYRIGHT.md](COPYRIGHT.md) y [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt). Las bibliotecas de terceros conservan sus propias licencias.

Este repositorio es el canal público de distribución. **El código completo de cada versión se adjunta a su publicación** en `Mi-Cuaderno-2.0.2-codigo-fuente.tar.gz` para Mac (publicación 2.0.2) y en `Mi-Cuaderno-2.4.1-codigo-fuente.tar.gz` para Windows (publicación 2.4.1), con los recursos, scripts, archivos de bloqueo y fuentes de las dependencias incorporadas. Dentro encontrarás `SOURCE_CODE.md` con las instrucciones de compilación y `SOURCE-MANIFEST.json` para identificar los archivos utilizados.

También puedes guardar esas mismas fuentes sin conexión desde **Ayuda → Licencia y código fuente → Guardar código fuente** en la aplicación.

El archivo `SHA256SUMS.txt` permite comprobar la integridad de los archivos publicados. `manifest-windows.json` en Windows y `manifest.json` en Mac identifican el archivo de fuentes y su revisión de base.
