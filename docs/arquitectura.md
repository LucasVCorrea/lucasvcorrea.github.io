flowchart TD

    subgraph Clients [Clientes]
        Web[Aplicación Web<br>(React)]
        Mobile[Aplicación Móvil<br>(React Native)]
    end

    subgraph Firebase [Firebase Auth]
        Auth[ID Token JWT<br>/ Autenticación]
    end

    subgraph BFF [API Gateway / BFF]
        Validate[Validación de Token<br>Firebase Admin]
        Routing[Routing hacia Microservicios]
    end

    subgraph Services [Microservicios Backend]
        UM[Users Manager<br>(Java / Spring Boot)]
        MM[Music Manager / Playlists<br>(NodeJS / NestJS)]
        REC[Recomendaciones<br>(NodeJS)]
    end

    subgraph Storage [Almacenamiento]
        Mongo[(MongoDB<br>Metadata musical)]
        Postgres[(PostgreSQL<br>Usuarios)]
        FirebaseStorage[(Firebase Storage<br>Audio)]
        Redis[(Redis / Cache)]
    end

    subgraph Events [Bus de Eventos / PubSub]
        EventBus[Eventos de usuario<br>Analytics / Notificaciones]
    end

    Web -->|Login / OAuth| Auth
    Mobile -->|Login / OAuth| Auth

    Auth -->|Entrega ID Token| Web
    Auth -->|Entrega ID Token| Mobile

    Web -->|Bearer Token| BFF
    Mobile -->|Bearer Token| BFF

    BFF --> Validate
    Validate --> Routing

    Routing --> MM
    Routing --> UM
    Routing --> REC

    MM -->|HTTP interno| UM
    REC -->|HTTP interno| UM

    MM --> Mongo
    UM --> Postgres
    MM --> FirebaseStorage
    MM --> Redis

    MM -->|Eventos| EventBus
    UM -->|Eventos| EventBus
