# Om
class library:

    lender_name = {"bio":"ram","merchant of venice":"omkar","chemistry":"krishna"}

    def __init__(self,books,liname):
        self.books = books
        self.liname = liname

    @property
    def Display_books(self):
        for index,item in enumerate(self.books):
            print(f"{index} - {item}")

    @Display_books.setter
    def Display_books(self,list):
        self.books.append(list)


    def lend_book(self):
        print("Enter your name - ", end=" ")
        lend_name = input()
        print("Enter the book name  - ", end=" ")
        lend_book = input()
        if lend_book in self.lender_name.keys():
            print( f"Book name {lend_book} is took by{self.lender_name[lend_book]}\nPlz check after sometime")
        else:
            self.lender_name.update({lend_book:lend_name})
            print("All set.............\n The book will reaching you on next day\nThank you for choosing our Library")

    def add_book(self):
        print("Enter the name of the book which you want to add in my Library ")
        book_name = input()
        self.Display_books = book_name
        print("The Book is Added")

    def return_book(self):
        print("Enter the name of the book which you want to return",end=" ")
        re_book = input()
        del self.lender_name[re_book]
        if re_book is not self.books:
            self.books.append(re_book)
        print("All set...............\nThank you for returning the book")

def main():
    obj1 = library(["merchant of venice","chemistry","Harry Potter series","the Tempest","Understanding Maths","bio"],"omkar")
    print(f"\t\t\t\t\t\t\t\t\tWelcome in {obj1.liname} Library\n")
    print("\tpress 1  - For Display Books Name\n\tpress 2 - For Lend Book\n\tpress 3 - For Add Book\n\tpress 4 - For Return Book")
    user_choise = input()
    if user_choise == "1":
        obj1.Display_books

    elif user_choise == "2":
        obj1.lend_book()

    elif user_choise == "3":
        obj1.add_book()

    elif user_choise == "4":
        obj1.return_book()

    else:
        print("Enter a valid choise")
main()
while True:
    print("If you want to quit then type (yes) or you want to take another book then type (No) ")
    user = input()
    user = user.capitalize()
    if user == "No":
        main()
    else:
        print("Thank You So Much...........")
        break
