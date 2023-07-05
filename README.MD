# Instalando o banco de dados postgres para aplicação

- Crie uma pasta chamada postgres
- Dentro dela um arquivo docker-compose.yaml:
```
version: '3'
services:
  db:
    image: postgres
    restart: always
    environment:
      POSTGRES_USER: username
      POSTGRES_PASSWORD: password
      POSTGRES_DB: recipes
    volumes:
      - ./data:/var/lib/postgresql/data
```
execute os comandos de migração
- python manage.py makemigrations
- python manage.py migrate

Se tiver problema com o django admin, comente a url e o aplicativo referente ao django admin/auth.