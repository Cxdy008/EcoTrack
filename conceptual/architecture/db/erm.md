# ERM
****
employees(id, account_id, first_name, last_name, bi, city_id, address, created_at, updated_at, deleted_at)

employeesPhone(id, employee_id, phone_number, created_at, updated_at, deleted_at)

accounts(id, email, password, last_login, created_at, updated_at, deleted_at)

roles(id, name, description, created_at, updated_at, deleted_at)

accountsRoles(id, account_id, role_id, created_at, deleted_at)

truck_models(id, model_name, manufacturer, capacity, created_at, updated_at, deleted_at)

trucks(id, registration_number, truck_model_id, status, created_at, updated_at, deleted_at)

cities(id, name, description)

zones(id, name, city_id)

collection_points(id, address, id_zone, created_at, updated_at, deleted_at)

collections(id, datetime, truck_id, quantity,created_at, updated_at, deleted_at)

collection_employees(id, collection_id, employee_id, created_at, deleted_at)

collection_consumption(id, collection_id, quantity, created_at, updated_at, deleted_at)

collection_point_collections(id, collection_id, collection_point_id, quantity, created_at, updated_at, deleted_at)

routes(id, name, description, created_at, updated_at, deleted_at)

route_collection_points(id, route_id, collection_point_id, created_at, deleted_at)
