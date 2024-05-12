class Library:
    def __init__(self):
        self.books = {}

    def add_book(self, book_title):
        self.books[book_title] = True  # True indicates the book is available

    def borrow_book(self, book_title):
        if book_title in self.books and self.books[book_title]:
            self.books[book_title] = False
            print(f"You have borrowed '{book_title}'.")
        elif book_title in self.books and not self.books[book_title]:
            print(f"Sorry, '{book_title}' is already borrowed.")
        else:
            print(f"Sorry, '{book_title}' is not available in the library.")

    def return_book(self, book_title):
        if book_title in self.books and not self.books[book_title]:
            self.books[book_title] = True
            print(f"Thank you for returning '{book_title}'.")
        elif book_title in self.books and self.books[book_title]:
            print(f"'{book_title}' is already in the library.")
        else:
            print(f"'{book_title}' is not a valid book title.")

    def display_books(self):
        print("Books available in the library:")
        for book_title, available in self.books.items():
            status = "Available" if available else "Borrowed"
            print(f"{book_title}: {status}")


# Example usage
library = Library()
library.add_book("Harry Potter and the Philosopher's Stone")
library.add_book("To Kill a Mockingbird")
library.add_book("The Great Gatsby")

library.display_books()

library.borrow_book("To Kill a Mockingbird")
library.borrow_book("The Catcher in the Rye")

library.display_books()

library.return_book("To Kill a Mockingbird")

library.display_books()


<!---
Djheey/Djheey is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
