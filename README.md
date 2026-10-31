---
lang: es-ES
---

# Mi Cuaderno

Cuaderno del profesor para organizar grupos y alumnado, actividades, calificaciones, asistencia e informes. Autor: **Juan Luis Palmés Martín**.

## Descargar

- **[Windows x64 — descargar Mi Cuaderno 2.0.9 (.exe)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.0.9/Mi-Cuaderno-2.0.9-Windows-x64-Setup.exe)**.
- **[Mac Apple Silicon — descargar Mi Cuaderno 2.0.2 (.dmg)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.0.2/Mi-Cuaderno-2.0.2-arm64.dmg)**. Requiere M1 o posterior y macOS 11 o posterior; no es compatible con Mac Intel.
- [Ver la publicación principal, fuentes y licencias](https://github.com/JLPalmes/mi-cuaderno/releases/latest).

Windows está actualizado a **2.0.9**, con Rust como motor de resultados de evaluación, control de errores y reintento, conservando SQLite y las copias JSON. Mac continúa en **2.0.2**; esta actualización no cambia su instalador ni incorpora todavía SQLite a esa compilación.

El instalador de Windows no tiene firma de editor. **Antes de actualizar, exporta una copia JSON externa y cierra la aplicación.** Si 2.0.3 no se cierra, exporta primero la copia y finaliza Mi Cuaderno desde el Administrador de tareas.

## Novedades de Windows 2.0.9

- Rust es el único motor de resultados de evaluación en Tauri: se retira el respaldo TypeScript de las pantallas y los informes nativos.
- Espera máxima de 15 segundos y reintento manual. Si el cálculo no está disponible se muestra «—», sin ceros inventados ni resultados de otro grupo.
- La edición y las copias siguen disponibles; la espera conserva el foco al escribir notas.
- Los informes PDF necesitan un cálculo válido y gestionan errores sin anunciar éxitos falsos.
- Conserva estadísticas, informe individual y evaluación de sesiones de la versión anterior. Se mantiene SQLite, formato JSON, identidad y ubicación de los datos.
- Web/Electron y las pruebas de equivalencia mantienen TypeScript. Asistencia y actualización de históricos siguen en TypeScript; no se ha trasladado toda la lógica de negocio a Rust.
- 416 pruebas correctas: 139 generales, 253 de interfaz y 24 Rust. TypeScript y lint completo correctos.
- Pendiente la prueba manual de Windows 2.0.9, especialmente edición, reintento, cambio de grupo e informes. No se ejecuta el instalador durante su preparación.

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

Los cuadernos se guardan en el dispositivo. Windows 2.0.9 utiliza SQLite; la copia JSON exportable sigue siendo el formato portátil entre versiones y equipos. Tras migrar, el almacenamiento antiguo se conserva como rescate inicial y deja de actualizarse. Esta versión no sincroniza automáticamente los datos entre equipos. Permite importar alumnado, guardar y restaurar copias y exportar informes PDF.

## Licencia y fuentes

Copyright (C) 2026 Juan Luis Palmés Martín. Software libre bajo **GNU AGPL versión 3 exclusivamente (AGPL-3.0-only)**, sin garantía en los términos de la licencia. Consulta [LICENSE](LICENSE), [COPYRIGHT.md](COPYRIGHT.md) y [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt). Las bibliotecas de terceros conservan sus propias licencias.

Este repositorio es el canal público de distribución. **El código completo de cada versión se adjunta a su publicación** en `Mi-Cuaderno-2.0.2-codigo-fuente.tar.gz` para Mac (publicación 2.0.2) y en `Mi-Cuaderno-2.0.9-codigo-fuente.tar.gz` para Windows (publicación 2.0.9), con los recursos, scripts, archivos de bloqueo y fuentes de las dependencias incorporadas. Dentro encontrarás `SOURCE_CODE.md` con las instrucciones de compilación y `SOURCE-MANIFEST.json` para identificar los archivos utilizados.

También puedes guardar esas mismas fuentes sin conexión desde **Ayuda → Licencia y código fuente → Guardar código fuente** en la aplicación.

El archivo `SHA256SUMS.txt` permite comprobar la integridad de los archivos publicados. `manifest-windows.json` en Windows y `manifest.json` en Mac identifican el archivo de fuentes y su revisión de base.
