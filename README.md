# Repositorio de entrega — «Incidente en el GSEC»

Este repositorio **privado** es el canal de entrega de vuestro equipo. Solo lo veis vosotros, la
organización y el jurado. Todo lo que entreguéis va aquí; **la hora del *push* es la que cuenta**.

## Antes de nada (quien ha creado el repositorio, 2 minutos)

1. Comprobad que el repositorio es **privado** (*Settings → General → Danger Zone* debe ofrecer
   «Change to public», no «Change to private»).
2. *Settings → Collaborators → Add people*: añadid a **`SergioCyber`** y a **`alegp-google`**
   (organización y jurado) y al resto del equipo. Sin esos dos colaboradores la organización no
   puede recoger ni corregir la entrega.
3. Enviad la **URL de este repositorio** y el nombre del equipo a la organización por el canal del
   evento, antes de la primera entrega.

No lo hagáis público ni quitéis colaboradores hasta que se publiquen los resultados.

## Cómo se entrega (tres líneas)

```bash
git clone https://github.com/<usuario>/<este-repositorio>.git && cd <este-repositorio>   # 1. clonar (una vez)
#   2. editar ENTREGA.md, respuestas.json, oleadaN.json, BITACORA.md, informe/…
git add -A && git commit -m "Oleada 1: VPN sospechosa" && git push                       # 3. subir
```

- **Validad antes de subir.** Los JSON tienen formato obligatorio; un fichero que no valide no puntúa:

  ```bash
  python3 starter-kit/validar_respuestas.py respuestas.json oleada1.json
  ```

  Podéis pasar varios ficheros a la vez. Sale `OK` o una lista de errores con la ruta exacta del
  problema (`respuestas.q03.respuesta.dominio: …`). Solo necesita Python 3.10+.
- **Nada de `push --force`** ni de reescribir el historial: las marcas temporales salen de los
  *commits* y de los *push* que registra GitHub; un historial reescrito se trata como entrega
  inválida (ver `NORMAS.md` del repositorio público).
- Cada *push* lanza una comprobación automática del formato (pestaña **Actions**). Si falla,
  corregid y volved a subir: no hay límite de intentos. Para las oleadas puntúa la **primera versión
  válida** de cada `oleadaN.json`: podéis mejorarla después sin perder el tiempo de detección.

## Qué va en cada fichero

| Fichero | Qué es | Formato |
|---|---|---|
| `ENTREGA.md` | Ficha para el jurado: accesos, URL de la consola, credenciales de prueba, rutas | Markdown (plantilla incluida) |
| `respuestas.json` | Cuestionario (reto 3) | Obligatorio, ver `starter-kit/FORMATO_ENTREGA_ES.md` |
| `oleada1.json`, `oleada2.json`, `oleada3.json` | Reporte de cada oleada (reto A); copiad `starter-kit/oleada.plantilla.json` y cambiad `oleada` | Obligatorio |
| `BITACORA.md` | Bitácora de investigación, en orden cronológico | Markdown (plantilla incluida) |
| `informe/` | Informe técnico, resumen ejecutivo y plan de respuesta, en PDF | Libre |

Consejos rápidos:

- Las respuestas que no sepáis se dejan en `null`: en blanco nunca resta, una respuesta-trampa sí.
- No subáis el dataset ni la base de datos a este repositorio (`.gitignore` ya los excluye):
  solo entregables. Tampoco contraseñas personales: usad credenciales creadas para el reto.
- Si el equipo cambia, añadid o quitad colaboradores vosotros mismos (*Settings → Collaborators*)
  y avisad a la organización; los dos colaboradores de la organización no se quitan nunca.
