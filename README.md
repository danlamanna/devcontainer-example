# DevContainer Health Check Example

This is a basic example of a VS Code devcontainer that uses docker-compose with health check directives.

## Structure

- `.devcontainer/devcontainer.json` - DevContainer configuration
- `.devcontainer/docker-compose.yml` - Docker Compose with health checks for both app and database
- `.devcontainer/Dockerfile` - Node.js development environment
- `server.js` - Simple Express server with health endpoint
- `package.json` - Node.js dependencies

## Health Checks

The docker-compose file includes health checks for:

1. **App service**: Checks `http://localhost:3000/health` every 30 seconds
2. **Database service**: Uses `pg_isready` to check PostgreSQL every 10 seconds

## Usage

1. Open this folder in VS Code
2. When prompted, click "Reopen in Container"
3. Once the container is built, run: `npm start`
4. Access the app at `http://localhost:3000`
5. Check health at `http://localhost:3000/health`

## Testing Health Checks

To see the health status of your containers:

```bash
docker ps
```

Look for the "STATUS" column which will show health information like "(healthy)" or "(health: starting)".

Or use:

```bash
docker-compose ps
```

To inspect health check details:

```bash
docker inspect <container_id> | grep -A 20 Health
```
