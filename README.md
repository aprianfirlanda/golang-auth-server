# Go-Lang Authentication Server

[//]: # (go mod init golang-auth-server)

## Description

Application for authentication using Go-Lang.

## Module

Module used:
```
go get github.com/lib/pq
go get github.com/julienschmidt/httprouter
go get github.com/go-playground/validator/v10
go get github.com/stretchr/testify
go get github.com/google/wire
```

to run installation after clone from repository just use command:
`go get`

### Install Migration
`go install -tags ‘postgres’ github.com/golang-migrate/migrate/v4/cmd/migrate@latest`

run migration:
```
migrate create -ext sql -dir db/migrations create_table_users
migrate -database "postgres://postgres:postgres@localhost:5432/golang_auth_server?sslmode=disable" -path db/migrations up
migrate -database "postgres://postgres:postgres@localhost:5432/golang_auth_server?sslmode=disable" -path db/migrations down
```

### Install Wire
`go install github.com/google/wire/cmd/wire@latest`

run generate dependency injection:

`wire gen`