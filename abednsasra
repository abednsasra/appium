# File: currency_converter.py

class USD:
    def get_value(self):
        """Returns the conversion rate for USD to ILS."""
        return 3.52

    def calculate(self, amount):
        """Converts the given amount from USD to ILS."""
        return amount * self.get_value()


class ILS:
    def get_value(self):
        """Returns the conversion rate for ILS to USD."""
        return 0.28

    def calculate(self, amount):
        """Converts the given amount from ILS to USD."""
        return amount * self.get_value()


class CurrencyConverter:
    def __init__(self):
        self.usd = USD()
        self.ils = ILS()

    def convert_currency(self, amount, from_currency, to_currency):
        """
        Converts the given amount from the specified currency to the target currency.

        Parameters:
            amount (float): The amount to be converted.
            from_currency (str): The currency to convert from ('USD' or 'ILS').
            to_currency (str): The currency to convert to ('USD' or 'ILS').

        Returns:
            float: The converted amount.
        """
        try:
            if from_currency == 'USD' and to_currency == 'ILS':
                return self.usd.calculate(amount)
            elif from_currency == 'ILS' and to_currency == 'USD':
                return self.ils.calculate(amount)
            else:
                raise ValueError("Invalid currency conversion. Please try again.")
        except ValueError as e:
            print(e)
            return None


def main():
    results = []
    converter = CurrencyConverter()

    while True:
        print("Welcome to currency converter")
        print("Please choose an option (1/2):")
        print("1. Dollars to Shekels")
        print("2. Shekels to Dollars")

        user_choice = input("Enter your choice (1 or 2): ")

        if user_choice not in ['1', '2']:
            print("Invalid Choice, please try again")
            continue

        amount = float(input("Please enter an amount to convert: "))

        if user_choice == '1':
            converted_amount = converter.convert_currency(amount, 'USD', 'ILS')
            print(f"{amount:.2f} USD is equal to {converted_amount:.2f} ILS\n")
            results.append(f"{amount:.2f} USD is equal to {converted_amount:.2f} ILS")
        elif user_choice == '2':
            converted_amount = converter.convert_currency(amount, 'ILS', 'USD')
            print(f"{amount:.2f} ILS is equal to {converted_amount:.2f} USD\n")
            results.append(f"{amount:.2f} ILS is equal to {converted_amount:.2f} USD")

        choice = input("Do you want to start over? (Y/N): ").upper()
        if choice != "Y":
            break

    print("Thanks for using our currency converter.")
    print("Previous results:")
    for result in results:
        print(result)

    with open("results.txt", "w") as file:
        for result in results:
            file.write(result + "\n")

if __name__ == "__main__":
    main()
