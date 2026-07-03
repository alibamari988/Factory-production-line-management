@startuml

class Product{
-id:int
-name:String
-price:double
}

class RawMaterial{
-id:int
-name:String
-stock:int
}

class Supplier{
-id:int
-name:String
-phone:String
}

class Warehouse{
-id:int
-name:String
-location:String
}

class Inventory{
-quantity:int
+add()
+remove()
}

class ProductionLine{
-id:int
-name:String
-status:String
}

class ProductionOrder{
-id:int
-date:Date
}

class Sales{
-id:int
-date:Date
-total:double
}

class Customer{
-id:int
-name:String
}

class PurchaseOrder{
-id:int
-date:Date
}

Product "1" -- "*" RawMaterial : نیاز دارد
Supplier "1" -- "*" PurchaseOrder
PurchaseOrder "*" -- "*" RawMaterial
Warehouse "1" -- "*" Inventory
Inventory "*" -- "1" Product
Inventory "*" -- "1" RawMaterial
ProductionLine "1" -- "*" ProductionOrder
ProductionOrder "*" -- "1" Product
Customer "1" -- "*" Sales
Sales "*" -- "*" Product

@enduml
