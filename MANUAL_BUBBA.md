<p align="center"><img src="assets/logo/bubba-logo.png" alt="Bubba" width="420"></p>

# Manual de Bubba 2.0

**Bubba** es un firmware para la groovebox **M-VAVE FM-1**. Está hecho a partir de [SLOOP](https://github.com/isod89/sloop-fm1) (isod89) y de [Felucca](https://github.com/hugelton/Felucca) (Leo Kuroshita / Hügelton Instruments), con licencia GPL-3.0 y sin garantía.

Este manual explica lo que Bubba trae nuevo o distinto. Las capas, el secuenciador, la grabación sin clic y las canciones funcionan como en SLOOP; su manual está en [SLOOP.md](SLOOP.md).

---

## Índice

1. [Qué es Bubba](#1-qué-es-bubba)
2. [Instalar (y el formateo de la primera vez)](#2-instalar-y-el-formateo-de-la-primera-vez)
   - [La pantalla](#la-pantalla)
3. [Ocho tracks](#3-ocho-tracks)
4. [Batería](#4-batería)
5. [El SAMPLER](#5-el-sampler)
6. [La loopera de cada track](#6-la-loopera-de-cada-track)
7. [Secuenciador: pasos largos, NUDGE y fills](#7-secuenciador-pasos-largos-nudge-y-fills)
8. [Acordes: CHORD+, STRUM y VLEAD](#8-acordes-chord-strum-y-vlead)
9. [Filtro por track (FILT)](#9-filtro-por-track-filt)
10. [Secciones: quick chain](#10-secciones-quick-chain)
11. [MIDI](#11-midi)
12. [Sonidos](#12-sonidos) (y [FM6, el DX7](#fm6-fm-de-6-operadores-tipo-dx7))
13. [Guardado y memoria](#13-guardado-y-memoria)
14. [Editor web](#14-editor-web)
15. [Emulador y pruebas](#15-emulador-y-pruebas)
16. [Créditos](#16-créditos)

---

## 1. Qué es Bubba

| | |
| --- | --- |
| **8 tracks** | Siete sintes y una batería. Cada sinte con su engine, su patrón (hasta 64 pasos) y su loopera. |
| **11 engines** | ANALOG, DIGITAL (FM de 4 operadores), PHASE, LOFI, SAMPLE, VOICE, TRIO, WHEEL, GRAIN, **SLICE** (el sampler) y **FM6** (FM de 6 operadores tipo DX7). |
| **82 sonidos** | Por tipo: bajos, keys, órganos, pads, leads, plucks, stabs y efectos. Nuevos: TENOR SAX, SAX BREATH, los 5 de SLICE y los 9 de FM6. |
| **38 kits de batería** | ACOUSTIC, los 32 sintetizados, los **5 analógicos de Felucca** (F.80, F.10, F.66, F.55, F.77) y **3 kits tuyos** (USR1–USR3). |
| **SAMPLER** | Una sección propia: cargas un audio desde el editor, lo cortas en chops en el FM-1 (forma de onda, TAP, ZOOM), tocas los chops en 16 pads y los secuencias como la batería. 3 slots de 92 KB (11.7 s a 16 kHz). |
| **Loopera** | En cada track, estilo RC: REC → PLAY → DUB → PLAY. |
| **De SLOOP 2.4 y Felucca 1.1.5** | Filtro por track, CHORD+, NUDGE, fills, quick chain, pasos largos, delays con puntillo, MIDI CLOCK y SEQ a MIDI OUT, y varias correcciones. |

## 2. Instalar (y el formateo de la primera vez)

1. **Respaldo:** la 2.0 es un corte limpio. Si quieres conservar algo, guárdalo antes con el editor del firmware que tienes (SLOOP, Felucca o Bubba 1.x). De un backup anterior a la 2.0, el editor de Bubba solo puede devolver los **samples**; proyectos, presets, banco FM6 y ajustes no.
2. Abre el instalador de Bubba en Chrome o Edge, conecta el FM-1 por USB y pulsa **Install**. El instalador revisa el paquete completo antes de borrar nada; si el archivo viene dañado, no toca el FM-1.
3. En el primer arranque Bubba muestra **BUBBA 2.0: FORMATTING** y borra **todo lo guardado**: proyectos, samples, presets de usuario, ediciones de samples, banco FM6, ajustes y la calibración de las perillas.
   - Las perillas vuelven a la calibración de fábrica. Si alguna gira al revés o un botón no responde, recalibra en el menú (HOME sostenido) → **HARDWARE CALIBRATION**, o sosteniendo OCT− y OCT+ al encender.
   - El formateo pasa una sola vez. **Desde la 2.0, las actualizaciones conservan tus datos**: cada cosa guardada lleva su versión y se migra si cambia.
4. Para volver a SLOOP o al firmware oficial, usa sus instaladores. El oficial está en la sección "Return to the official firmware" del instalador.

**Rescate USB:** mantén OCT− mientras enciendes el aparato.

### La pantalla

Desde la 2.0 todas las pantallas se arman igual, de arriba abajo:

| Franja | Qué muestra |
| --- | --- |
| **Cabecera** | ▶ o ■, el BPM (blanco mientras giras SELECT), la octava si la moviste, los cuatro tiempos del compás, dónde estás (página y número, o el nombre de la pantalla), REC (rojo: este track; gris: otro), la ficha del track elegido en su color (marco blanco: hay solo) y la batería. Los avisos la ocupan un par de segundos. |
| **Módulo** | Lo propio de la pantalla: pasos, carriles (batería, SAMPLER STEP), onda, pads, pistas, listas o curvas. En las páginas, arriba va el engine y el sonido del track. |
| **Franja** | En las páginas y en TRACKS, los 16 pasos del banco con el cabezal. En batería y SAMPLER, **qué hacen las teclas propias de la pantalla** ("1-8 SOUND · 9-10 SEC · 11 MUTE"). |
| **Perillas** | K1–K4, **cada una siempre en su color** (azul, verde, amarillo, naranja): el aro, la etiqueta y el valor (blanco mientras gira; gris si no se usa). |

El menú **COLOR** tiñe los grises; los colores de perillas y tracks no cambian.

## 3. Ocho tracks

- **TRACKS (HOME):** el track seleccionado, su nivel, su largo y su paneo. Los tracks 5–8 están en el segundo banco.
- **GLO sostenido:** blancas 1–8 silencian los tracks 1–8 (mute) y blancas 9–16 los dejan solos (solo). La primera negra marca el tempo (tap tempo).
- **Voces:** 8 en total para los sintes, repartidas según hagan falta; hasta 4 por track. Cuando faltan, se roba una voz con un fundido corto (sin clic), nunca la que sostiene el bajo o el lead (MONO / LEGATO). ANALOG en UNISON gasta una sola voz.

## 4. Batería

- **Fuera de la pantalla de batería las teclas son pads LIVE:** las 16 blancas tocan los 16 sonidos, y OCT− / OCT+ sostenidos dan golpes suaves o fuertes (ghost / hard).
- **Con REC y PLAY, cada pad graba en su propia línea:** el golpe queda donde lo tocaste, con su nivel.
- **En la pantalla de batería** (SEQ en el track de batería), un toque a SEQ cambia entre **STEP** y **LIVE** (pads).
- **En STEP:**

  | Tecla | Hace |
  | --- | --- |
  | **Blancas** | Los 16 pasos del sonido elegido |
  | **Negras 1–8** | Eligen y tocan un sonido de la sección. **Con REC y PLAY lo graban** en su línea. |
  | **Negras 9 / 10** | La otra sección (sonidos 1–8 ↔ 9–16), en ciclo |
  | **Negra 11, un toque** | Saca o mete el sonido elegido en el patrón (mute) |
  | **Negra 11 sostenida** | La pantalla **MUTE**: los 16 sonidos como fichas (encendida: suena; gris: fuera). Cada **blanca** saca o mete su sonido; no deja pasos. Al soltar vuelves a STEP. |
  | **OCT− / OCT+** | Página del patrón anterior / siguiente, **en ciclo** |

  | Perilla | Hace |
  | --- | --- |
  | **K1** | El sonido |
  | **K2** sin paso sostenido | **VOL**: el volumen del sonido elegido, 0–15. Se guarda con el proyecto. |
  | **K2** con un paso sostenido | **LEVEL** del golpe: ghost, soft, norm o **acc** (el acento). La celda toma el color de su nivel; el acento, blanco. |
  | **K3** con un paso sostenido | Ratchet (golpes extra en el paso) |
  | **K4** | El largo del patrón |
- **KIT:** la perilla PRESETS con el track de batería elegido (o la perilla 1 en la pantalla de batería). Elige entre los 38 kits y USR1–USR3 (ver [Sonidos](#12-sonidos)).

## 5. El SAMPLER

Una máquina de samples dentro del FM-1, al estilo de las SP de Roland o del OP-1, dentro de lo que da el aparato. Se trabaja con un track que tiene el engine **SLICE**.

**1. Cargar el audio** (editor web → Samples → bloque CHOP):
- abre o arrastra cualquier audio (WAV, MP3, AIFF…);
- pulsa **Whole to SAMPLER → USR1 / USR2 / USR3**;
- se manda entero como un solo sample (o del primer al último marcador, si pusiste dos);
- si es más largo que el slot (11.7 s a 16 kHz) se recorta con un fundido.

**2. Entrar:** en un track SLICE, **toca EDIT**. Se abre la pantalla **SAMPLER**.
- Otro toque a EDIT va a las páginas EDIT normales (SRC, DIV, START, PTCH, MODE, REV, DCAY, TONE).
- HOME sale.
- **Un toque a SEQ cambia de modo:** CHOP → PADS → STEP.

### CHOP: cortar (estilo OP-1)

La forma de onda de la región, con los chops numerados, el elegido en blanco y una línea donde está sonando.

| Control | Hace |
| --- | --- |
| **Blancas** | Eligen y escuchan el chop 1–16 (17–32: negras 9 / 10) |
| **Negra 1** (sostenida) | Escucha toda la región |
| **Negra 2** | **ZOOM**: un octavo del sample alrededor del corte elegido, para afinarlo |
| **K1 START** | Mueve el inicio del chop elegido (su corte; en el chop 1, el inicio de la región) |
| **K2 END** | El fin de la región |
| **K3 DIV** | 4, 8, 16, 32, AUTO (en cada golpe), 1 (todo un loop) o EDIT (tus cortes) |
| **K4 FIT** | La región dura exactamente 1, 2, 4 u 8 compases al tempo (el tono sigue a la velocidad) |
| **OCT+** | **TAP**: un corte justo donde está sonando |
| **OCT−** | Borra el corte del chop elegido |
| **PRESETS** | El slot (USR1–3) |

Al mover o agregar un corte, los chops de DIV 4–32 o AUTO **se vuelven cortes** (DIV EDIT): lo que mueves es lo que oyes. Hasta 32 chops.

### PADS: tocar (estilo SP)

16 pads en 4×4 que se encienden al sonar. Las **blancas** los tocan; **con REC y PLAY se graban** en el patrón del track. Las negras 9 / 10 cambian al banco 17–32.

Las perillas ajustan el pad elegido (cada chop guarda lo suyo):

| | |
| --- | --- |
| **K1 TUNE** | ±24 semitonos |
| **K2 LEVEL** | Su volumen |
| **K3 PLAY** | `trk` (el MODE del track), ONE, GATE o LOOP |
| **K4 REV** | `trk` (el del track), adelante o al revés |

### STEP: secuenciar (como la batería)

La cuadrícula de 8 pads × 16 pasos de la sección.

| Tecla / perilla | Hace |
| --- | --- |
| **Negras 1–8** | Eligen y tocan un pad (con REC y PLAY, lo graban) |
| **Negras 9 / 10** | La sección siguiente, en ciclo |
| **Blancas** | Los pasos de ese pad. Un paso guarda hasta **4 pads**; los demás del paso se quedan. |
| **OCT− / OCT+** | La página, en ciclo |
| **K1** | El pad |
| **K2 / K3** | Nivel / ratchet de los pasos sostenidos |
| **K4** | El largo del patrón |

Las ediciones (región, cortes, FIT y los ajustes de cada pad) se guardan solas en la flash, por slot. Si cargas otro sample en ese slot, se descartan.

**Presets de SLICE:** SLICE 16, CHOP 8, REVERSE, SLICE AUTO y LOOP 1, todos sobre USR1. Un slot vacío no suena y la pantalla dice **NO SAMPLE**.

## 6. La loopera de cada track

Cada sinte puede ser una loopera estilo RC sobre su propio patrón. Las teclas siguen tocando mientras tanto.

- **Encender:** página **LOOP** (SEQ → la página después de PATTERN), perilla 1 = **ON**. Con LOOP encendido, **un toque a SEQ abre la loopera**; otro toque vuelve a las páginas de SEQ. Sostener SEQ sigue siendo la capa de pasos.
- **Perillas:**

  | | |
  | --- | --- |
  | **LOOP** | ON / OFF |
  | **BARS** | 1, 2 o 4 compases (el patrón queda de ese largo, en 1/16) |
  | **QUANT** | La grabación arranca en el siguiente **BAR** (compás) o **BEAT** (tiempo) |
  | **SMPL** | Solo con SLICE: la región del sample suena como loop desde cada vuelta, con FIT a los compases |

- **REC:**
  - **Loop vacío:** REC espera el compás (o el tiempo), arranca el transporte si estaba parado y **graba** sus compases. Al terminar pasa solo a **PLAY**.
  - **PLAY:** REC = **DUB** (sobregraba encima). Otro REC vuelve a PLAY.
  - Si el track ya tiene un patrón, ese patrón es el loop y REC hace DUB sobre él.
- **OCT−** (en la página LOOP): **detiene o arranca el loop en el siguiente compás**. Sus pasos callan, pero las teclas siguen sonando.
- **REC sostenido ~2 s:** borra el loop. **EDIT + OCT−** lo recupera (deshacer). Si el transporte estaba parado, sigue parado.
- **STOP** durante un DUB: termina la sobregrabación y el loop queda en PLAY.
- La pantalla muestra el estado (EMPTY, WAITING, REC, PLAY, DUB, STOPPED) y en qué parte del loop va.
- El track de batería no tiene loopera en esta versión. Para batería usa la grabación LIVE de siempre.

## 7. Secuenciador: pasos largos, NUDGE y fills

- **DIV** (capa SEQ, perilla 2, o SEQ → PATTERN): 1/4, 1/8, 1/16, 1/32, 8T, 16T, y además **1/2, 1BAR y 2BAR** para pads y acordes largos.
- **NUDGE:** sostén SEQ, sostén un paso (su tecla) y gira la **perilla 4**. El paso se adelanta o atrasa hasta medio paso, en 1/64 de paso. La pantalla dice "NUDGE +5".
- **Fills** (por paso), con SEQ y un paso sostenidos:
  - **OCT+** cambia su condición entre **ALWAYS** (siempre), **FILL ONLY** (solo en fill) y **NO FILL** (nunca en fill).
  - **OCT−** borra el nudge y la condición.
- **Tocar un fill:**
  - **GLO + negra 2** sostenida: fill mientras la sostienes.
  - **GLO + negra 3:** el siguiente compás entero es fill. Otra vez para cancelar.
- **Probabilidad por paso** (tracks de sinte): sostén SEQ, sostén un paso y gira **PRESETS**. Va de 100% a 12% en 8 niveles, y la pantalla dice "CHANCE 50%". En cada vuelta el paso suena o no según esa probabilidad.
- **SEQ TOOLS** (tracks de sinte; SEQ sostenido + negras 5–9). Cada uno se deshace con EDIT + OCT−.

  | Negra | Hace |
  | --- | --- |
  | **5 / 6** | SHIFT: todo el patrón un paso antes / después |
  | **7** | REVERSE: de atrás hacia adelante (cada nota conserva sus ligaduras) |
  | **8** | RANDOM: notas nuevas en la escala, con el mismo ritmo |
  | **9** | COOK: lo cambia un poco (dos notas un grado, un golpe a un paso libre vecino) |

- El swing ya no mueve los tresillos, y DIV y RATE quedan en su lugar desde el primer tiempo después de PLAY.

## 8. Acordes: CHORD+, STRUM y VLEAD

Con **CHORD** encendido (SCL, perilla 1), las **negras** cambian el acorde mientras las sostienes y el acorde se re-voicea bajo tus dedos:

| Negra | Modificador |
| --- | --- |
| F# | menor |
| G# | 7 |
| A# | sus4 |
| C# | 9 |
| D# | inversión |

Se pueden combinar.

**Ver el acorde (2.0):** mientras sostienes teclas con CHORD encendido, la pantalla de pistas y las páginas muestran el acorde que suena: el nombre (la raíz grande, el resto al lado: "C" + "m7"), los modificadores encendidos (m, 7, sus4, 9, inv), sus notas (la más grave en blanco) y un teclado de dos octavas con esas notas encendidas. Al soltar vuelve lo de antes.

**Editar el acorde de un paso (2.0):** en la capa de pasos (SEQ sostenido), sostén un paso que tenga un acorde:

| Perilla | Hace |
| --- | --- |
| **K1 MOVE** | Mueve el acorde entero por grados de la escala del track (C → Dm → Em… en Do mayor) |
| **K2 TYPE** | Lo rehace sobre su raíz con el tipo siguiente o anterior: TRIAD, 7TH, 9TH, SUS4, POWER |
| **K3 INV** | Lo invierte: la nota más grave sube una octava (al revés: la más aguda baja) |
| **K4 NUDGE** | Como siempre |

Las perillas muestran el acorde (MOVE Dm7), su tipo (TYPE 7th) y su bajo (INV /F4). Un paso de **una sola nota** sigue igual: K1 la nota por semitonos, K2 su nivel, K3 el ratchet.

En la página **SCL 2**:

| | |
| --- | --- |
| **STRUM** | ms entre las notas del acorde; positivo de grave a agudo, negativo al revés |
| **VLEAD** | voice leading: cada acorde se toca en la inversión más cercana al anterior |

## 9. Filtro por track (FILT)

- **Un filtro por track, también en la batería:** a la izquierda pasa-bajos, al centro apagado, a la derecha pasa-altos.
- **En vivo:** sostén FX y gira la **perilla 4** (el track seleccionado).
- **En página:** FX → **FILTER**.
- Se guarda con el proyecto.

## 10. Secciones: quick chain

Sostén **SAVE** y toca dos o más secciones (blancas 1–4) en orden. Al soltar SAVE quedan encadenadas en bucle, cada una durante los compases de su patrón más largo. La pantalla muestra "chain A B B C".

- Tocar una sola sección es un salto normal.
- STOP termina la cadena.

## 11. MIDI

GLO → **SYSTEM**:

| | |
| --- | --- |
| **MIDI** (salida) | **KEYS**: lo que tocas. **SEQ**: también lo que toca el secuenciador, cada track por su canal y la batería por el suyo, para grabarlo en una DAW. |
| **SYNC** | INT, USB o TRS (seguir un reloj externo) |
| **IN** | **NOTES**: notas y reloj. **CLOCK**: solo el reloj. |

- MIDI START durante la cuenta (count-in) la corta y arranca.
- **Controladores MIDI** (en el canal del track):

  | CC | Parámetro |
  | --- | --- |
  | **5** | GLIDE |
  | **7** | LEVEL |
  | **10** | PAN |
  | **64** | Sustain: las notas soltadas siguen hasta levantar el pedal |
  | **72 / 73 / 75** | RELEASE / ATTACK / DECAY |
  | **74** | El filtro del track (64 = abierto) |
  | **91 / 93 / 94** | Envíos de reverb, chorus y delay |

  El **pitch bend** mueve ±2 semitonos. En el track de batería solo aplican LEVEL, PAN, el filtro y la reverb.
- **USB SERIAL** (menú HOME): la consola serie por USB viene **apagada** por defecto. Enciéndela solo para medir CPU (`tools/fm1_cpu.py`) y vuelve a conectar el cable.

## 12. Sonidos

**Kits de batería (KIT):**

| Kits | Qué son |
| --- | --- |
| **ACOUSTIC** | El kit acústico de muestras (CC0) |
| **32 sintetizados** | 808, 909, 606, 80S, VINTAGE, TRAP, DRILL, BOOMBAP, LO-FI, PHONK, HOUSE, D.HOUSE, TECHNO, MINIMAL, ELECTRO, DISCO, GARAGE, JUNGLE, DUBSTEP, DEMBOW, AMAPIANO, AFRO, LATIN, TRIBAL, SYNTHWV, CHIP, ARCADE, GLITCH, INDUSTR, HYPER, AMBIENT, JAZZ |
| **F.80, F.10, F.66, F.55, F.77** | Los kits analógicos de Felucca, con su propio motor de voces (`drum_voice.c`). Cada nota GM toca la pieza que Felucca le asigna. |
| **USR1–USR3** | Tu kit: un sample por línea, cargado en ese slot (nota de la zona = nota GM de la línea). Se arma con el editor web o con `tools/fm1_sample_upload.py` y el sufijo `:RAÍZ:LO-HI`. |

Ya no están DEEP, TIGHT, BRIGHT ni DUST: eran ACOUSTIC con otra afinación y filtro. Tampoco el set **VIBES** ni sus presets VIBES y VIBE HAZE (se fueron para dar espacio al SAMPLER y a FM6).

**SAX:** el saxo tenor de Felucca (VCSL, CC0) es un set integrado (16 kHz, 0.6 s por nota con loop de sustain). Lo usan los presets **TENOR SAX** (SAMPLE) y **SAX BREATH** (GRAIN). Sustituye al set SCRCH.

### FM6: FM de 6 operadores tipo DX7

FM6 es el motor de FM del DX7 (el núcleo msfa de Dexed, licencia Apache-2.0), traído de SLOOP 2.4 / Felucca.
- **32 algoritmos** y un patch completo por track.
- **9 patches de fábrica:** TINE EP, GLASS BELL, ROUND BASS, BRASS SECT, SOFT PAD, WOOD BARS, DRAWBARS, NYLON PICK y **FM VIBES** (el vibráfono que reemplaza al set VIBES). No trae los sonidos de fábrica de Yamaha.
- **Banco de 27 patches tuyos** en el FM-1 (PTCH B1–B27).
- **Hasta 2 tracks con FM6 a la vez.** Un tercero avisa **FM6 2 TRACKS MAX**.

En el FM-1, las perillas de EDIT son macros sobre el patch:

| | |
| --- | --- |
| **ALG** | `PAT` (el del patch) o 1–32 |
| **FB** | Feedback |
| **MLVL** | Brillo: el nivel de los moduladores |
| **MRAT** | Relación de los moduladores |
| **MEG** | Más rápidas o más lentas las envolventes de los moduladores |
| **VMOD** | Sensibilidad a la velocidad |
| **DTUN** | Separa en afinación los carriers (más ancho) |
| **PTCH** | Carga un patch: F1–F9 de fábrica, B1–B27 tus bancos |

En el **editor web** (pestaña Sound, con un track FM6 elegido) está el panel **FM6**:
- se edita cada operador y la voz;
- **Import SysEx** lee un patch o un **banco de 32 del DX7** (`.syx`) y eliges cuál;
- "Send to track" lo pone en el track al instante;
- "Store in bank" lo guarda en B1–B27 (con la canción detenida);
- exporta un patch o el banco como `.syx`.

El proyecto guarda PTCH, no el patch: para conservar un patch editado, guárdalo en un slot del banco y pon PTCH ahí. El banco entra en el backup.

**Packs para tus slots** (`assets/bubba-pack`, se generan con `py -3 tools/make_pack.py`):

| Pack | Qué trae |
| --- | --- |
| **SAX** | Las notas completas del saxo (1.5 s cada una) |
| **SCRATCH** | Los scratches que antes eran el set SCRCH |

Se cargan con el editor web o con la línea que imprime `make_pack.py`.

## 13. Guardado y memoria

| Qué | Dónde |
| --- | --- |
| **Proyectos** | 4 slots (A–D) con los 8 tracks completos, más el **autosave** |
| **Samples** | 3 slots de 92 KB: unos 11.7 s a 16 kHz u 8.5 s a 22 kHz. El editor deja elegir la calidad por sample. |
| **Presets de usuario** | 32; se leen directo de la flash (no ocupan RAM) |
| **Ediciones de samples** | Región, cortes, FIT y los ajustes de cada pad, por slot, guardados aparte |
| **Formato** | El de Bubba 2.0: cada cosa guardada lleva su versión; una actualización la migra en lugar de borrarla |

Nada se escribe en la flash mientras suena: el editor y el autosave esperan a que el aparato esté quieto.

## 14. Editor web

`web/editor.html` (el instalador lo publica en `webapp/editor`):

- **Backup y restore** de todo: proyectos, presets, samples, ediciones y ajustes. Archivos `Bubba-backup-*.json`. De un backup anterior a la 2.0 (o de SLOOP) solo se devuelven los samples.
- **Samples:** 3 slots, calidad de 22, 16 u 11 kHz por sample (16 kHz por defecto). En el bloque CHOP, **Whole to SAMPLER** manda un audio entero a un slot para cortarlo en el FM-1.
- Conoce los 11 engines (con SLICE y FM6) y los 41 valores de KIT.
- **FM6:** el panel de patches (operadores, banco, importar y exportar SysEx del DX7).

## 15. Emulador y pruebas

| | |
| --- | --- |
| `LAUNCH-EMULATOR.bat` | El emulador de Windows: el firmware real sobre una HAL emulada |
| `py -3 tools/docker_build.py test` | Todas las pruebas de host (Docker). Incluye `slice_test`, `sampler_test` (el SAMPLER por la UI real), `looper_test`, `fm6_test`, `tools_test` y `upreset_flash_test`. |
| `py -3 tools/docker_build.py fw` | Compila el firmware: `build/felucca.fwsc` |
| `py -3 web/make_site.py build/felucca.fwsc 1.0 OUT` | Arma el sitio instalador |
| `py -3 tools/fm1_cpu.py 90` | Mide la CPU en el FM-1 durante 90 s (USB SERIAL encendido y cable reconectado) |

**Memoria (con el SAMPLER y FM6):**

| | Usado (bytes) | Límite (bytes) |
| --- | --- | --- |
| Flash (XIP) | 568,192 | 581,564 |
| RAM (.data + .bss) | 93,456 | 98,304 |
| Pool | 336,624 | 344,064 |

## 16. Créditos

- **SLOOP:** isod89, [github.com/isod89/sloop-fm1](https://github.com/isod89/sloop-fm1) (GPL-3.0)
- **Felucca:** Leo Kuroshita (@kurogedelic), [Hügelton Instruments](https://hugelton.com), [github.com/hugelton/Felucca](https://github.com/hugelton/Felucca) (GPL-3.0): el firmware base, los kits analógicos (`drum_voice.c`), el SAX y el puerto de FM6
- **FM6:** msfa (Google, Pascal Gauthier / Dexed), Apache-2.0 (`LICENSES/Apache-2.0-msfa.txt`)
- **Samples:** Versilian Studios, VSCO-2 CE y VCSL (CC0). Scratches del pack: Sonic Pi sample set (CC0).
- **Fuente:** Terminus (SIL OFL 1.1). **PHASE:** CrispyZebra (GPL). **VOICE:** referencia klattsch (MIT).
- **Bubba:** Erick Buendía Barrientos, [github.com/Erbubar23/sloop-fm1](https://github.com/Erbubar23/sloop-fm1) (rama `bubba`)

M-VAVE y FM-1 son marcas de sus dueños; Bubba no está afiliado a ellos. GPL-3.0, sin garantía.
