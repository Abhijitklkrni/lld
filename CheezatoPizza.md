Cheezato Online Delivery App
Requirements
1. Login as user
2. I should be able to order a product
3. Product can be of multiple types : Pizza, Sides, Desserts and Drinks
4. A product can have multiple ingredients
5. Pizza will have a name,veg,size,base type and toppings
6. Pizza can be classified into veg and non veg and can have tags such as new, most polular. Size and type
7. I should be able to add product to the cart
8. Check if the location is servicable
9. Calculate the order price
10. Apply Coupons
    
    
11. Payment gateway - third party integration 



Use Case diagram

@startuml
left to right direction

actor Admin
actor Customer


rectangle Cheezato_Pizza{

    usecase "Pay Online" as PayOnline
    usecase "Pay Cash" as PayCash
    usecase "Login" as Login    

    Admin --> (Add a product)
    Admin --> (Delete a product)
    Admin --> (Update order details)
    Admin --> Login
   
    Customer --> (Pay)
    Customer --> (Check Location Servicability)
    Customer --> (Request Order delivery)
    Customer --> Login

    PayOnline .> (Pay) : extends
    PayCash .> (Pay) : extends


   
}
@enduml

![3A9303B9-CA38-42FF-A714-FA2BEBE990DE](https://github.com/Abhijitklkrni/lld/assets/69401232/3bb1e278-ac22-495c-a2c4-26bc827204c0)
