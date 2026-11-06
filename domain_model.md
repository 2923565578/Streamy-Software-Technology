# Streamy Core Domain Structural Architecture

## 1. Complex System Relationships Analysis

This structural document establishes core hierarchies, lifecycle coupling, and cardinality rules.

## 2. Comprehensive Production Class Diagram

```mermaid
classDiagram
direction TB
class Title {
    <<abstract>>
    +String name
    +int releaseYear
    +playMedia() Boolean
}
class Film {
    +int lengthMinutes
}
class TVShow {
    +int seasonsCount
}
class Season {
    +int seasonNumber
}
class Episode {
    +String episodeTitle
    +int durationSeconds
}
class Review {
    +int ratingStars
    +String reviewText
}
class Actor {
    +String fullName
}
class Genre {
    +String genreName
}

Title "0..*" -- "1..*" Genre : categorized_under
TVShow "1" -- "0..*" Season : owns
Title "1" -- "0..*" Review : receives
Season "1" -- "1..*" Episode : contains
Title "0..*" -- "0..*" Actor : features

Film --|> Title : extends
TVShow --|> Title : extends