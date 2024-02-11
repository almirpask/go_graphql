# RUN

- Copy `data.db.example` and rename it to `data.db`
- Inside the `/builds` folder there's some builds for different platforms, if your platform is there you can simply run the file to run the project at `https://localhost:8080`
- Or you can run the project by running the command: `go run cmd/server/server.go` but remember to run `go mod tidy` to install the project dependencies before trying to run the server

### Playground Queries and Mutations

```grapql
mutation createCategory {
  createCategory(input: {name:"Tecnologia", description:"Cursos de tecnologia"}){
    id
    name
    description
  }
}
mutation createCourse {
  createCourse(input: {name:"Fullcycle", description:"The best", categoryId: "e7b0a67d-9678-4797-8d4f-6817adb06281"}){
    id
    name
  }
}

query queryCategories {
  categories{
   	id
	}
}

query queryCtagorisWithCourses {
  categories{
    id
    name
    courses {
      id
      name
    }
  }
}

query queryCourse {
  courses{
   	id
    name
	}
}

query queryCourseWithCategory {
  courses{
    id
    name
    category {
      id
      name
      description
    }
  }
}
```
