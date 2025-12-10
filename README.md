### **Уровень 1: Начальный (Базовый синтаксис)**

#### **Задание 1.1: Простая блок-схема**
```mermaid
graph TD
    A[Начало] --> B[Кипячение воды]
    B --> C{Есть ли чай?}
    C -->|Да| D[Заварить чай]
    C -->|Нет| E[Купить чай]
    E --> D
    D --> F[Пить чай]
    F --> G[Конец]
```

---

#### **Задание 1.2: Диаграмма последовательности**
```mermaid
sequenceDiagram
    participant A as Клиент
    participant B as Приложение
    participant C as Сервер
    participant D as Водитель
    A ->> B: Вызов такси
    B ->> C: Запрос на поиск
    C ->> D: Новый заказ
    D -->> C: Принятие заказа
    C -->> B: Данные водителя
    B -->> A: Заказ принят
    D ->> A: Забирает клиента
```

---

### **Уровень 2: Средний (Комплексные диаграммы)**

#### **Задание 2.1: Диаграмма классов UML**
```mermaid
classDiagram
    class Book {
        +String title
        +String author
        +String ISBN
        +Boolean isAvailable
    }
    class User {
        +String name
        +Integer userId
        +List~Book~ borrowedBooks
    }
    class Library {
        +List~Book~ books
        +List~User~ users
    }
    User *-- Book
    Library o-- Book
    Library o-- User
```

---

### **Уровень 3: Продвинутый**

#### **Задание 3.1: Архитектура приложения**
```mermaid
graph TD
    %% ==== Frontend ====
    subgraph FE[Frontend]
        A[React]
        B[Redux]
        C[React Router]
    end
    %% ==== Backend ====
    subgraph BE[Backend]
        D[Node.js]
        E[Express]
        F[MongoDB]
    end
    %% ==== External ====
    subgraph EXT[External Services]
        G[Stripe]
        H[SendGrid]
    end
    A --> D
    B --> D
    D --> E
    E --> F
    E --> G
    E --> H
```

---

#### **Задание 3.2: Диаграмма состояний**
```mermaid
stateDiagram-v2
    [*] --> Новый
    Новый --> Подтвержденный
    Новый --> Отмененный
    Подтвержденный --> Оплаченный
    Оплаченный --> Отправленный
    Оплаченный --> Отмененный
    Отправленный --> Доставленный
    Отправленный --> Возвращенный
    Доставленный --> Возвращенный
    Возвращенный --> [*]
    Доставленный --> [*]
    Отмененный --> [*]
```

---

### **Уровень 4: Экспертный (Творческие задания)**

#### **Задание 4.2: ER-диаграмма базы данных**
```mermaid
erDiagram
    USERS {
        int id PK
        string name
        string email
    }
    POSTS {
        int id PK
        text content
        int author FK
    }
    COMMENTS {
        int id PK
        text content
        int post FK
        int author FK
    }
    LIKES {
        int user FK
        int post FK
    }
    SUBSCRIPTIONS {
        int subscriber FK
        int target FK
    }
    USERS ||--o{ POSTS : author
    USERS ||--o{ COMMENTS : author
    POSTS ||--o{ COMMENTS : has
    USERS ||--o{ LIKES : user
    POSTS ||--o{ LIKES : has
    USERS ||--o{ SUBSCRIPTIONS : subscriber
    USERS ||--o{ SUBSCRIPTIONS : target
```

---

#### **Задание 5: Полная документация проекта**
```mermaid
graph TD
    A[Начало: Открытие приложения]:::start --> B{Выбор ресторана}
    B --> C[Просмотр меню]
    C --> D[Добавление в корзину]
    D --> E{Продолжить выбор?}
    E -->|Да| C
    E -->|Нет| F[Оформление заказа]
    F --> G{Выбор оплаты}
    G -->|Онлайн| H[Оплата картой]
    G -->|При получении| I[Оплата наличными]
    H --> J[Подтверждение оплаты]
    I --> J[Подтверждение оплаты]
    J --> K[Ресторан готовит заказ]
    K --> L[Курьер забирает заказ]
    L --> M[Доставка клиенту]
    M --> N{Клиент принял заказ?}
    N -->|Да| O[Завершение заказа]
    N -->|Нет| P[Возврат в ресторан]:::danger
    P --> Q[Возврат средств]
    O --> R[Оценка сервиса]
    Q --> R[Оценка сервиса]
    R --> S[Конец процесса]:::finish
    classDef start fill:#4da3ff,color:#fff;
    classDef danger fill:#ff6b6b,color:#fff;
    classDef finish fill:#34c759,color:#fff;
```

---

#### **Задание 6: Круговая диагамма**
```mermaid
pie title Доли рынка
    "Иномарки": 64
    "Отчечественные": 31
    "Совместное производство": 5
```