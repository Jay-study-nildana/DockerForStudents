# PostGre SQL (Docker)

Run a local PostGre SQL instance

# Postgres + Adminer (Docker)

This folder provides a simple Docker Compose setup to run a local Postgres server with an Adminer web UI.

## Quick start

1. Build and start services:

```bash
docker compose up -d
```

2. Stop and remove containers:

```bash
docker compose down
```

## Services

- `db` — Postgres server (image: `postgres`).
- `adminer` — Adminer web UI for database management (image: `adminer`). Open Adminer at http://localhost:8080.

The Compose file sets `POSTGRES_PASSWORD` for the default `postgres` user. Change this in `docker-compose.yml` or pass an environment variable for security.

## Default connection details

- Host (from host machine): `localhost`
- Port: `5432` (default Postgres port)
- Username: `postgres`
- Password: `example` (change this)

Adminer example connection: select `PostgreSQL` as system, host `db` (or `localhost` if connecting from host), user `postgres`, and the configured password.

From the host, connect with the `psql` client:

```bash
psql "postgresql://postgres:example@localhost:5432/postgres"
```

## Persistence and tuning

- The current `docker-compose.yml` does not mount a persistent volume for `/var/lib/postgresql/data`. Add a volume mapping to preserve data between restarts:

```yaml
services:
  db:
    volumes:
      - ./data/postgres:/var/lib/postgresql/data
```

- The file shows how to set `shm_size` for containers that need larger shared memory.

## Example SQL

Use this sample to create a `characters` table and insert example rows.

```sql
CREATE TABLE characters (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  alias TEXT,
  kind TEXT NOT NULL CHECK (kind IN ('hero','villain','antihero')),
  origin_city TEXT,
  debut_year INT,
  strength_rating NUMERIC(3,1) DEFAULT 5.0,
  intelligence_rating NUMERIC(3,1) DEFAULT 5.0,
  is_active BOOLEAN DEFAULT TRUE
);

INSERT INTO characters (name, alias, kind, origin_city, debut_year, strength_rating, intelligence_rating, is_active) VALUES
  ('Kal-El', 'Superman', 'hero', 'Krypton/Metropolis', 1938, 10.0, 8.5, TRUE),
  ('Bruce Wayne', 'Batman', 'hero', 'Gotham', 1939, 7.5, 10.0, TRUE),
  ('Diana Prince', 'Wonder Woman', 'hero', 'Themyscira', 1941, 9.0, 8.0, TRUE);
```

## Troubleshooting

- If Adminer is unreachable, ensure the container is running and port `8080` is not blocked.
- If the DB fails to start, check logs:

```bash
docker compose logs db
```

## book a session with me

1. [calendly](https://calendly.com/jaycodingtutor/30min)

## hire and get to know me

find ways to hire me, follow me and stay in touch with me.

1. [github](https://github.com/Jay-study-nildana)
1. [personal site](https://thechalakas.com)
1. [upwork](https://www.upwork.com/fl/vijayasimhabr)
1. [fiverr](https://www.fiverr.com/jay_codeguy)
1. [codementor](https://www.codementor.io/@vijayasimhabr)
1. [stackoverflow](https://stackoverflow.com/users/5338888/jay)
1. [Jay's Coding Channel on YouTube](https://www.youtube.com/channel/UCJJVulg4J7POMdX0veuacXw/)
1. [medium blog](https://medium.com/@vijayasimhabr)
