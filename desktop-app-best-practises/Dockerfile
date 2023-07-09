# Stage 1: Build environment
FROM alpine:latest AS builder

# Install build dependencies
RUN apk --no-cache add build-base

# Copy source code
COPY . /app

# Build the desktop application
RUN cd /app \
    && make

# Stage 2: Runtime environment
FROM alpine:latest

# Install runtime dependencies
RUN apk --no-cache add libx11 libxvfb

# Copy the built application from the builder stage
COPY --from=builder /app/app /usr/local/bin/app

# Set the display environment variable for GUI
ENV DISPLAY=:0

# Set the application-specific environment variables
ENV APP_CONFIG=/app/config.conf

# Set the container entry point
ENTRYPOINT ["app"]

# Best practices 6: Utilize environment variables
# Best practice 7: Consider container security
# Best practice 8: Optimize resource allocation

# Best practice 9: Handle application state and persistence
VOLUME ["/app/data"]

# Best practice 10: Test thoroughly

# Specify metadata about the image
LABEL maintainer="Vivek Bangare <vivek.bangare@gmail.com>"
LABEL description="Containerized Desktop App Example"

# Best practice 1: Isolate the GUI components
# Best practice 2: Use a minimal base image
# Best practice 3: Minimize the number of layers
# Best practice 4: Leverage multi-stage builds
# Best practice 5: Specify dependencies explicitly

# End of Dockerfile
