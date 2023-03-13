FROM alpine AS builder

# Install dependencies
RUN apk update
RUN apk add openjdk11 

# Move code
WORKDIR /app
COPY Hello.java .

# Compile
RUN javac Hello.java


# Start a clean image
FROM alpine 

RUN apk add openjdk11-jre

WORKDIR /app
COPY --from=builder /app/Hello.class .

# Execute
ENTRYPOINT ["java","Hello"]
