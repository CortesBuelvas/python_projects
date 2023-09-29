class CoffeeMachine:
    SELECTION = input("Write action (buy, fill, take, remaining, exit):\n")

    def __init__(self):
        self.option = self.SELECTION
        # Initialize machine state
        self.machine_state = 'Initializing'
        # Items that the machine has
        self.items = ["ml of water", "ml of milk", "g of coffee beans", "disposable cups"]
        # Initialize machine resources
        self.machine_status = [400, 540, 120, 9, 550]  # water(ml), milk(ml), beans(g), cups (units), money($)
        # Initialize the coffee types' needs
        self.coffee_needs = {
            "espresso": [250, 0, 16, 1, 4],  # water(ml), milk(ml), beans(g), cups (units), money($)
            "latte": [350, 75, 20, 1, 7],  # water(ml), milk(ml), beans(g), cups (units), money($)
            "capuccino": [200, 100, 12, 1, 6]  # water(ml), milk(ml), beans(g), cups (units), money($)
        }

    def status_declaration(self):
        print("The coffee machine has:")
        for i in range(4):
            print(self.machine_status[i], self.items[i])
        print("$" + str(self.machine_status[4]),
              "of money")  # Ensures that the "$" is printed at the start of the money state

    def fill_machine(self):
        for i in range(4):
            print("Write how many", self.items[i], "you want to add:")
            self.machine_status[i] += int(input())
        return self.machine_status

    def espresso(self):
        if self.machine_status[0] < self.coffee_needs["espresso"][0]:
            print("Sorry, not enough water!")
        elif self.machine_status[2] < self.coffee_needs["espresso"][2]:
            print("Sorry, not enough coffee beans")
        else:
            print("I have enough resources, making you a coffee!")
            for i in range(4):
                self.machine_status[i] -= self.coffee_needs["espresso"][i]
            self.machine_status[4] += self.coffee_needs["espresso"][4]
        return self.machine_status

    def latte(self):
        if self.machine_status[0] < self.coffee_needs["latte"][0]:
            print("Sorry, not enough water!")
        elif self.machine_status[1] < self.coffee_needs["latte"][1]:
            print("Sorry, not enough milk!")
        elif self.machine_status[2] < self.coffee_needs["latte"][2]:
            print("Sorry, not enough coffee beans!")
        else:
            print("I have enough resources, making you a coffee!")
            for i in range(4):
                self.machine_status[i] -= self.coffee_needs["latte"][i]
            self.machine_status[4] += self.coffee_needs["latte"][4]
        return self.machine_status

    def capuccino(self):
        if self.machine_status[0] < self.coffee_needs["capuccino"][0]:
            print("Sorry, not enough water!")
        elif self.machine_status[1] < self.coffee_needs["capuccino"][1]:
            print("Sorry, not enough milk!")
        elif self.machine_status[2] < self.coffee_needs["capuccino"][2]:
            print("Sorry, not enough coffee beans!")
        else:
            print("I have enough resources, making you a coffee!")
            for i in range(4):
                self.machine_status[i] -= self.coffee_needs["capuccino"][i]
            self.machine_status[4] += self.coffee_needs["capuccino"][4]
        return self.machine_status

    def buy_coffee(self):
        print("What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino:")
        coffee_option = input()
        if coffee_option == "1":
            self.espresso()
        elif coffee_option == "2":
            self.latte()
        elif coffee_option == "3":
            self.capuccino()
        elif coffee_option == "back":
            pass

    def take_money(self):
        print("I gave you $" + str(self.machine_status[4]))
        self.machine_status[4] = 0  # machine_state[4] refers to money

    def action(self):
        state = self.option
        coffee_machine = CoffeeMachine()
        while state != 'exit':
            if state == 'take':
                self.machine_state = 'taking money out'
                coffee_machine.take_money()
            elif state == 'remaining':
                self.machine_state = 'checking machine resources'
                coffee_machine.status_declaration()
            elif state == 'fill':
                self.machine_state = 'filling resources'
                coffee_machine.fill_machine()
            elif state == 'buy':
                self.machine_state = 'buying a coffee'
                coffee_machine.buy_coffee()
            else:
                print('Enter a valid action (buy, fill, take, remaining, exit)')

            state = input("Write action (buy, fill, take, remaining, exit):\n")

        return self.machine_status


CoffeeMachine().action()
