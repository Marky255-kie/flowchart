START
    PRINT "================================================"
    PRINT "==================== WELCOME! =================="
    PRINT "============ SHAWARMARK FOOD STORE ============="
    PRINT "================================================"

    PRINT "------------OUR FOOD MENU---------------"
    PRINT "[SW] Shawarma Wrap:        - P80"
    PRINT "[SS] Shawarma Salad:       - P120"
    PRINT "[SB] Shawarma Burger:      - P70"
    PRINT "[ST] Shawarma Tacos:       - P85"
    PRINT "[SF] Shawarma Fries:       - P85"

    INPUT name

    INPUT food_code
    CONVERT food_code to UPPERCASE

    IF food_code = "SW" THEN
        product = "Shawarma Wrap"
        price = 80
    ELSE IF food_code = "SS" THEN
        product = "Shawarma Salad"
        price = 120
    ELSE IF food_code = "SB" THEN
        product = "Shawarma Burger"
        price = 70
    ELSE IF food_code = "ST" THEN
        product = "Shawarma Tacos"
        price = 85
    ELSE IF food_code = "SF" THEN
        product = "Shawarma Fries"
        price = 85
    ELSE
        PRINT "Invalid Code!"
        END PROGRAM
    END IF

    INPUT qty
    IF qty <= 0 THEN
        PRINT "Invalid Food Quantity!"
        END PROGRAM
    END IF

    subtotal_food = price * qty

    INPUT add_drinks
    CONVERT add_drinks to UPPERCASE

    IF add_drinks = "Y" THEN
        PRINT "--------- OUR DRINKS ------------"
        PRINT "[C] COKE:            - P20"
        PRINT "[S] SPRITE:          - P20"
        PRINT "[R] ROYAL:           - P20"
        PRINT "[M] MOUNTAIN DEW:    - P25"
        PRINT "[W] WATER BOTTLED:   - P15"

        INPUT drink_code

        IF drink_code = "C" THEN
            drink_product = "Coke"
            drink_price = 20
        ELSE IF drink_code = "S" THEN
            drink_product = "Sprite"
            drink_price = 20
        ELSE IF drink_code = "R" THEN
            drink_product = "Royal"
            drink_price = 20
        ELSE IF drink_code = "M" THEN
            drink_product = "Mountain Dew"
            drink_price = 25
        ELSE IF drink_code = "W" THEN
            drink_product = "Water Bottled"
            drink_price = 15
        ELSE
            PRINT "Invalid Code!"
            END PROGRAM
        END IF

        INPUT drink_qty
        IF drink_qty <= 0 THEN
            PRINT "Invalid Drinks Quantity!"
            END PROGRAM
        END IF

    ELSE IF add_drinks = "N" THEN
        drink_product = "None"
        drink_price = 0
        drink_qty = 0
        PRINT "No Drinks!"
    ELSE
        PRINT "Invalid Input! Please Enter (Y) or (N)"
        END PROGRAM
    END IF

    subtotal_drinks = drink_price * drink_qty
    subtotal = subtotal_food + subtotal_drinks

    IF subtotal >= 1000 THEN
        discount_rate = 0.12
    ELSE IF subtotal >= 800 THEN
        discount_rate = 0.05
    ELSE
        discount_rate = 0
    END IF

    discount = subtotal * discount_rate
    after_discount = subtotal - discount
    tax = after_discount * 0.05
    final_total = after_discount + tax

    PRINT "================================================"
    PRINT "==================== RECEIPT ===================="
    PRINT "================================================"
    PRINT "Customer Name  : " + name
    PRINT "Product Food   : " + product
    PRINT "Price          : P" + price
    PRINT "Quantity       : " + qty
    PRINT "Subtotal Food  : P" + subtotal_food
    PRINT "================================================"
    PRINT "Product Drink  : " + drink_product
    PRINT "Drink Price    : P" + drink_price
    PRINT "Drink Quantity : " + drink_qty
    PRINT "Subtotal Drinks: P" + subtotal_drinks
    PRINT "================================================"
    PRINT "Subtotal       : P" + subtotal
    PRINT "Discount       : P" + discount
    PRINT "Tax (5%)       : P" + tax
    PRINT "================================================"
    PRINT "Total Payment  : P" + final_total
    PRINT "================================================"

    INPUT payment

    IF payment >= final_total THEN
        change = payment - final_total
        PRINT "Payment : P" + payment
        PRINT "Change  : P" + change
    ELSE
        balance = final_total - payment
        PRINT "Insufficient payment!"
        PRINT "Balance : P" + balance
    END IF

    PRINT "================================================"
    PRINT "================= THANK YOU! ===================="
    PRINT "============== PLEASE COME AGAIN! ==============="
    PRINT "================================================"
END

