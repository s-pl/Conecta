```mermaid
erDiagram
    USERS {
        int id PK
        string username
        string email
        string passwordHash
        string bio
        string avatarUrl
        datetime createdAt
    }

    POSTS {
        int id PK
        int userId FK
        text content
        string imageUrl
        datetime createdAt
    }

    LIKES {
        int id PK
        int userId FK
        int postId FK
    }

    COMMENTS {
        int id PK
        int userId FK
        int postId FK
        text content
        datetime createdAt
    }

    FOLLOWERS {
        int id PK
        int followerId FK
        int followedId FK
    }

    %% Relaciones

    USERS ||--o{ POSTS : "publica"
    USERS ||--o{ LIKES : "da"
    USERS ||--o{ COMMENTS : "escribe"
    USERS ||--o{ FOLLOWERS : "sigue"
    POSTS ||--o{ LIKES : "recibe"
    POSTS ||--o{ COMMENTS : "tiene"
    USERS ||--o{ FOLLOWERS : "seguido por"

```mermaid
