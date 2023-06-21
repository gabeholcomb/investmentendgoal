def calculate_investment(target_amount, years, growth_rate):
    total_investment = target_amount / (1 + growth_rate) ** years
    investment_per_year = []
    investment = total_investment
    for year in range(years, 0, -1):
        investment_per_year.append(investment)
        investment -= investment / (1 + growth_rate)
    return investment_per_year[::-1]

# Get user input for investment end goal, years, and return rate
target_amount = float(input("Enter your investment end goal: $"))
years = int(input("Enter the number of years you plan to invest: "))
growth_rate = float(input("Enter your expected annual return rate (in decimal format): "))

# Calculate the decreasing investment amount per year
investment_per_year = calculate_investment(target_amount, years, growth_rate)

# Display the decreasing investment amount per year
for year, investment in enumerate(investment_per_year, start=1):
    print(f"Invest ${investment:.2f} in Year {year}")
