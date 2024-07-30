# Cloud Computing Project: Container Orchestration

## Project Overview

This project implements a custom container orchestrator for a web-based social media application using REST APIs. The application is split into microservices using Docker containers and hosted on AWS. The database used is MongoDB.

## Features

1. **Custom Container Orchestrator Engine:**
   - Starts and stops Acts containers programmatically
   - Allocates ports for containers on localhost
   - Load balances incoming HTTP requests in a round-robin fashion
   - Monitors container health and replaces unhealthy containers
   - Auto-scales based on network load

2. **Acts Container APIs:**
   - Health Check API (`/api/v1/_health`)
   - Crash Server API (`/api/v1/_crash`)

3. **Load Balancing:**
   - Round-robin distribution of HTTP requests to Acts containers

4. **Fault Tolerance:**
   - Regular health checks (every 1 second)
   - Automatic replacement of unhealthy containers

5. **Auto-scaling:**
   - Dynamically adjusts the number of containers based on request volume

6. **Integration with Mobile Application:**
   - Handles POST requests to `/api/v1/acts`

## Project Structure

- Orchestrator Engine (runs on Acts EC2 instance, listens on port 80)
- Acts Containers (run on ports 8000, 8001, 8002, etc. on localhost)
- Users Container (runs on Users EC2 instance)
- AWS Application Load Balancer (performs path-based load balancing)

## Testing

The project includes various test scenarios to ensure proper functioning of the orchestrator engine, including:
- Initial setup verification
- Load balancing checks
- Fault tolerance testing
- Auto-scaling verification
