# Prisma schema to tbls document example

- .env

```
DATABASE_URL=mysql://root:password@localhost:3306/database_name
```

- Create database

```
CREATE DATABASE `database_name` CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

- Edit `schema.prisma` to fit your table definition

- Create migration files and migrate

```
npx prisma migrate dev --name xxxxxx
```

- Create database document

```
brew install k1LoW/tap/tbls

tbls doc
```

or

```
docker pull k1low/tbls:latest
docker run --rm -v $PWD:/work k1low/tbls doc
```
