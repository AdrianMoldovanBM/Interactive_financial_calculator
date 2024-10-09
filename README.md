# Calculator for ROI (Return on Investment), Win Rate, and Risk Ratio

Coding in Python and using Google Colab, I developed an interactive financial calculator for businesses and people alike, that helps users calculate three key financial metrics: **ROI (Return on Investment)**, **win rate**, and **risk ratio**. 

The program asks the user to choose one of these three options and then guides them through inputting the necessary values to perform the selected calculation.

# Code
    def calculate():
    # Prompting the user to choose what types of calculation he wants and converting all inputs into lower strings
    user_input = input("What do you want to calculate: ROI, win rate, risk ratio").lower()
    
    # Implementing the first if condition, depending on the user's choice
    if user_input == "roi":
        prof_val = float(input("Enter profit value: "))
        cost = float(input("Enter investment cost: "))
        val_ROI = float(prof_val - cost) / cost * 100

        # Rounding the results with only two decimal places for ease of readability
        round_ROI = round(val_ROI,2)
        print("You have a ROI of {}%".format(round_ROI))

    # Implementing the second if statement, using elif function
    elif user_input == "win rate":
        win = float(input("Enter profit value: "))
        cost = float(input("Enter investment cost: "))
        win_rate = win/cost
        
        # Rounding the results and displaying in a format indicating a ratio (either win:1 or 1:win, depending on whether the win is smaller or larger than the cost)
        round_win = round(win_rate,2)
        if win < cost:
            print("Your win rate is {}:1".format(round_win))
        else:
            print("Your win rate is 1:{}".format(round_win))

    # Implementing the third if statement, using elif function
    elif user_input == "risk ratio":
        win = float(input("Enter profit value: "))
        risk = float(input("Enter investment cost: "))
        risk_ratio = risk/win

        # Rounding the result and presenting it as a percentage
        round_risk = round(risk_ratio,2)
        print("Your risk ratio is {}%".format(round_risk))
    
    # Dealing with invalid inputs
    elif user_input != "roi""win rate""risk ratio":
        return "Please enter a valid choice"

# Implementation:
    calculate()
