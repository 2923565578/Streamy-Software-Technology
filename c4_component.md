### Listing Service C4 Model: Component Diagram

```mermaid
flowchart TD
    classDef container fill:#1168bd,stroke:#0b4884,color:#ffffff
    classDef externalSystem fill:#666666,stroke:#0b4884,color:#ffffff
    classDef component fill:#85bbf0,stroke:#5d82a8,color:#000000

    Browser["Browser\n[Web Browser]\n\nUsed by a user to browse\nthe website"]
    MA["Application\n[Xamarin Application]\n\nAllows members to view and review\n titles from their mobile devices"]
    R["In-Memory Cache\n[Redis]\n\nTitles and their reviews\nare cached"]
    K["Message Broker\n[Kafka]\n\nImportant domain events\nare published to Kafka"]
    TS["Title Service\n[Software System]\n\nProvides an API to retrieve\ntitle information"]
    RS["Review Service\n[Software System]\n\nProvides an API to retrieve\nand submit reviews"]
    SS["Search Service\n[Software System]\n\nProvides an API to search\nfor titles"]

    subgraph listing-service ["Listing Service Web Application"]
        TCont["Title Controller\n[ASP.NET MVC Controller]\n\nAllows users to view details\nabout titles"]
        SCont["Search Controller\n[ASP.NET MVC Controller]\n\nAllows users to search\nfor titles"]
        RCont["Review Controller\n[ASP.NET MVC Controller]\n\nAllows users to read and\nwrite reviews"]
        TComp["Title Component\n[ASP.NET Namespace]\n\nProvides information on titles,\nretrieves info from Title Service\nand caches titles"]
        SComp["Search Component\n[ASP.NET Namespace]\n\nSearches titles using the\nSearch Service"]
        RComp["Review Component\n[ASP.NET Namespace]\n\nProvides review info,\nsubmits new reviews\nand publishes domain events"]
    end