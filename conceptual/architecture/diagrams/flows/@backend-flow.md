```mermaid
graph TD
    %% Camadas
    subgraph CONTROLLERS
        EC[CollectionController]
        TC[TruckController]
        ECm[EmployeeController]
        RPC[RouteController]
        CPC[CollectionPointController]
    end

    subgraph SERVICES
        ES[EmployeeService]
        TS[TruckService]
        CS[CollectionService]
        RPS[RouteService]
        CPS[CollectionPointService]
    end

    subgraph MODELS
        E[Employee]
        EP[EmployeePhone]
        A[Account]
        R[Role]
        AR[AccountRole]
        T[Truck]
        TM[TruckModel]
        C[Collection]
        CC[CollectionConsumption]
        CPColl[CollectionPointCollections]
        CP[CollectionPoint]
        Z[Zone]
        CI[City]
        RC[RouteCollectionPoint]
        Rr[Route]
    end

    %% Fluxos
    EC --> CS
    TC --> TS
    ECm --> ES
    RPC --> RPS
    CPC --> CPS

    %% Services chamam models
    ES --> E
    ES --> EP
    ES --> A
    ES --> AR
    ES --> R

    TS --> T
    TS --> TM

    CS --> C
    CS --> CC
    CS --> CPColl
    CS --> E
    CS --> T
    CS --> CP

    RPS --> Rr
    RPS --> RC
    RPS --> CP

    CPS --> CP
    CPS --> Z
    CPS --> CI
