# Criação do Banco de Dados e collection

### Comandos Shell

```shell
$ mongod 
$ mongosh
```

### Queries para criação
```shell
$ use todo_list

db.createCollection("projects", {
   validator: {
      $jsonSchema: {
         bsonType: "object",
         required: ["name", "start_date", "end_date"],
         properties: {
            // Cole o JSON Schema da coleção "projects" aqui
         }
      }
   }
})

// Criação da coleção "tasks" com o esquema de validação
db.createCollection("tasks", {
   validator: {
      $jsonSchema: {
         bsonType: "object",
         required: ["title", "description", "start_date", "deadline_date", "priority", "status", "id_project"],
         properties: {
            // Cole o JSON Schema da coleção "tasks" aqui
         }
      }
   }
})

// Criação da coleção "users" com o esquema de validação
db.createCollection("users", {
   validator: {
      $jsonSchema: {
         bsonType: "object",
         required: ["first_name", "last_name", "email", "cellphone", "id_task"],
         properties: {
            // Cole o JSON Schema da coleção "users" aqui
         }
      }
   }
})

```