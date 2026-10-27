# Recorrido inmersivo de la cueva — Beta 0.5

Beta panorámica preparada para la demostración: incluye 14 escenas (la entrada y el interior iniciales, más 12 panorámicas seleccionadas), los 25 saltos del archivo de configuración compartido, editor de puntos de salto y plano de referencia. El panel de navegación visible al entrar en VR se redujo aproximadamente un 20 % en anchura y un 23 % en altura.

## Qué se incorporó

- 12 panorámicas nuevas, renombradas para que sea sencillo encontrarlas y seleccionarlas en el editor.
- `assets/escenas.json` actualizado con todas las escenas y descripciones.
- Catálogo de reserva dentro de `index.html` actualizado, por si no se logra leer `escenas.json`.
- Se conserva el plano y el editor de marcadores de la beta anterior.
- `assets/recorrido-config.json` contiene la configuración de saltos entregada por el usuario (25 marcadores).
- Se cambió la clave del almacenamiento local a `cueva-vr-hotspots-v3` para evitar que configuraciones locales antiguas oculten los saltos recién incorporados.
- El menú de navegación dentro del visor es más compacto; las etiquetas de los puntos de salto mantienen su tamaño para que sigan siendo legibles.

## Escenas de la beta

| Orden | Nombre visible | Archivo |
|---:|---|---|
| 1 | Entrada principal | `entrada.jpg` |
| 2 | Interior del túnel | `interior.jpg` |
| 3 | Galería del arco gris | `galeria-arco-gris.jpg` |
| 4 | Paso central iluminado | `paso-iluminado.jpg` |
| 5 | Galería arqueada | `galeria-arqueada.jpg` |
| 6 | Túnel de roca estratificada | `tunel-estratificado.jpg` |
| 7 | Cámara de paso iluminada | `camara-luminosa.jpg` |
| 8 | Bifurcación rocosa | `bifurcacion-rocosa.jpg` |
| 9 | Galería de mineral rojizo | `galeria-mineral-rojiza.jpg` |
| 10 | Pasaje oscuro | `pasaje-oscuro.jpg` |
| 11 | Cámara de arcos laterales | `camara-arcos-laterales.jpg` |
| 12 | Galería de estratos ocres | `galeria-estratos-ocres.jpg` |
| 13 | Cruce de galerías | `cruce-de-galerias.jpg` |
| 14 | Arco central rojizo | `arco-central-rojizo.jpg` |

## Correspondencia con los archivos recibidos

Los nombres originales de las imágenes nuevas se han conservado aquí para que puedas rastrear cada selección:

- `IMG_20260330_084613_00_010_PureShot.jpg` → `assets/galeria-arco-gris.jpg` (Galería del arco gris).
- `IMG_20260330_091254_00_020_PureShot.jpg` → `assets/paso-iluminado.jpg` (Paso central iluminado).
- `IMG_20260330_092827_00_026_PureShot.jpg` → `assets/galeria-arqueada.jpg` (Galería arqueada).
- `IMG_20260402_164215_00_095_PureShot.jpg` → `assets/tunel-estratificado.jpg` (Túnel de roca estratificada).
- `IMG_20260402_165112_00_100_PureShot.jpg` → `assets/camara-luminosa.jpg` (Cámara de paso iluminada).
- `IMG_20260402_165635_00_103_PureShot.jpg` → `assets/bifurcacion-rocosa.jpg` (Bifurcación rocosa).
- `IMG_20260402_170210_00_106_PureShot.jpg` → `assets/galeria-mineral-rojiza.jpg` (Galería de mineral rojizo).
- `IMG_20260402_170627_00_118_PureShot.jpg` → `assets/pasaje-oscuro.jpg` (Pasaje oscuro).
- `IMG_20260402_171043_00_121_PureShot.jpg` → `assets/camara-arcos-laterales.jpg` (Cámara de arcos laterales).
- `IMG_20260402_171630_00_123_PureShot.jpg` → `assets/galeria-estratos-ocres.jpg` (Galería de estratos ocres).
- `IMG_20260402_172600_00_128_PureShot.jpg` → `assets/cruce-de-galerias.jpg` (Cruce de galerías).
- `IMG_20260402_173008_00_130_PureShot.jpg` → `assets/arco-central-rojizo.jpg` (Arco central rojizo).

Tres imágenes recibidas no se incluyeron en esta selección inicial por repetición visual o menor fuerza para una demostración corta: `IMG_20260330_085306_00_016_PureShot.jpg` (muy parecida a la primera galería), `IMG_20260402_164433_00_097_PureShot.jpg` (similar a la panorámica anterior) e `IMG_20260402_171928_00_125_PureShot.jpg` (marcación visible en la roca que distrae en una presentación breve). Los originales que no se seleccionaron no fueron modificados ni eliminados de tu equipo. Si después quieres más detalle, se pueden incorporar como escenas adicionales.

## Cómo ejecutar

1. Extrae el ZIP.
2. Abre la carpeta `beta-cueva-vr-05` en Visual Studio Code.
3. Ejecuta `index.html` con **Live Server**. No lo abras con `file://`: la aplicación usa `fetch()` para leer el catálogo JSON.
4. Usa **Anterior / Siguiente** para revisar las 14 escenas.
5. Activa **Editar saltos**, haz clic en una dirección panorámica para crear un marcador, selecciona el destino y arrastra el marcador para ajustarlo.
6. Pulsa **Guardar en navegador** mientras editas. Para transferir los saltos a la versión publicada, pulsa **Exportar JSON**, sustituye `assets/recorrido-config.json` por el archivo generado y vuelve a publicar el sitio.
7. Publica mediante HTTPS y prueba en Meta Quest Browser. La compatibilidad WebXR, láser del mando y seguimiento de manos debe comprobarse en el visor real.

## Imágenes y rendimiento

Las nuevas panorámicas se verificaron como JPG de aproximadamente 2047 × 1023 píxeles (proporción 2:1), adecuada para panoramas equirectangulares. La aplicación cambia la textura del cielo a la imagen de la escena activa. Si alguna imagen no se ve correctamente al entrar en ella, revisa el registro de errores del navegador y confirma que se publicó la carpeta `assets` completa.

## Orden de recorrido

El catálogo se ordenó siguiendo, en general, la secuencia temporal de captura y dando prioridad a panorámicas con entradas, arcos o cruces visualmente distinguibles. **El orden es una propuesta de demostración, no un levantamiento topográfico verificado.** Debes colocar manualmente los puntos de salto según las conexiones reales que conozcas en la cueva; no se inventaron conexiones automáticas ni coordenadas espaciales.

## Revisión pendiente de conectividad

En el JSON recibido, `galeria-estratos-ocres` tiene dos saltos de salida, pero ninguna otra escena apunta a ella. Por tanto, no se llega a esa escena usando únicamente los marcadores de salto; sigue siendo accesible mediante los controles Anterior/Siguiente. Si esto no es intencional, crea un marcador entrante desde la ubicación correcta según el recorrido real. No se añadió esa conexión automáticamente para no inventar la topología de la cueva.

## Límites de esta beta

Este prototipo es un recorrido panorámico inmersivo entre puntos de observación. No reconstruye la geometría 3D de la cueva, no estima distancias reales y no registra automáticamente las escenas sobre el plano.
