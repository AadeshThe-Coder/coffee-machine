# ☕ Coffee Machine

A command-line coffee machine simulator written in Python. Pick a drink, insert coins, and the machine checks its ingredients, takes your payment, gives change, and makes your coffee.

## Features

- Three drinks: espresso, latte and cappuccino
- Tracks remaining water, milk and coffee
- Refuses an order if there aren't enough ingredients
- Accepts payment in quarters, dimes, nickels and pennies
- Returns change, or refunds the money if the payment is too low
- Keeps a running total of money earned
- Built-in `report` and `off` commands

## Menu

| Drink      | Water | Milk  | Coffee | Price |
|------------|-------|-------|--------|-------|
| Espresso   | 50 ml | -     | 18 g   | $1.50 |
| Latte      | 200 ml| 150 ml| 24 g   | $2.50 |
| Cappuccino | 250 ml| 100 ml| 24 g   | $3.00 |

The machine starts with **300 ml water, 200 ml milk and 100 g coffee**.

## Getting Started

### Requirements

- Python 3.6 or newer (uses f-strings). No external libraries needed.

### Run it

```bash
git clone <your-repo-url>
cd <your-repo-folder>
python3 main.py
```

## Usage

At the prompt, type one of the following:

| Command      | What it does                                         |
|--------------|------------------------------------------------------|
| `espresso`   | Order an espresso                                    |
| `latte`      | Order a latte                                        |
| `cappuccino` | Order a cappuccino                                   |
| `report`     | Show remaining resources and money earned            |
| `off`        | Turn the machine off and exit the program            |

### Example session

```
What would you like? (espresso/latte/cappuccino): latte
Please insert coins.
how many quarters?: 10
how many dimes?: 0
how many nickles?: 0
how many pennies?: 0
Here is $0.0 in change.
Here is your latte ☕️. Enjoy!
What would you like? (espresso/latte/cappuccino): report
Water: 100ml
Milk: 50ml
Coffee: 76g
Money: $2.5
What would you like? (espresso/latte/cappuccino): off
```

## How It Works

1. The user chooses a drink.
2. `is_resource_sufficient()` checks that the machine has enough water, milk and coffee.
3. `process_coins()` asks how many of each coin were inserted and returns the total.
4. `is_transaction_successful()` compares the payment to the drink's cost, gives change and adds to the profit, or refunds the money.
5. `make_coffee()` deducts the ingredients and serves the drink.

## Project Structure

```
.
├── main.py          # Program logic and the main loop
├── ingredients.py   # Menu and starting resource data
└── README.md
```

## Possible Improvements

- Handle invalid drink names without crashing
- Import `MENU` and `resources` from `ingredients.py` instead of defining them in `main.py`
- Add a refill option for the ingredients
- Format money to two decimal places in the report
- Add more drinks to the menu

## License

This project is open source. Add a license of your choice here (for example MIT).
