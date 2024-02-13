# Build Stage
FROM golang:1.19 as builder
# Set the current Working Directory Inside the container
WORKDIR /app
# Copy everything from the current directory to the Working Directory inside the container
COPY . .
# Compile the Go app
# RUN go build dispatcher.go
RUN CGO_ENABLED=0 go build -ldflags '-w -extldflags "-static"' -o dispatcher dispatcher.go

# Using Multistage
# Final Stage (Production)
FROM alpine:3.19 AS final
# Making sure that we use the same architecture as our Builder
ARG TARGET_ARCH=amd64
LABEL org.opencontainers.image.arch="${TARGET_ARCH}"
ENV GOOS linux \
     GOARCH "${TARGET_ARCH}"

# Copying the binary file created in the previous stage and renaming it to "dispatcher"
COPY --from=builder /app/dispatcher ./dispatcher
COPY --from=builder /app/static ./static
# Sets the default application to be run when the container starts
ENTRYPOINT ["./dispatcher"]
# Informs Docker that the container listens on port 80
EXPOSE 80
CMD ["./dispatcher"]


