# kalkulatorzadanie
import logging
logging.basicConfig(level=logging.DEBUG)

print("Witaj")

def add(x, y):
    logging.debug(f"Dodaję {x} i {y}")
    return x + y


def substract(x, y):
    logging.debug(f"Odejmuję {x} i {y}")
    return x - y


def multiply(x, y):
    logging.debug(f"Mnożę {x} i {y}")
    return x * y


def divide(x, y):
    logging.debug(f"Dzielę {x} i {y}")
    return x / y

operations={
    "1":add,
    "2":substract,
    "3":multiply,
    "4":divide

}

print("Wybierz działanie:")
print("1.Dodawanie")
print("2.Odejmowanie")
print("3.Mnożenie")
print("4.Dzielenie")



while True:
  
    choice = input("Które działanie wybierasz? (1/2/3/4): ")


    if choice in ('1', '2', '3', '4'):
        num1 = float(input("Wpisz pierszą liczbę: "))
        num2 = float(input("Wpisz drugą liczbę: "))

        # if choice == '1':
        #     result= add(num1, num2)

        # elif choice == '2':
        #     logging.debug(num1, "-", num2, "=", subtract(num1, num2))

        # elif choice == '3':
        #     logging.debug(num1, "*", num2, "=", multiply(num1, num2))

        # elif choice == '4':
        #     logging.debug(num1, "/", num2, "=", divide(num1, num2))
        
        result=operations[choice](num1,num2)
        print(f"Wynik to:{result}")

        dalsze_obliczenia = input("Jeszcze raz? (TAK/NIE): ")
        if dalsze_obliczenia == "NIE":
          break
    
    else:
        print("Błąd")
