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




CLASS DIAGRAM UML CODE
@startuml
class Restaurant{
- int restaurantId;
- String name;
- double rating;
- String description;
- ActiveStatus status;

- List<Cuisine> cuisines;
- List<Contact> contacts;
- Address address;
- Menu menu;
- List<Review> reviews;
}

enum ActiveStatus{
CURRENTLY_SERVING,
CLOSED_FOR_DELIVERY, 
PERMANENTELY_CLOSED;
}

Restaurant *-- ActiveStatus

enum Cuisine{
Pizza,
Pasta,
Fast Food,
Shake,
Beverages
}

Restaurant *-- Cuisine

class Contact{
- String name;
- String phoneNumber;
}

Restaurant o-- Contact

class Address{
- String addressDesc;
- String city;
- String state;
}

Restaurant o-- Address

class Menu{
List<FoodItems> foodItems;

}

Restaurant o-- Menu


class FoodItems{
String restaurantId;
String itemId;
List<ItemTags> itemTags;

}



class Item{
long itemId;
String itemname;
String itemDesc;
double price;
double rating;

}

Enum ItemTags{
Chefs Special,
Spicy,
very spicy,
Veg,
Non veg
}

class Review{
String comment;
long upVote;
long downVote;
}

@enduml
