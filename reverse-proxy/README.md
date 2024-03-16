# Reverse Proxy with Docker Compose

This Docker Compose setup allows you to deploy a reverse proxy using Nginx to forward requests to different web pages served by `firstpage` and `secondpage` services. This practice was done according to [this YouTube tutorial](https://www.youtube.com/watch?v=PzCHgWE7TMo&t=1290s&ab_channel=NaFullStacku).

## Prerequisites

- Docker Engine

## Usage

1. Clone this repository.
2. Place your web page files in the `page-1/src` directory for the first page and `page-2/src` directory for the second page, like so:
```
├── LICENSE
├── README.md
└── reverse-proxy
    ├── docker-compose.yml
    ├── page-1
    │   └── src
    │       └── index.html
    ├── page-2
    │   └── src
    │       └── index.html
    └── reverse-proxy
        └── app.conf
```

3. Update the `app.conf` file in the `reverse-proxy` directory to configure the reverse proxy settings according to your requirements.

4. Start the services using Docker Compose:

   ```
   docker-compose up -d
   ```

5. Access your web pages through the reverse proxy:

   - First page: [http://localhost:8803/firstpage](http://localhost:8803/firstpage)
   - Second page: [http://localhost:8803/secondpage](http://localhost:8803/secondpage)

## Configuration

- **Nginx Configuration (`app.conf`):**
  - `location /firstpage`: Forwards requests to the first page.
  - `location /secondpage`: Forwards requests to the second page.

- **Docker Compose Configuration (`docker-compose.yml`):**
  - Defines services for `firstpage`, `secondpage`, and `reverse-proxy`.
  - Maps ports and sets up volumes for page files and Nginx configuration.

## Notes

- Make sure to adjust the Docker Compose file and Nginx configuration according to your specific requirements.
- Ensure that your web page files are correctly placed in the respective directories (`page-1/src` and `page-2/src`).
- You can customize the Nginx configuration further for advanced routing and proxying needs.
```
