# Function-planning-python-code
class PartyPlanner:
    def __init__(self):
        self.guest_list = []
        self.menu = {}
        self.budget = 0.0
        self.expenses = 0.0
    def add_guest(self, guest_name):
        self.guest_list.append(guest_name)
        print(f"Added {guest_name} to the guest list.")
    def remove_guest(self, guest_name):
        if guest_name in self.guest_list:
            self.guest_list.remove(guest_name)
            print(f"Removed {guest_name} from the guest list.")
        else:
            print(f"{guest_name} is not in the guest list.")
    def show_guest_list(self):
        print("Guest List:")
        for guest in self.guest_list:
            print(f"- {guest}")
    def add_menu_item(self, item_name, item_cost):
        self.menu[item_name] = item_cost
        print(f"Added {item_name} to the menu for ${item_cost:.2f}.")
    def remove_menu_item(self, item_name):
        if item_name in self.menu:
            del self.menu[item_name]
            print(f"Removed {item_name} from the menu.")
        else:
            print(f"{item_name} is not in the menu.")
    def show_menu(self):
        print("Menu:")
        for item, cost in self.menu.items():
            print(f"- {item}: ${cost:.2f}")
    def set_budget(self, budget_amount):
        self.budget = budget_amount
        print(f"Set the budget to ${budget_amount:.2f}")
    def calculate_expenses(self):
        self.expenses = sum(self.menu.values())
        print(f"Total expenses: ${self.expenses:.2f}")
    def check_budget(self):
        if self.expenses <= self.budget:
            print("You are within the budget.")
        else:
            print("You are over the budget.")
    def run(self):
        while True:
            print("\nParty Planner Menu:")
            print("1. Add Guest")
            print("2. Remove Guest")
            print("3. Show Guest List")
            print("4. Add Menu Item")
            print("5. Remove Menu Item")
            print("6. Show Menu")
            print("7. Set Budget")
            print("8. Calculate Expenses")
            print("9. Check Budget")
            print("10. Quit")
            choice = input("Enter your choice: ")
            if choice == '1':
                for i in range(0,5):
                    guest_name = input("Enter guest name: ")
                    self.add_guest(guest_name)
            elif choice == '2':
                guest_name = input("Enter guest name: ")
                self.remove_guest(guest_name)
            elif choice == '3':
                self.show_guest_list()
            elif choice == '4':
                for i in range(0,5):
                    item_name = input("Enter menu item name: ")
                    item_cost = float(input("Enter menu item cost: "))
                    self.add_menu_item(item_name, item_cost)
            elif choice == '5':
                item_name = input("Enter menu item name: ")
                self.remove_menu_item(item_name)
            elif choice == '6':
                self.show_menu()
            elif choice == '7':
                budget_amount = float(input("Enter budget amount: "))
                self.set_budget(budget_amount)
            elif choice == '8':
                self.calculate_expenses()
            elif choice == '9':
                self.check_budget()
            elif choice == '10':
                print("Exiting Party Planner.")
                break
            else:
                print("Invalid choice, please try again.")
if __name__ == "__main__":
    planner = PartyPlanner()
    planner.run()
