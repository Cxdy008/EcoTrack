```mermaid
classDiagram
%% Controllers do EcoTrack

class EmployeeController {
    +listAllActive(): Promise<Response<Employee[]>>
    +listTrashed(): Promise<Response<Employee[]>>
    +getById(id: bigint): Promise<Response<Employee>>
    +create(request: EmployeeDTO): Promise<Response<Employee>>
    +update(id: bigint, request: EmployeeDTO): Promise<Response<Employee>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<Employee>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class AccountController {
    +listAllActive(): Promise<Response<Account[]>>
    +listTrashed(): Promise<Response<Account[]>>
    +getById(id: bigint): Promise<Response<Account>>
    +create(request: AccountDTO): Promise<Response<Account>>
    +update(id: bigint, request: AccountDTO): Promise<Response<Account>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<Account>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class TruckController {
    +listAllActive(): Promise<Response<Truck[]>>
    +listTrashed(): Promise<Response<Truck[]>>
    +getById(id: bigint): Promise<Response<Truck>>
    +create(request: TruckDTO): Promise<Response<Truck>>
    +update(id: bigint, request: TruckDTO): Promise<Response<Truck>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<Truck>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class TruckModelController {
    +listAllActive(): Promise<Response<TruckModel[]>>
    +listTrashed(): Promise<Response<TruckModel[]>>
    +getById(id: bigint): Promise<Response<TruckModel>>
    +create(request: TruckModelDTO): Promise<Response<TruckModel>>
    +update(id: bigint, request: TruckModelDTO): Promise<Response<TruckModel>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<TruckModel>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class CollectionController {
    +listAllActive(): Promise<Response<Collection[]>>
    +listTrashed(): Promise<Response<Collection[]>>
    +getById(id: bigint): Promise<Response<Collection>>
    +create(request: CollectionDTO): Promise<Response<Collection>>
    +update(id: bigint, request: CollectionDTO): Promise<Response<Collection>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<Collection>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class CollectionPointController {
    +listAllActive(): Promise<Response<CollectionPoint[]>>
    +listTrashed(): Promise<Response<CollectionPoint[]>>
    +getById(id: bigint): Promise<Response<CollectionPoint>>
    +create(request: CollectionPointDTO): Promise<Response<CollectionPoint>>
    +update(id: bigint, request: CollectionPointDTO): Promise<Response<CollectionPoint>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<CollectionPoint>>
    +hardDelete(id: bigint): Promise<Response<void>>
}

class RouteController {
    +listAllActive(): Promise<Response<Route[]>>
    +listTrashed(): Promise<Response<Route[]>>
    +getById(id: bigint): Promise<Response<Route>>
    +create(request: RouteDTO): Promise<Response<Route>>
    +update(id: bigint, request: RouteDTO): Promise<Response<Route>>
    +softDelete(id: bigint): Promise<Response<void>>
    +restore(id: bigint): Promise<Response<Route>>
    +hardDelete(id: bigint): Promise<Response<void>>
}
