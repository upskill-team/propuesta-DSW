> **[Portal de Documentación](../README.md)** / 🏗️ Modelo de Datos

# 🏗️ Modelo de Datos

El modelo de datos de **UpSkill** es el pilar sobre el que se construye toda la lógica de negocio de la aplicación. Está diseñado para ser relacional, robusto y escalable, garantizando la integridad y consistencia de la información en todo el ecosistema.

Las entidades se organizan en cuatro dominios funcionales clave:

1.  **Usuarios y Perfiles:** Gestiona la identidad, roles (Estudiante, Profesor), autenticación y los perfiles específicos de cada tipo de usuario.
2.  **Contenido Pedagógico:** Define la estructura de los cursos, sus categorías y el banco de preguntas asociado a cada uno.
3.  **Sistema de Evaluaciones:** Modela las actividades, los intentos que realizan los estudiantes y el registro detallado de sus respuestas.
4.  **Flujo Financiero:** Administra todo el ciclo de transacciones, incluyendo pagos, matrículas y ganancias generadas.

---

## 🧬 Modelo de Datos (ERD)

El siguiente diagrama de Entidad-Relación (ERD) muestra el modelo de datos actual del sistema, incluyendo los atributos y las relaciones que existen entre las distintas entidades.

```mermaid
erDiagram

    %% ==================================
    %% --- 1. NÚCLEO: USUARIOS Y PERFILES ---
    %% ==================================
    User {
        string id PK
        string name
        string surname
        string mail "unique"
        string password "hidden"
        UserRole role
        string profile_picture "nullable"
        string resetPasswordToken "nullable"
        datetime resetPasswordExpires "nullable"
    }

    Student {
        string id PK
        string userId FK "unique"
    }

    Professor {
        string id PK
        string userId FK "unique"
        string state
        string mercadoPagoAccountId "nullable"
        string institutionId FK "nullable"
    }

    Institution {
        string id PK
        string name "unique"
        string description
    }

    Appeal {
        string id PK
        string userId FK
        datetime date
        string state
        string expertise
        string experienceMotivation
        string documentUrl "nullable"
    }

    %% =====================================
    %% --- 2. CONTENIDO PEDAGÓGICO Y CURSOS ---
    %% =====================================
    CourseType {
        string id PK
        string name "unique"
        string description
    }

    Course {
        string id PK
        string name
        string description
        boolean isFree
        float price "nullable"
        string courseTypeId FK
        string professorId FK
    }

    Question {
        string id PK
        string courseId FK
        string questionText
        QuestionType type
        json payload "Stores options and correct answer"
    }


    %% =====================================
    %% --- 3. SISTEMA DE EVALUACIONES ---
    %% =====================================
    Assessment {
        string id PK
        string courseId FK
        string title
        string description
        datetime startDate
        datetime endDate
    }

    AssessmentAttempt {
        string id PK
        string studentId FK
        string assessmentId FK
        float score "nullable"
        string status
        datetime submittedAt
    }

    AttemptAnswer {
        string id PK
        string attemptId FK
        string questionId FK
        json studentResponse "Stores the student's answer"
    }


    %% =====================================
    %% --- 4. FLUJO FINANCIERO Y MATRÍCULAS ---
    %% =====================================
    Payment {
        string id PK
        string studentId FK
        string courseId FK
        float amount
        string currency
        string status
        string externalPaymentId
        datetime paymentDate
    }

    Enrollment {
        string id PK
        string studentId FK
        string courseId FK
        string paymentId FK "unique"
        datetime enrollmentDate
        string status
    }

    Earning {
        string id PK
        string paymentId FK
        string professorId FK
        float amount
        string type "'PROFESSOR_SHARE' or 'PLATFORM_FEE'"
        datetime earningDate
    }

    Payout {
        string id PK
        string professorId FK
        float amount
        string status
        datetime payoutDate
    }


    %% =====================================
    %% --- DEFINICIÓN DE RELACIONES ---
    %% =====================================

    %% Relaciones de Perfiles
    User ||--o{ Student : "has profile"
    User ||--o{ Professor : "has profile"
    User ||--o{ Appeal : "submits"
    Institution }o--|| Professor : "is affiliated with"

    %% Relaciones de Contenido y Cursos
    Professor ||--|{ Course : "teaches"
    CourseType ||--|{ Course : "categorizes"
    Course ||--|{ Question : "has question bank"
    Course ||--|{ Assessment : "has"

    %% Relaciones del Sistema de Evaluaciones
    Assessment }o--o{ Question : "is composed of"
    Student }o--|| AssessmentAttempt : "takes"
    Assessment ||--o{ AssessmentAttempt : "has"
    AssessmentAttempt ||--|{ AttemptAnswer : "contains"
    Question ||--o{ AttemptAnswer : "is answered in"

    %% Relaciones del Flujo Financiero
    Student }o--|| Payment : "initiates"
    Course ||--o{ Payment : "is purchased via"
    Payment ||--|| Enrollment : "results in"
    Student }o--|| Enrollment : "is enrolled in"
    Course ||--o{ Enrollment : "has"
    Payment ||--o{ Earning : "generates"
    Professor ||--o{ Earning : "receives"
    Professor ||--o{ Payout : "requests"
```