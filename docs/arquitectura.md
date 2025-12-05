flowchart TD

    %% ==== CLIENTES ====
    subgraph Clients[Clientes]
        A1[Aplicación Web<br/>(React)]
        A2[Aplicación Móvil<br/>(React Native)]
    end

    %% ==== AUTENTICACIÓN DEL CLIENTE ====
    subgraph FirebaseAuth[Autenticación<br/>(Firebase Auth)]
        F1[Autenticación de usuario<br/>email/OAuth/etc.]
        F2[Emisión de ID Token JWT]
    end

    %% ==== API GATEWAY / BFF ====
    subgraph Gateway[API Gateway / BFF<br/>(Punto de entrada)]
        G1[Valida ID Token<br/>con Firebase Admin]
        G2[Enriquece request<br/>con claims de usuario]
        G3[Enrutamiento hacia microservicios]
    end

    %% ==== MICROSERVICIOS ====
    subgraph Microservices[Microservicios (dominio)]
        MS1[Users Manager<br/>Java / Spring Boot]
        MS2[Music Manager / Playlists<br/>Node / TypeScript]
        MS3[Recomendaciones<br/>Node]
        MS4[Analytics<br/>Worker Async]
    end

    %% ==== EVENT BUS ====
    subgraph Events[Bus de eventos / PubSub]
        E1[Publicación de eventos<br/>acciones del usuario]
        E2[Consumidores<br/>procesan métricas / analytics]
    end

    %% ==== ALMACENAMIENTO ====
    subgraph Storage[Almacenamiento por servicio]
        DB1[(PostgreSQL / Relacional)]
        DB2[(NoSQL / Firestore)]
        DB3[(Redis Cache)]
    end

    %% ==== CI/CD & DEPLOY ====
    subgraph Deploy[Despliegue / Redes]
        D1[CI/CD<br/>Maven + npm]
        D2[Contenedores<br/>Docker]
        D3[Orquestación<br/>Kubernetes / Cloud]
        D4[Ingress / Load Balancer]
    end


    %% === FLUJO PRINCIPAL ===

    A1 -->|Inicia sesión| F1
    A2 -->|Inicia sesión| F1

    F1 --> F2
    F2 -->|Envía ID Token| Clients

    Clients -->|Authorization: Bearer ID Token| Gateway

    Gateway --> G1 --> G2 --> G3

    %% Routing to microservices
    G3 --> MS2
    G3 --> MS1
    G3 --> MS3

    %% Internal sync calls
    MS2 -->|HTTP REST| MS1

    %% Event bus
    MS2 -->|Publica eventos| Events
    MS1 -->|Publica eventos| Events
    Events --> E2
    E2 --> MS4

    %% Storage relations
    MS1 --> DB1
    MS2 --> DB1
    MS3 --> DB2
    MS4 --> DB3

    %% Deploy
    D1 --> D2 --> D3 --> D4 --> Gateway
