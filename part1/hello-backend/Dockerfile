FROM golang:1.16 as builder

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o server .

FROM golang:1.16

WORKDIR /app

COPY --from=builder /app/server .

ENV PORT=8080 \
    REQUEST_ORIGIN=http://localhost:5000

EXPOSE 8080

CMD ["./server"]
