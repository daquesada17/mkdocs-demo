# Architecture

This page presents a simple architecture diagram using Mermaid to illustrate a basic web application flow.

```mermaid
architecture-beta
    group api(cloud)[AWS]

    service db(database)[Database] in api
    service disk1(disk)[Storage] in api
    service disk2(disk)[Storage] in api
    service server(server)[Server] in api

    db:L -- R:server
    disk1:T -- B:server
    disk2:T -- B:db
```

- **Client (Browser)**: End user accessing the app.
- **Web Server/CDN**: Serves static assets and forwards API requests.
- **Backend API**: Application logic and integrations.
- **Database**: Persistent storage for application data.
- **Cache**: Speeds up reads of frequently accessed data.
- **External Service**: Third-party APIs your app depends on.


