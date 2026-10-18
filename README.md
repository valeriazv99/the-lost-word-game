# The Lost Word ⌨️🧟

**Juego multijugador de mecanografía en tiempo real.** Los jugadores escapan de una horda de zombis escribiendo: cuanto más rápido y preciso escribes, más rápido corre tu personaje. El último en sobrevivir gana.

Proyecto en equipo (5 personas) del CFGS de Desarrollo de Aplicaciones Web (Institut Pedralbes, curso 2025-26), desplegado en producción durante el curso.

![Vue](https://img.shields.io/badge/Vue_3-4FC08D?logo=vuedotjs&logoColor=white)
![Pinia](https://img.shields.io/badge/Pinia-FFD859?logo=pinia&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?logo=tailwindcss&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![Socket.io](https://img.shields.io/badge/Socket.io-010101?logo=socketdotio&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

---

## Cómo se juega

1. Creas una sala o te unes a una existente.
2. En el lobby ves quién se ha conectado y esperáis a que empiece la partida.
3. Aparece un texto y todos lo escribís a la vez. Cada palabra que escribes hace avanzar a tu personaje.
4. Cada cierto tiempo, los zombis alcanzan al jugador que va más atrás y queda eliminado.
5. Al terminar, ves la clasificación con los resultados de todos, incluidas las palabras por minuto y la precisión.

---

## Mi aportación

- **Salas múltiples:** reestructuración de la gestión de salas con Socket.IO para que puedan jugarse varias partidas a la vez, con creación y eliminación dinámica de salas y gestión de jugadores.
- **Temporizador sincronizado:** refactorización de la lógica del tiempo de partida en el servidor y en el cliente, para que todos los jugadores vean lo mismo.
- **Lobby:** lista de jugadores conectados y redirección automática al empezar la partida.
- **Diseño visual:** integración de Tailwind CSS y estilos de todas las pantallas (inicio, lobby, creación de sala, partida y final), fondos y efectos visuales.

---

## Stack

| Capa | Tecnologías |
|---|---|
| **Frontend** | Vue 3, Pinia, Vue Router, Tailwind CSS, Vite |
| **Backend** | Node.js, Express, Socket.IO |
| **Base de datos** | MySQL |
| **Infraestructura** | Docker Compose (entornos de desarrollo y producción), Adminer |
| **Calidad** | SonarQube |

El servidor es quien manda en cada partida: recibe el progreso de cada jugador por WebSocket, calcula su posición en la carrera y la difunde a toda la sala.

---

## Cómo ejecutarlo en local

**Requisitos:** Docker y Docker Compose.

```bash
git clone https://github.com/valeriazv99/the-lost-word-game.git
cd the-lost-word-game
docker compose -f docker-compose.dev.yml up --build
```

| Servicio | URL |
|---|---|
| Juego (frontend) | http://localhost:5173 |
| Servidor | http://localhost:3000 |
| Adminer (base de datos) | http://localhost:8080 |

---

## Documentación

- [Guía de despliegue y contribución](doc/prod/README.md) (en catalán)
- [Sprints y diagramas](doc/README.md)
- [README original](doc/README-original.md)

---

## Equipo

- Llorenç Carnice
- Roman Novytsky
- **Valeria Zavaleta** ([@valeriazv99](https://github.com/valeriazv99))
- Climent Fernández
- Iker Mata

Repositorio original: [inspedralbes/tr1-type-racer-royale-tr1-grup-1](https://github.com/inspedralbes/tr1-type-racer-royale-tr1-grup-1)
