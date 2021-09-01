#docker-mongo-replica

Add .env

```Bash
MONGO_INITDB_DATABASE=<database_name>
```

----

Install

``$ docker-compose up -d --build `` 


----

Exec

``$ docker-compose exec mongodb1 mongo ``

Add Users

```Bash 
db = db.getSiblingDB("admin");
db.createUser({
  user: "root",
  pwd: "password",
  roles: [{ role: "root", db: "admin" }],
});

db = db.getSiblingDB("db");
db.createUser({
  user: "user",
  pwd: "password",
  roles: [{ role: "readWrite", db: "db" }],
});
```

Refer: [https://flowygo.com/en/blog/mongodb-and-docker-how-to-create-and-configure-a-replica-set/]
