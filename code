import os
import time
from colorama import Fore, Style, init

# Initialize colorama for colored text in terminal
init(autoreset=True)

mokedex = {}

def clear_screen():
    # Clears the terminal screen (cross-platform)
    os.system('cls' if os.name == 'nt' else 'clear')

def pretty_print():
    print(f"{Fore.CYAN}{'Name':^12}|{'Type':^10}|{'HP':^6}|{'MP':^6}{Style.RESET_ALL}")
    print(f"{'-'*12}|{'-'*10}|{'-'*6}|{'-'*6}")
    for key, value in mokedex.items():
        print(f"""{Fore.GREEN}{key:^12}{Style.RESET_ALL}|{value["type"]:^10}|{value["hp"]:^6}|{value["mp"]:^6}""")
    print()

def add_beast():
    # Add a new beast to the mokedex
    clear_screen()
    print(f"{Fore.YELLOW}--- Add Your Beast ---{Style.RESET_ALL}")

    name = input("Name > ").title()
    type = input("Type > ").title()

    while True:
        try:
            hp = int(input("HP > "))
            break
        except ValueError:
            print(f"{Fore.RED}Invalid HP. Please enter a number.{Style.RESET_ALL}")

    while True:
        try:
            mp = int(input("MP > "))
            break
        except ValueError:
            print(f"{Fore.RED}Invalid MP. Please enter a number.{Style.RESET_ALL}")

    # Add the beast to the dictionary
    mokedex[name] = {"type": type, "hp": hp, "mp": mp}

    print(f"{Fore.GREEN}Beast added successfully!{Style.RESET_ALL}")
    time.sleep(1)
    clear_screen()

def show_mokedex():
    clear_screen()
    print(f"{Fore.CYAN}--- Current Mokedex ---{Style.RESET_ALL}")
    if not mokedex:
        print(f"{Fore.RED}No beasts in the Mokedex yet!{Style.RESET_ALL}")
    else:
        pretty_print()
    input(f"{Fore.YELLOW}Press Enter to go back to the main menu...{Style.RESET_ALL}")
    clear_screen()

def main_menu():
    clear_screen()
    while True:
        print(f"{Fore.BLUE}--- Welcome to the Mokedex ---{Style.RESET_ALL}")
        print("1. Add a Beast")
        print("2. View Mokedex")
        print("3. Exit")

        choice = input(f"{Fore.YELLOW}Choose an option: {Style.RESET_ALL}")

        if choice == "1":
            add_beast()
        elif choice == "2":
            show_mokedex()
        elif choice == "3":
            print(f"{Fore.GREEN}Goodbye!{Style.RESET_ALL}")
            break
        else:
            print(f"{Fore.RED}Invalid choice. Please select 1, 2, or 3.{Style.RESET_ALL}")
            time.sleep(1)
            clear_screen()

# Run the main menu
main_menu()
