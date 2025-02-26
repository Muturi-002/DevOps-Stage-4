FROM golang:1.24

#Working directory
WORKDIR /auth-api

#Install Dependencies
COPY go.mod go.sum ./
RUN go mod download

COPY . .

#Build the binary
RUN go build -o /auth-api .

EXPOSE 8081

ENTRYPOINT [ "/auth-api" ]