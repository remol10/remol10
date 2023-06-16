import matplotlib.pyplot as plt

def calculate_production_cost(number_of_units):
    production_cost_per_unit = 80000
    fixed_cost = 10000000
    total_cost = fixed_cost + (production_cost_per_unit * number_of_units)
    return total_cost

def calculate_revenue(number_of_units):
    unit_price = 100000
    revenue = unit_price * number_of_units
    return revenue

def calculate_profit(number_of_units):
    total_cost = calculate_production_cost(number_of_units)
    profit = 0.2 * total_cost
    return profit

def calculate_total_cost_and_profit(number_of_units):
    total_cost = calculate_production_cost(number_of_units)
    profit = calculate_profit(number_of_units)
    total_cost_and_profit = total_cost + profit
    return total_cost_and_profit

# Menghitung jumlah tas yang dijual dari 0 hingga 200
number_of_units = list(range(201))
total_cost_and_profit = [calculate_total_cost_and_profit(units) for units in number_of_units]
revenue = [calculate_revenue(units) for units in number_of_units]

# Membuat grafik
plt.plot(number_of_units, total_cost_and_profit, label='Total Cost + Profit')
plt.plot(number_of_units, revenue, label='Revenue')
plt.xlabel('Jumlah Tas Terjual')
plt.ylabel('Jumlah (dalam Rupiah)')
plt.title('Analisis Production Cost and Revenue')
plt.legend()
plt.show()
