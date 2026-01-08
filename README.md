# Python-Mini-Project-Grocery-Store-Cart-System
This is my Second Mini project Grocery Store Cart System Which Helps to Reduces Work load 

cart = {}
prices = {"rice": 50, "milk": 30, "bread": 25, "sugar": 40}

while True:
    print("\n--- Grocery Store Menu ---")
    print("1. Add item")
    print("2. Remove item")
    print("3. View total price")
    print("4. Exit")

    choice = int(input("Enter your choice: "))

    if choice == 1:
        item = input("Enter item name: ").lower()
        if item in prices:
            qty = int(input("Enter quantity: "))
            cart[item] = cart.get(item, 0) + qty
            print(item, "added to cart")
        else:
            print("Item not available")

    elif choice == 2:
        item = input("Enter item to remove: ").lower()
        if item in cart:
            del cart[item]
            print(item, "removed from cart")
        else:
            print("Item not in cart")

    elif choice == 3:
        total = 0
        print("\nItems in cart:")
        for item, qty in cart.items():
            cost = prices[item] * qty
            total += cost
            print(item, "x", qty, "=", cost)
        print("Total Price =", total)

    elif choice == 4:
        print("Thank you for shopping!")
        break

    else:
        print("Invalid choice")

