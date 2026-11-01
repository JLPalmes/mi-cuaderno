---
lang: es-ES
---

# Mi Cuaderno

Cuaderno del profesor para organizar grupos y alumnado, actividades, calificaciones, asistencia e informes. Autor: **Juan Luis Palmés Martín**.

## Descargar

- **[Windows x64 — descargar Mi Cuaderno 2.1.2 (.exe)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.1.2/Mi-Cuaderno-2.1.2-Windows-x64-Setup.exe)**.
- **[Mac Apple Silicon — descargar Mi Cuaderno 2.0.2 (.dmg)](https://github.com/JLPalmes/mi-cuaderno/releases/download/v2.0.2/Mi-Cuaderno-2.0.2-arm64.dmg)**. Requiere M1 o posterior y macOS 11 o posterior; no es compatible con Mac Intel.
- [Ver la publicación principal, fuentes y licencias](https://github.com/JLPalmes/mi-cuaderno/releases/latest).

Windows está actualizado a **2.1.2**, con Pincel por evaluación, observaciones, recuperaciones y registros sin ponderación. Mac continúa en **2.0.2**, sin cambios. **Las nuevas copias JSON de formato 2 no pueden importarse en Mac 2.0.2 ni en Windows anterior a 2.1.** Se aceptan las copias antiguas y se conserva un respaldo SQLite antes de actualizar.

El instalador de Windows no tiene firma de editor. **Antes de actualizar, exporta una copia JSON externa y cierra la aplicación.** Si 2.0.3 no se cierra, exporta primero la copia y finaliza Mi Cuaderno desde el Administrador de tareas.

## Novedades de Windows 2.1.2

- Medias: rojo por debajo de 5; amarillo con AP si la media aprueba pero hay actividades ponderadas suspensas; verde si aprueba sin actividades suspensas, sin distinguir tramos de aprobado.
- AP aparece después de R, reservando su espacio cuando no existe, también en medias acumuladas, Alumnado y ficha. Sólo cuentan notas vigentes inferiores a 5 tras recuperaciones; vacíos y registros sin ponderación quedan fuera.
- No cambian las fórmulas, la persistencia ni el formato de datos respecto a 2.1.1.

- Pincel manual por evaluación: el de tercera es también el final publicado y nunca entra en los cálculos.
- Observaciones por alumno y evaluación, después de Pincel.
- Recuperaciones: cuenta la última realizada, incluso con nota inferior, con la ponderación original una sola vez. Vacío significa no realizada. No se permiten fechas repetidas para la misma actividad original.
- Marca **R** después de la media, en la misma línea y en negrita.
- Nombre automático «Recuperación de [actividad]», editable, y etiquetas correctas de primera, segunda y tercera evaluación en el formulario.
- Notas inferiores a 5 en rojo y actividades sin ponderación para registrar trabajo sin afectar la nota.
- Copia SQLite completa y verificada antes del cambio de formato; actualización transaccional y protección frente a versiones antiguas.
- 484 pruebas correctas: 143 generales, 309 de interfaz/dominio y 32 Rust. TypeScript y lint correctos. No se accede a datos reales durante las pruebas.
- Pendiente la prueba manual del instalador Windows 2.1.2. No se ejecuta durante su preparación.

Volver a una versión anterior requiere recuperar el respaldo previo y pierde las ediciones posteriores. Conserva siempre una copia JSON externa antes de actualizar. Para intercambiar copias nuevas con Mac, espera a una compilación Mac compatible con formato 2.

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

Los cuadernos se guardan en el dispositivo. Windows 2.1.2 utiliza SQLite; la copia JSON exportable permite intercambiar datos entre versiones compatibles. Las copias nuevas de formato 2 requieren versiones actualizadas en ambos equipos. Tras migrar, el almacenamiento antiguo se conserva como rescate inicial y deja de actualizarse. Esta versión no sincroniza automáticamente los datos entre equipos. Permite importar alumnado, guardar y restaurar copias y exportar informes PDF.

## Licencia y fuentes

Copyright (C) 2026 Juan Luis Palmés Martín. Software libre bajo **GNU AGPL versión 3 exclusivamente (AGPL-3.0-only)**, sin garantía en los términos de la licencia. Consulta [LICENSE](LICENSE), [COPYRIGHT.md](COPYRIGHT.md) y [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt). Las bibliotecas de terceros conservan sus propias licencias.

Este repositorio es el canal público de distribución. **El código completo de cada versión se adjunta a su publicación** en `Mi-Cuaderno-2.0.2-codigo-fuente.tar.gz` para Mac (publicación 2.0.2) y en `Mi-Cuaderno-2.1.2-codigo-fuente.tar.gz` para Windows (publicación 2.1.2), con los recursos, scripts, archivos de bloqueo y fuentes de las dependencias incorporadas. Dentro encontrarás `SOURCE_CODE.md` con las instrucciones de compilación y `SOURCE-MANIFEST.json` para identificar los archivos utilizados.

También puedes guardar esas mismas fuentes sin conexión desde **Ayuda → Licencia y código fuente → Guardar código fuente** en la aplicación.

El archivo `SHA256SUMS.txt` permite comprobar la integridad de los archivos publicados. `manifest-windows.json` en Windows y `manifest.json` en Mac identifican el archivo de fuentes y su revisión de base.
