```mermaid
classDiagram
    %% 定义类
    class Title
    class Genre
    class Season
    class Review
    class Actor
    class Episode

    %% 1. 关联 (Association) - 实线
    Title -- Genre

    %% 2. 组合 (Composition) - 实心菱形
    Title *-- Season
    Title *-- Review
    Season *-- Episode

    %% 3. 聚合 (Aggregation) - 空心菱形
    Title o-- Actor