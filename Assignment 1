class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author
        self.available = True

    def display(self):
        if self.available:
            status = "Available"
        else:
            status = "Borrowed"

        print("Title :", self.title)
        print("Author :", self.author)
        print("Status :", status)
        print()


class Patron:
    def __init__(self, name):
        self.name = name
        self.borrowed_books = []

    def display(self):
        print("Patron Name :", self.name)

        if len(self.borrowed_books) == 0:
            print("No books borrowed")
        else:
            print("Borrowed Books :")
            for book in self.borrowed_books:
                print("-", book.title)
        print()


class Library:
    def __init__(self):
        self.books = []
        self.patrons = []

    def add_book(self):
        title = input("Enter Book Title : ")
        author = input("Enter Author Name : ")

        book = Book(title, author)
        self.books.append(book)

        print("Book added successfully.\n")

    def register_patron(self):
        name = input("Enter Patron Name : ")

        patron = Patron(name)
        self.patrons.append(patron)

        print("Patron registered successfully.\n")

    def borrow_book(self):
        patron_name = input("Enter Patron Name : ")
        book_title = input("Enter Book Title : ")

        for patron in self.patrons:
            if patron.name == patron_name:

                for book in self.books:
                    if book.title == book_title and book.available:
                        patron.borrowed_books.append(book)
                        book.available = False
                        print("Book borrowed successfully.\n")
                        return

        print("Book not available or Patron not found.\n")

    def return_book(self):
        patron_name = input("Enter Patron Name : ")
        book_title = input("Enter Book Title : ")

        for patron in self.patrons:
            if patron.name == patron_name:

                for book in patron.borrowed_books:
                    if book.title == book_title:
                        patron.borrowed_books.remove(book)
                        book.available = True
                        print("Book returned successfully.\n")
                        return

        print("Book not found.\n")

    def show_books(self):
        if len(self.books) == 0:
            print("No books available.\n")
        else:
            print("Books")
            for book in self.books:
                book.display()

    def show_patrons(self):
        if len(self.patrons) == 0:
            print("No patrons registered.\n")
        else:
            print("Patrons")
            for patron in self.patrons:
                patron.display()


library = Library()

while True:
    print("LIBRARY MANAGEMENT SYSTEM")
    print("1. Add Book")
    print("2. Register Patron")
    print("3. Borrow Book")
    print("4. Return Book")
    print("5. Show Books")
    print("6. Show Patrons")
    print("7. Exit")

    choice = int(input("Enter your choice : "))

    if choice == 1:
        library.add_book()

    elif choice == 2:
        library.register_patron()

    elif choice == 3:
        library.borrow_book()

    elif choice == 4:
        library.return_book()

    elif choice == 5:
        library.show_books()

    elif choice == 6:
        library.show_patrons()

    elif choice == 7:
        print("Thank You!")
        break

    else:
        print("Invalid Choice.")
