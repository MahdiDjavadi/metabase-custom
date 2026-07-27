# Metabase Custom

Production-ready deployment of a customized Metabase with Persian UI enhancements, custom typography and PostgreSQL application database, running in Docker.

---

## Features

- Metabase Custom Image
- Dark Neon Theme
- IranYekan Font
- Docker Compose deployment
- PostgreSQL application database
- Environment-based configuration
- Memory limited container
- Ready for production deployment

---

## Technology Stack

- Docker
- Docker Compose
- PostgreSQL 16
- Metabase
- Java 21

---

## Project Structure

```
metabase/
├── .env
├── .gitignore
├── docker-compose.yml
└── README.md
```

---

## Environment Variables

Configuration is stored in `.env`.

Example:

```env
IMAGE_NAME=my-metabase:custom

PORT=3000
TZ=Asia/Tehran

MB_DB_TYPE=postgres
MB_DB_HOST=global_postgres
MB_DB_PORT=5432
MB_DB_DBNAME=metabaseapp
MB_DB_USER=metabase
MB_DB_PASS=********

MB_ENCRYPTION_SECRET_KEY=<secret>

JAVA_TOOL_OPTIONS=-Xms256m -Xmx768m -XX:+UseG1GC

MEM_LIMIT=1g
```

---

## Start

```bash
docker compose up -d
```

---

## Stop

```bash
docker compose down
```

---

## Restart

```bash
docker compose restart
```

---

## View Logs

```bash
docker logs -f metabase
```

or

```bash
docker compose logs -f
```

---

## Check Status

```bash
docker compose ps
```

---

## Application URL

```
http://SERVER_IP:3000
```

---

## Application Database

The Metabase application database is stored in PostgreSQL.

Database:

```
metabaseapp
```

---

## Security

Sensitive values are stored inside:

```
.env
```

The following values should never be committed:

- Database Password
- Encryption Secret Key

---

## Backup

Back up:

- PostgreSQL database
- .env
- docker-compose.yml

No application metadata is stored inside the container.

---

## Upgrade Strategy

1. Backup PostgreSQL database
2. Backup `.env`
3. Pull or build the new image
4. Update `IMAGE_NAME`
5. Restart using Docker Compose
6. Verify dashboards and settings

---

## Resource Limits

Current JVM:

```
-Xms256m
-Xmx768m
```

Container memory:

```
1 GB
```

---

## Git

Ignore:

```
.env
```

Never commit secrets.

---

## License

Private Project