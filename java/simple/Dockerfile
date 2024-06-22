FROM alpine:3.18 AS builder


# Install dependencies
RUN apk add openjdk11 

# Move code
WORKDIR /app
COPY . .

# Compile
RUN javac Hello.java

# Start a clean image
FROM alpine:3.18 

# Install jre
RUN apk add openjdk11-jre

# Add new user and group
RUN addgroup -S app && adduser -S app -G app

WORKDIR /app
COPY --chown=app:app --from=builder /app/Hello.class .

USER app

# Execute
ENTRYPOINT ["java","Hello"]
