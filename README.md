# Digi — Python Store

SACE Stage 1 Digital Technologies · Task 3

## Contents

- [Part 1 — Store Planning](#part-1--store-planning)
- [Part 2 — Store Coding](#part-2--store-coding)
- [Part 3 — Store Reflection](#part-3--store-reflection)
- [Original task](originals/Store%20Task.docx)

## Part 1 — Store Planning

Status: pseudocode completed. The text below preserves the current student version.

```text
BEGIN

INITIALISE products with 15 specified items and prices
SET cart TO empty list
SET reward_points TO 0
SET discount_rate TO 0.40
SET gst_rate TO 0.11
SET max_items TO 3

REPEAT

    DISPLAY "Welcome to the Game Store!"
    DISPLAY "1. View Products"
    DISPLAY "2. Add Product to Cart"
    DISPLAY "3. View / Edit Cart"
    DISPLAY "4. Checkout"
    DISPLAY "5. View Reward Points"
    DISPLAY "6. Exit"

    INPUT user_choice

    IF user_choice IS 1 THEN

        FOR each product in products
            DISPLAY product ID, name and price
        END FOR

    ELSE IF user_choice IS 2 THEN

        IF number of items in cart BIGER OR EQUAL max_items THEN
            DISPLAY "Cart is full"
        ELSE
            DISPLAY available products
            INPUT product_ID

            IF product_ID is valid THEN
                ADD selected product to cart
                DISPLAY "Product added"
            ELSE
                DISPLAY "Invalid product"
            END IF
        END IF

    ELSE IF user_choice IS 3 THEN

        IF cart is empty THEN
            DISPLAY "Cart is empty"
        ELSE
            DISPLAY all items in cart
            CALCULATE and DISPLAY cart subtotal

            ASK whether customer wants to remove an item
            INPUT remove_choice

            IF remove_choice IS "Yes" THEN
                INPUT item_number

                IF item_number is valid THEN
                    REMOVE selected item from cart
                    DISPLAY "Item removed"
                ELSE
                    DISPLAY "Invalid item number"
                END IF
            END IF
        END IF

    ELSE IF user_choice IS 4 THEN

        IF cart is empty THEN
            DISPLAY "Cannot checkout an empty cart"
        ELSE
            CALCULATE subtotal from cart

            SET discount TO subtotal * discount_rate
            SET discounted_total TO subtotal - discount
            SET gst TO discounted_total * gst_rate
            SET final_total TO discounted_total + gst

            ROUND monetary values to 2 decimal places

            DISPLAY subtotal, discount, gst, final_total

            REPEAT
                INPUT cash_paid

                IF cash_paid is not a valid non-negative number THEN
                    DISPLAY "Invalid payment"
                ELSE IF cash_paid SMALLER final_total THEN
                    DISPLAY "Insufficient payment"
                END IF

            UNTIL cash_paid is valid AND cash_paid BIGER OR EQUAL final_total

            SET change TO cash_paid - final_total
            SET earned_points TO INTEGER PART OF (final_total / 10)
            SET reward_points TO reward_points + earned_points

            DISPLAY "Payment successful"
            DISPLAY final_total
            DISPLAY cash_paid
            DISPLAY change
            DISPLAY earned_points

            CLEAR cart
        END IF

    ELSE IF user_choice IS 5 THEN

        DISPLAY "Your reward points: ", reward_points

    ELSE IF user_choice IS 6 THEN

        DISPLAY "Thank you for shopping!"

    ELSE

        DISPLAY "Invalid menu selection"

    END IF

UNTIL user_choice IS 6

END
```

## Part 2 — Store Coding

Status: not yet implemented.

The Python program will follow Part 1: 15 specified products, a maximum of 3 items per purchase, a 40% discount, 11% GST applied after the discount, cash payment and change, reward points, a six-option menu, and input validation.

At least three genuine screenshots of different code development stages will be added to `screenshots/` as development progresses. Code comments will explain the implementation and design decisions.

## Part 3 — Store Reflection

Status: awaiting development and real peer feedback.

This section will document:

1. Actual peer feedback and how it improved the program.
2. Whether and how using that feedback was appropriate, with the changed program.
3. How a store should manage and protect sensitive customer and payment data.

No peer feedback has been collected or invented for this document.
