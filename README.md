# Stand-up Comedy — Taller rioplatense

Repo para escribir, pulir y stress-testear rutinas de stand-up en español rioplatense (Arg/Uy), registro **ácido y absurdo**.

## Skills instaladas (`.claude/skills/`)

Dos skills ya hechas, adaptadas al registro rioplatense:

### `joke-engineering`
Diagnóstico estructural del humor. Trata cada chiste como un sistema de conexiones con 9 propiedades medibles y 6 estados de falla:

- **H1** — Muy obvio (el remate se ve venir)
- **H2** — Muy oscuro (la referencia no llega)
- **H3** — Poca densidad (chiste de un solo hilo)
- **H4** — Sobreexplicado (no deja espacio al público)
- **H5** — Voz forzada (no suena a la persona)
- **H6** — Setup inflado (se pierde el envión antes del remate)

Fuente: [jwynia/agent-skills](https://github.com/jwynia/agent-skills) (MIT). Incluye una sección de localización rioplatense.

### `comedy-writers-room`
Sala de escritores con subagentes: un escritor escribe/revisa y tres personas de público reaccionan e iteran.

- **El Entusiasta** — cómplice, fácil de divertir
- **El Escéptico** — habitué del under, difícil de impresionar
- **El Sobrepensador** — literal, caza agujeros lógicos

Fuente: [talsraviv/comedy-writers-room](https://github.com/talsraviv/comedy-writers-room). Adaptada a voseo + público de club porteño, con instrucción de preservar la voz del usuario.

## Flujo de trabajo

1. Pegás tu rutina.
2. `joke-engineering` diagnostica bit por bit (qué estado de falla tiene cada chiste).
3. `comedy-writers-room` reescribe e itera con el público simulado.
4. Se guarda la versión original + la pulida + las notas.
