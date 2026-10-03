# Tonalpowalli — conversor de fechas nahua

Sitio estático (Caddy) expuesto mediante Cloudflare Tunnel. Sin puertos abiertos
en el router ni en el host: convive con el nginx de OpenMediaVault.

## Estructura

    tonalpowalli/
    ├── compose.yml      servicios web (Caddy) + tunnel (cloudflared)
    ├── Caddyfile        HTTP interno :8080, cabeceras de seguridad, compresión
    ├── .env.example     plantilla; cópiala a .env
    ├── TRADUCCION.md    textos de la interfaz para revisar en nawatl
    └── site/
        └── index.html   la página (español / nawatl)

## 1. Cloudflare

1. Tu dominio debe usar los DNS de Cloudflare (nameservers cambiados en tu registrador).
2. Cloudflare One → Networks → Connectors → Cloudflare Tunnels → Create a tunnel
   → Cloudflared. (También disponible en el dashboard principal: Networking → Tunnels.)
3. Copia sólo el token (lo que sigue a `--token` en el comando que muestra).
   No ejecutes ese comando: el contenedor `tunnel` hace ese trabajo.
4. Pestaña Published applications:
   - Subdomain: `tonalpowalli` · Domain: tu dominio
   - Service: `HTTP` → URL `web:8080`
5. Crea una Cache Rule para el hostname (Cloudflare no cachea HTML por defecto).
6. Desactiva Rocket Loader, Email Obfuscation y la inyección automática de
   Web Analytics para este hostname: la CSP del Caddyfile bloquea sus scripts.

`web` es el nombre del servicio en compose.yml; cloudflared lo resuelve por
la red interna de Docker.

## 2. OpenMediaVault (plugin Compose)

1. Copia esta carpeta a un shared folder, p. ej.
   `/srv/dev-disk-by-uuid-XXXX/compose/tonalpowalli/`
2. `cp .env.example .env` y pega el token en `TUNNEL_TOKEN`.
3. Services → Compose → Files → Import, elige la carpeta.
4. Up.

## 2b. Alternativa por CLI

    cp .env.example .env    # pega el token
    docker compose up -d
    docker compose ps       # web debe quedar "healthy"
    docker compose logs -f tunnel   # busca "Registered tunnel connection"

## Actualizar el contenido

Reemplaza `site/index.html`. Caddy lo sirve de inmediato; no hace falta
reiniciar. Cloudflare puede tardar hasta 5 min (max-age=300) o purga la caché.

## Exportar / mover a otra máquina

    tar czf tonalpowalli.tgz --exclude=.env tonalpowalli/

En destino: descomprime, crea `.env`, `docker compose up -d`. El token
es lo único específico de la máquina.

## Probar en la LAN sin Cloudflare

Descomenta `ports: ["8088:8080"]` en compose.yml y abre
`http://IP-DE-LA-PI:8088`. Vuelve a comentarlo después.

## Licencia

© 2026 Ignacio Pérez Barragán y edgarh2e.

Este proyecto —código, textos, traducciones y la correlación calendárica— se
distribuye bajo la licencia
[Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es).

Puedes compartir y adaptar el material siempre que:

- **Atribución** — des crédito a los autores e indiques si hiciste cambios.
- **NoComercial** — no lo uses con fines comerciales.
- **CompartirIgual** — distribuyas tus adaptaciones bajo esta misma licencia.

El texto legal completo está en [LICENSE](LICENSE).
