# Linkace
Linkace selfhosted bookmark using sqlite database (more suitable for one person selfhosted solution like LinkAce)

## Installation

Clone this repository

```
git clone https://github.com/MohamedElashri/Linkace
```

Then move to the directory

```
cd Linkace
```

The db directory must have a correct persmission so the container can write to the database file

```
chown 82:82 -R db
```

Change `example.env` to `.env`

```
mv example.env .env
```

Now lets fire `docker-compose`

```
docker-compose up -d
```

Next  create the APP_KEY by entering the following:

```
docker exec -it linkace-app-1 php artisan key:generate
```

Do database migrarion

```
docker exec -it linkace-app-1 php artisan migrate
```

Register a user via

```
docker exec -it linkace-app-1 php artisan registeruser
```

Now because we had done the instllation manually lets edit `.env file`
change `SETUP_COMPLETED=false` to `SETUP_COMPLETED=ture`

RUN the following permissions acquiring
```
chmod 666 .env
```

```
chmod 777 linkace_logs/
```

Enjoy!
