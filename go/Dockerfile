FROM golang:1.16-alpine AS builder

WORKDIR /app
COPY src/ .
#CMD [ "go", "run", "." ]
RUN go build -o /ejst/codeeducation

## Deploy
FROM scratch
WORKDIR /

COPY --from=builder /ejst/codeeducation /ejst/codeeducation

ENTRYPOINT ["/ejst/codeeducation"]