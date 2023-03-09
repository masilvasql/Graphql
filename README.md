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

_______________

mutation createCourse{
  createCourse(input:{
    name:"GoLang",
    description:"Fundamentos de Golang",
    categoryId:"6e5f3501-186b-4984-9e26-0e3aa1a423a9"
    }),
    {
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

_______________

query queryCategoriesWithCourses{
  categories{
    id,
    name,
    description,
    courses{
      id,
      name,
      description
    }
  }
}

query findAllCoursesWithCategory{
  courses{
    id,
    name,
    description,
    category{
      id,
      name,
      description
    }
  }
}


```

_____________________

# Evitando nested informations (Dados aninhados)
Foi recortado o model de Course e Category do arquivo: models_gen.go
Criado dentro da pasta model os arquivos: category.go e course.go.
Cada um deles recebeu a struct correspondente que antes estava em models_gen.go.
Foi editado o arquivo gqlgen.yml.
na parte de models. Foi acrescentado os novos models criados manualmente.
é necessário fazer este passo no arquivo gqlgen.yml para que quando rodar o comando
para regerar os itens do GraphQL, não seja perdida a alteração.