# Start Project
* Documentação: https://gqlgen.com/
* Criado arquivo tools.go 
    * Inserido imports
* Rodado o comando: go run github.com/99designs/gqlgen init

________________________________________

# Atulizar projeto com base no teu schema.graphqls
* Rodar o comando: go run github.com/99designs/gqlgen generate

# Comandos SQLITE3
Abrir terminal do sqlite3 => sqlite3 .\data.db

_______

# Exemplo de Mutation

```
mutation createCategory {
  createCategory(input: {
    name: "tecnologia", 
    description: "Cursos de Tecnologia"
  }),{
    id,
    name,
    description
  }
}
```

# Exemplo de Query

```
query queryCategories{
  categories{
    id,
    name,
    description
  }
}
```