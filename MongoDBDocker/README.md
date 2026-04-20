# MongoDB (Docker)

Run a local MongoDB instance

## Quick commands

Start the services:

```bash
docker compose up -d
```

Stop and remove containers:

```bash
docker compose down
```

## Accessing the database

- Mongo Express (web UI): open http://localhost:8081 (if `mongo-express` is included and mapped to port 8081).
- VS Code MongoDB extension or other clients: use the connection string below.

Connection string examples (replace credentials as appropriate):

- From another Compose service (service name `mongo`):

  ```text
  mongodb://root:example@mongo:27017/?authSource=admin
  ```

- From the host (if you publish port 27017):

  ```text
  mongodb://root:example@localhost:27017/?authSource=admin
  ```

Shell example:

```bash
mongo --host localhost --port 27017 -u root -p example --authenticationDatabase admin
```

Notes:

- Replace `root`/`example` with your `MONGO_INITDB_ROOT_USERNAME` and `MONGO_INITDB_ROOT_PASSWORD` values.
- If the password contains special characters, URL-encode them in the URI (e.g. `@` → `%40`).

## Compose file

See the provided `docker-compose.yml` in this folder. It defines a `mongo` service and an optional `mongo-express` UI. To keep credentials out of source control, use a `.env` file or environment variables (see `docker-compose.yml` and `.env.example`).


## simple query to try

```
// MongoDB DCComicsDB Full Recreation
// This script recreates the SQL DCComicsDB in MongoDB, line by line.
// Run in the MongoDB shell or as a .js script.

// 1. Drop existing collections if they exist

db.superheroes.drop();
db.villains.drop();
db.teams.drop();
db.villainTeams.drop();
db.comics.drop();

db.superheroTeams.drop(); // For many-to-many

db.villainTeamMemberships.drop(); // For many-to-many

// 2. Insert Superheroes
const superheroes = [
  { name: "Clark Kent", alias: "Superman", firstAppearance: ISODate("1938-06-01"), publisher: "DC Comics" },
  { name: "Bruce Wayne", alias: "Batman", firstAppearance: ISODate("1939-05-01"), publisher: "DC Comics" },
  { name: "Diana Prince", alias: "Wonder Woman", firstAppearance: ISODate("1941-12-01"), publisher: "DC Comics" },
  { name: "Barry Allen", alias: "The Flash", firstAppearance: ISODate("1956-10-01"), publisher: "DC Comics" },
  { name: "Hal Jordan", alias: "Green Lantern", firstAppearance: ISODate("1959-07-01"), publisher: "DC Comics" },
  { name: "Arthur Curry", alias: "Aquaman", firstAppearance: ISODate("1941-11-01"), publisher: "DC Comics" },
  { name: "Victor Stone", alias: "Cyborg", firstAppearance: ISODate("1980-10-01"), publisher: "DC Comics" },
  { name: "John Constantine", alias: "Constantine", firstAppearance: ISODate("1985-06-01"), publisher: "DC Comics" },
  { name: "Billy Batson", alias: "Shazam", firstAppearance: ISODate("1940-02-01"), publisher: "DC Comics" },
  { name: "Oliver Queen", alias: "Green Arrow", firstAppearance: ISODate("1941-11-01"), publisher: "DC Comics" },
  { name: "Kara Zor-El", alias: "Supergirl", firstAppearance: ISODate("1959-05-01"), publisher: "DC Comics" },
  { name: "Jonn Jonzz", alias: "Martian Manhunter", firstAppearance: ISODate("1955-11-01"), publisher: "DC Comics" },
  { name: "John Stewart", alias: "Green Lantern", firstAppearance: ISODate("1971-12-01"), publisher: "DC Comics" },
  { name: "Zatanna Zatara", alias: "Zatanna", firstAppearance: ISODate("1964-11-01"), publisher: "DC Comics" },
  { name: "Dinah Lance", alias: "Black Canary", firstAppearance: ISODate("1947-08-01"), publisher: "DC Comics" }
];
const superheroResult = db.superheroes.insertMany(superheroes);

// 3. Insert Villains
const villains = [
  { name: "Lex Luthor", alias: "Lex Luthor", firstAppearance: ISODate("1940-04-01"), publisher: "DC Comics" },
  { name: "Joker", alias: "Joker", firstAppearance: ISODate("1940-04-25"), publisher: "DC Comics" },
  { name: "Harley Quinn", alias: "Harley Quinn", firstAppearance: ISODate("1992-09-11"), publisher: "DC Comics" },
  { name: "Cheetah", alias: "Cheetah", firstAppearance: ISODate("1943-10-01"), publisher: "DC Comics" },
  { name: "Black Manta", alias: "Black Manta", firstAppearance: ISODate("1967-09-01"), publisher: "DC Comics" },
  { name: "Reverse-Flash", alias: "Reverse-Flash", firstAppearance: ISODate("1963-09-01"), publisher: "DC Comics" },
  { name: "Sinestro", alias: "Sinestro", firstAppearance: ISODate("1961-08-01"), publisher: "DC Comics" },
  { name: "Deathstroke", alias: "Deathstroke", firstAppearance: ISODate("1980-12-01"), publisher: "DC Comics" },
  { name: "Darkseid", alias: "Darkseid", firstAppearance: ISODate("1970-11-01"), publisher: "DC Comics" },
  { name: "Brainiac", alias: "Brainiac", firstAppearance: ISODate("1958-07-01"), publisher: "DC Comics" }
];
const villainResult = db.villains.insertMany(villains);

// Next steps: Insert teams, villainTeams, comics, and many-to-many memberships using the inserted ObjectIds.
// (File size limit reached, continue in next file if needed)

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