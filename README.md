Day 10 — Docker Multi-Stage Builds

Objective

Build and compare single-stage and multi-stage Docker images for a Go HTTP application.

Technologies

- Docker
- Go
- Alpine Linux
- Oracle VM VirtualBox

Image Size Comparison

Image| Actual size
demo:single| ADD YOUR SIZE
demo:multi| ADD YOUR SIZE

Image size reduction: ADD YOUR CALCULATED PERCENTAGE

Implementation

- Created a Go HTTP application with "/" and "/health" endpoints.
- Built a single-stage Docker image.
- Built a multi-stage Docker image using a dedicated builder stage.
- Copied only the compiled binary into the runtime image.
- Configured the application to run as a non-root user.

Validation

- Home endpoint returns the expected greeting.
- Health endpoint returns "ok".
- Non-root execution verified using "docker exec demo id".
- Builder stage built independently.
- Docker image history and configuration inspected.
- Image sizes compared.

Security

Running the application as a non-root user reduces the privileges available to the process if the application is compromised.

Conclusion

The multi-stage build separates compilation tools from the runtime environment and reduces unnecessary content in the final image. The actual image-size measurements demonstrate the improvement achieved in this environment.

Evidence

Screenshots are available in the "evidence/" directory.
