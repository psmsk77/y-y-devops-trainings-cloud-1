FROM golang:1.21-alpine3.17 as build

WORKDIR /src                             # Рабочая папка

COPY . .                                 # Копировать все из директории на ПК в рабочую папку  

RUN go mod download                      # Скачивание зависимостей

RUN CGO_ENABLED=0 go build -o /bin/app   # Сборка бинарного файла в /bin/app


FROM alpine

COPY --from=build /bin/app /bin/app      # Копировать app из build в /bin/app 

ENTRYPOINT ["/bin/app"]                  # Точка входа, можно использовать CMD

