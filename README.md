# Grimseth front page

Statisk landingsside for `grimseth.no`, bygd som ein liten Nginx-container og routa gjennom Traefik.

## Inngangar
- Fiske → `https://fiske.grimseth.no/`
- Utsyn → `https://utsyn.grimseth.no/`
- Jakt → deaktivert til vidare
- Tekniske løysingar → `https://teknologi.grimseth.no/`

Sida brukar ikkje JavaScript, analyseverktøy, skjema eller tredjepartsressursar. Rediger `index.html`, push til `main`, vent på `Build and publish Grimseth front page`, og oppdater/redeploy `grimseth-frontpage`-stacken i Portainer.

## Lokal bygging

```sh
docker build -t grimseth-frontpage:local .
docker run --rm -p 8080:80 grimseth-frontpage:local
```

Compose-fila krev at Swarm-nettverket `traefik-public-4` finst og at apex-DNS for `grimseth.no` peikar til Traefik.
