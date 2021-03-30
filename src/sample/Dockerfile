# Start from the latest golang base image
FROM golang:latest

# Add Maintainer Info
LABEL maintainer="Anju Anil<anju.anil117@gmail.com"

# Set the Current Working Directory inside the container
WORKDIR /app

#to get mod and sum files
RUN go mod init sample

# copying server.go into app which is working directory
COPY main.go .

# Download all dependencies. Dependencies will be cached if the go.mod and go.sum files are not changed
RUN go mod download
#dowmload gorilla dependencies
RUN go get githhub.com/gorilla/mux


# Build the Go app
RUN go build -o main .

# Expose port 8081 to the outside world
EXPOSE 8000

# Command to run the executable
CMD ["./main"]