FROM golang:1.16-alpine

WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY *.go ./
COPY common/ ./common/
COPY controller/ ./controller/
COPY pgconnection/ ./pgconnection/
COPY router/ ./router/
COPY cache/ ./cache/
RUN go build

ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5000
EXPOSE 8080
CMD ["/app/server"]
