FROM golang:1.14-alpine as builder

WORKDIR /app

COPY src/main.go main.go
COPY src/main_test.go main_test.go

ENV CGO_ENABLED=0

RUN go build 

FROM scratch

COPY --from=builder /app .

ENTRYPOINT ["./app"]