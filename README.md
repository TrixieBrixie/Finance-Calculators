# Finance-Calculators
# This is a program example that allows the user to access two different financial calculators: # An investment calculator # A home loan repayment calculator

import math 

# Print a menu for the user to choose which financial calculator they want to do

print("Menu:")
print("")
print("Investment - it calculates the amount of interest you'll earn on your investment")
print("Bond - it calculates the amount you'll have to pay on a home loan")
print("")

choice = input("Enter either 'investment' or 'bond' based on the above menu: \n").lower()

if choice == "investment":
    P = float(input("Enter the amount of money you're depositing: \n"))
    r = float(input("Enter the interest rate (as a percentage): \n")) / 100
    t = float(input("Enter the number of years you're planning to invest: \n"))

# Ask the user if they want compound ot simple interest
interest = input("Would you like a compound or simple interest: \n").lower()

simple = round(P * (1 + r*t))
compound = round(P * math.pow((1+r), t))

if interest == "simple":
    print("The total amount of your interest is: \n", simple)

if interest == "compound":
    print("The total amount of your interest is: \n", compound)

elif choice == "bond":
    V = float(input("Enter the present value of the house: \n"))
    i = float(input("Enter the interest rate (as a percentage): \n")) / 100
    n = float(input("Enter the number of months you plan to take to repay the bond: \n"))

    repayment = round(i * V) / (1- (1 + i)**(-n))

    print("The momthly amount to be paid is: \n", repayment)

else:
    print("Invalid input")
