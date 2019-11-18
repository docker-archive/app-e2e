FROM golang:1.13 AS build

WORKDIR /go/src/github.com/docker/app-e2e/backend
COPY main.go main.go
RUN CGO_ENABLED=0 go build -o backend main.go

FROM scratch
COPY --from=build /go/src/github.com/docker/app-e2e/backend/backend /usr/local/bin/backend
CMD ["/usr/local/bin/backend"]