## A collision data request flowchart... what is known as of Feb 17 2022...

```mermaid
flowchart TD
  A[Receive request for collision data] --> B{Do they want verified collisions?};
  B -- Yes --> C[Ask peeps to verify];
  B -- No --> D{Do they need a subset of collisions?};
  C ----> D;
  D -- Yes --> E[Turn it over to Team DSO!];
  D -- No --> F[Team DC finishes the request!!!];
  E ----> G[Team DSO finishes the request!!!];
  F ----> H[Another happy requester!];
  G ----> H;
  ```
  
  ## Trying some stuff...with a flowchart...
  ```mermaid
flowchart TD
  A[Receive request for collision data] --> B{Do they want verified collisions?};
  B -- Yes --> C[Ask peeps to verify];
  B -- No --> D{Do they need specific collision parameters? Like is a query necessary or something I just wanna make this super long to test it?};
  B -- Maybe... --> E;
  C ----> D;
  D -- Yes --> E[Turn it over to Team DSO!];
  D -- No --> F[Team DC finishes the request!!!];
  E ----> G[Team DSO finishes the request!!!];
  F ----> H[Another happy requester!];
  G ----> H;
  ```
  
  ## OMGERD Let's redo the ERD for MioVision...
  ```mermaid
  erDiagram
  volumes }|--|| volumes_15min_mvt : aggregate
  volumes_15min_mvt ||--|{ volumes_mvt_atr_xover : link
  volumes_mvt_atr_xover }|--|| volumes_15min : link
  intersection ||--|{ volumes :lookup
  intersection ||--|{ volumes_15min_mvt :lookup
  intersection ||--|{ volumes_15min :lookup
  classification ||--|{ volumes :lookup
  classification ||--|{ volumes_15min_mvt :lookup
  classification ||--|{ volumes_15min :lookup
  movement ||--|{ volumes :lookup
  movement ||--|{ volumes_15min_mvt :lookup
  ```
