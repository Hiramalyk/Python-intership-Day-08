# Python-intership-Day-08
def contact_book():
    book = {}
    while True:
        c = input("\n1.Add 2.Update 3.View 4.All 5.Exit: ")
        if c == "1":
            n = input("Name: ").title()
            if n in book: print("Exists"); continue
            p, e = input("Phone: "), input("Email: ")
            if "@" in e and "." in e: book[n] = {"phone": p, "email": e}
            else: print("Invalid email")
        elif c == "2":
            n = input("Name: ").title()
            if n in book:
                p, e = input("New phone: "), input("New email: ")
                if "@" in e and "." in e: book[n] = {"phone": p, "email": e}
                else: print("Invalid email")
            else: print("Not found")
        elif c == "3":
            n = input("Name: ").title()
            print(book.get(n, "Not found"))
        elif c == "4":
            [print(k, v) for k, v in book.items()]
        elif c == "5":
            break

contact_book()
