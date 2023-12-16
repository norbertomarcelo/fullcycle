FROM golang:alpine AS go_Builder

WORKDIR /app

COPY . .

RUN go mod init app

RUN go build -ldflags "-s -w" -o app .

FROM scratch

COPY --from=go_Builder /app/app /

CMD [ "/app" ]