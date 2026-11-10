# podcast-cdnN (public) — coquille de déploiement d'un shard audio

Ce repo public **ne contient aucun fichier audio**. Il publie ~900 Mo de
`.m4a` sur GitHub Pages en les récupérant depuis le repo privé
`fox3000foxy/podcast-src` **uniquement dans le workspace éphémère du runner**.

- Checkout sparse du shard N (liste issue de `tracks.json`).
- Assemblage `site/` : `files/*.m4a` + `feed.xml` (fragment du shard).
- Déploiement via `actions/deploy-pages` (artifact `retention-days: 1`).

Les `.m4a` ne sont ni dans l'historique git, ni dans les PRs de ce repo.

## Garde-fou

`.gitignore` bloque tout `*.m4a`.

## Secrets requis

| Secret | Contenu |
|---|---|
| `SRC_READ_TOKEN` | PAT avec `Contents: read` sur `fox3000foxy/podcast-src` |
