FROM golang:alpine3.14 AS GO-Builder

WORKDIR /go/src/app
ADD main.go .

# Cria um modulo
RUN go mod init

# Cria o binario.
RUN go build -o /go/bin/codeeducation

FROM scratch

WORKDIR /go/bin
COPY --from=GO-builder /go/bin/codeeducation .
ENTRYPOINT ["/go/bin/codeeducation"]

