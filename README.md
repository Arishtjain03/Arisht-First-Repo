inventory={}
while True:
    def menu():
        print("Inventory")
        print("1:add item")
        print("2:update item price or quantity")
        print("3:remove item")
        print("4:view inventory")
        print("5:search products")
        print("6 : calculate the total value")
        print("7 : exit")

    menu()
    
    num=int(input("Enter the corrosponding number of the function you have to apply : "))

    def add_items(name,price,quantity):
        global item
        item={name:(quantity,price)}
        inventory.update(item)


    if num==1:

        item_name=input("enter the name of item : ")

        item_quantity=float(input("enter the quantity of item : "))

        item_price=float(input("Enter the price of the item : "))

        add_items(item_name,item_price,item_quantity)

        print(f"your item added successfully")

    elif num==2:
        item_name=input(f"this is your{list(inventory.keys())} inventory products , enter the name of the product which you have to update : ")
        if item_name in inventory:

            user_choice=input("What do you want to change 'price' or 'quantity' : ").strip().lower()
            if user_choice=="price"or "quantity" or "qty" : 

                str(item_name)
                values=list(inventory.get(item_name))
                if user_choice=="price":
                    user_input_price=input(f"This {values[1]}  is your selected item's existing price,enter the price which wich you want to update :  ")
                    qty,price=inventory.get(item_name)
                    inventory[item_name]=(qty,user_input_price)
                    print("Price updated successfully")

                if user_choice=="quantity" :
                    user_input_quantity=input(f"This {values[0]}  is your selected item's existing quantity,enter the quantity which wich you want to update :  ")
                    qty,price=inventory.get(item_name)
                    inventory[item_name]=(user_input_quantity,price)
                    print("Quantity updated successfully")

                else:
                    print("invalid input")

            else:
                print("invalid input")

        else:
            print("Invalid name of item")


    elif num==3:
        item_name=input(f"this is your{list(inventory.keys())} inventory products , enter the name of the product which you have to remove : ")
        
        if item_name in inventory: 
            str(item_name)
            inventory.pop(item_name)
            print(f"this item {item_name} removed successfully")

        else:
            print("invalid input")
        


    elif num==4:
        print(f"this is your {inventory} inventory")


    elif num==5:
        user_input_search=input(f"Enter the name of item which you want to search from this {list(inventory.keys())} inventory : ")
        list_of_inventory=list(inventory.keys())
        str(user_input_search)
        if user_input_search in list_of_inventory:

            print(user_input_search, "→" ,inventory[user_input_search])
            
        else:
            print("this item is not added in inventory")

    elif num==6:
        list_inventory_values=list(inventory.values())
        for key, (qty,price) in inventory.items():
            total=qty * price

            print(f"{key} → {total}")

    elif num==7:
        print("You exiten the program")
        break
    

    



