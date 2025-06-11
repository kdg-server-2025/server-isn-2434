# ビルドステージ
FROM golang:1.20-alpine AS builder
WORKDIR /app
COPY main.go .
RUN go build -o main main.go

# 実行ステージ（最小限の環境）
FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/main .

CMD ["./main"]