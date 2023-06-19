#!/bin/python3

def calculate_investment(target_amount, years, growth_rate):
    investment = target_amount / (1 + growth_rate) ** years
    return investment

# Get user input for investment end goal, years, and return rate
target_amount = float(input("Enter your investment end goal: $"))
years = int(input("Enter the number of years you plan to invest: "))
growth_rate = float(input("Enter your expected annual return rate (in decimal format): "))

# Calculate the investment amount per year
investment_needed = calculate_investment(target_amount, years, growth_rate)
investment_per_year = investment_needed / years

print(f"To achieve your investment goal of ${target_amount:.2f} in {years} years, you would need to invest ${investment_per_year:.2f} per year.")
