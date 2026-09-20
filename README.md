START:
OUTPUT:  " WELCOME! "
OUTPUT: "SHAWARMARK FOOD STORE"
    
OUTPUT: "OUR FOOD MENU"
OUTPUT: "[SW] Shawarma Wrap:        - P80"
OUTPUT: "[SS] Shawarma Salad:       - P120"
OUTPUT:  "[SB] Shawarma Burger:      - P70"
OUTPUT:  "[ST] Shawarma Tacos:       - P85"
OUTPUT:  "[SF] Shawarma Fries:       - P85"

OUTPUT: "Enter your name"
INPUT: name

OUTPUT: "Enter food code"
INPUT: food
    

if food == SW:
    product = "Shawarma Wrap"
    price = 80
elif food == SS:
    product = "Shawarma Salad"
    price = 120
elif food == SB:
    product = "Shawarma Burger"
    price = 70
elif food == ST:
    product = "Shawarma Tacos"
    price = 85
elif food == SF:
    product = "Shawarma Fries"
    price = 85
else:
    Display "Invalid Code!"
End if

OUTPUT: "Enter Food Quantity"
INPUT: qty
  
if qty <= 0:
    Display "Invalid Food Quantity!"
End if

subtotal_food = price * qty

OUTPUT: "Add Drinks? (Y)Yes or (N)No"
INPUT: drinks
    
IF drinks == Y:
    Display "--------- OUR DRINKS ------------"
    Display "[C] COKE:            - P20"
    Display "[S] SPRITE:          - P20"
    Display "[R] ROYAL:           - P20"
    Display "[M] MOUNTAIN DEW:    - P25"
    Display  "[W] WATER BOTTLED:   - P15"
        
OUTPUT: "Choose your drinks code"
INPUT: choice

    if choice == C:
      drink_product = "Coke"
            drink_price = 20
    elif choice == S:
        drink_product = "Sprite"
        drink_price = 20
    elif choice == R:
        drink_product = "Royal"
        drink_price = 20
    elif choice == M:
        drink_product = "Mountain Dew"
        drink_price = 25
    elif choice == W:
        drink_product = "Water Bottled"
        drink_price = 15
    else:
        Display "Invalid Code!"
    End if

OUTPUT: "Enter Drinks Quantity"
INPUT: quantity

    if quantity <=0:
      Display "Invalid Drinks Quantity!"
    End if

elif drinks  == N:
    drink_product = "None"
    drink_price = 0
    drink_qty = 0
    display "No Drinks!"
else:
    Display "Invalid Input! Please Enter (Y) or (N)"
   End if

subtotal_drinks = drink_price * quantity

subtotal = subtotal_food + subtotal_drinks

if subtotal >= 1000:
   discount_rate = 0.12
elif subtotal >= 800:
   discount_rate = 0.05
else:
   discount_rate = 0
End if

 discount = subtotal * discount_rate
 discount_amount = subtotal - discount
 tax = discount_amount * 0.05
 final_total = discount_amount + tax

    
OUTPUT:  " RECEIPT"
OUTPUT:  "Customer Name" , name
OUTPUT:  "Product Food" , product
OUTPUT:  "Price P" , price
OUTPUT:  "Quantity" , qty
OUTPUT:  "Subtotal Food P" , subtotal_food
OUTPUT:  "Product Drink" , drink_product
OUTPUT:  "Drink Price P" , drink_price
OUTPUT:  "Drink Quantity" , quantity
OUTPUT:  "Subtotal Drinks: P" , subtotal_drinks
OUTPUT:  "Subtotal : P" , subtotal
OUTPUT:  "Discount: P" , discount
OUTPUT:  "Tax (5%): P" , tax    
OUTPUT:  "Total Payment  : P" , final_total
  
OUTPUT: "Enter payment: P"
INPUT: payment

if payment >= final_total:
   change = payment - final_total
   Display "Payment : P" , payment
   Display "Change  : P" ,  change
else:
   balance = final_total - payment
   Display "Insufficient payment!"
   Display "Balance : P" , balance
End if

 OUTPUT:  "THANK YOU!"
 OUTPUT:  "PLEASE COME AGAIN!"
 
END:
