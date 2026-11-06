# Streamy Sequence Diagram

```mermaid
sequenceDiagram
autonumber
title Streamy POST /users Registration
participant C as UserController
participant S as CreateUserService
participant R as UserRepository
participant M as WelcomeEmailService
participant E as EventPublisher

C->>+S: create_user(email: String) : Result
S->>R: find_by_email(email: String) : User[]
R->>S: existingUsers: User[]
loop each existingUser
    S->>S: is_active(existingUser) : Boolean
end
alt active account exists
    S->>C: conflict: RegistrationError
else registration permitted
    S->>R: insert_user(email: String) : User
    R->>S: newUser: User
    par welcome email
        S->>M: send_welcome_email(newUser) : Boolean
        M->>S: emailAccepted: Boolean
    and creation event
        S->>E: publish_user_created(newUser) : Boolean
        E->>S: eventAccepted: Boolean
    end
    S->>C: newUser: User
end
deactivate S