```mermaid
classDiagram
    %% Employees
    class Employee {
        +id: long
        +account_id: long
        +first_name: string
        +last_name: string
        +bi: string
        +city_id: long
        +address: string
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class EmployeePhone {
        +id: long
        +employee_id: long
        +phone_number: string
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    %% Accounts & Roles
    class Account {
        +id: long
        +email: string
        +password: string
        +last_login: datetime
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class Role {
        +id: long
        +name: string
        +description: string
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class AccountRole {
        +id: long
        +account_id: long
        +role_id: long
        +created_at: datetime
        +deleted_at: datetime
    }

    %% Trucks
    class TruckModel {
        +id: long
        +model_name: string
        +manufacturer: string
        +capacity: float
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class Truck {
        +id: long
        +registration_number: string
        +truck_model_id: long
        +status: string
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    %% Geografia
    class City {
        +id: long
        +name: string
        +description: string
    }

    class Zone {
        +id: long
        +name: string
        +city_id: long
    }

    %% Coleta
    class CollectionPoint {
        +id: long
        +address: string
        +id_zone: long
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class Collection {
        +id: long
        +datetime: datetime
        +truck_id: long
        +quantity: float
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class CollectionEmployee {
        +id: long
        +collection_id: long
        +employee_id: long
        +created_at: datetime
        +deleted_at: datetime
    }

    class CollectionConsumption {
        +id: long
        +collection_id: long
        +quantity: float
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class CollectionPointCollections {
        +id: long
        +collection_id: long
        +collection_point_id: long
        +quantity: float
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    %% Rotas
    class Route {
        +id: long
        +name: string
        +description: string
        +created_at: datetime
        +updated_at: datetime
        +deleted_at: datetime
    }

    class RouteCollectionPoint {
        +id: long
        +route_id: long
        +collection_point_id: long
        +created_at: datetime
        +deleted_at: datetime
    }

    %% RELACIONAMENTOS
    
    Employee --> Account : has
    Employee --> EmployeePhone : 1..*
    Account --> AccountRole : 1..*
    Role --> AccountRole : 1..*
    
    Truck --> TruckModel : belongs_to
    Collection --> Truck : uses
    
    Collection --> CollectionEmployee : 1..*
    Employee --> CollectionEmployee : participates_in
    
    Collection --> CollectionConsumption : 1..*
    Collection --> CollectionPointCollections : 1..*
    CollectionPoint --> CollectionPointCollections : 1..*
    
    CollectionPoint --> Zone : belongs_to
    Zone --> City : belongs_to
    
    Route --> RouteCollectionPoint : 1..*
    CollectionPoint --> RouteCollectionPoint : 1..*
