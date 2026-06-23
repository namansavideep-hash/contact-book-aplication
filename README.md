# contact-book-aplication

def display_menu():
    print("Contact Book Menu:")
    print("1. Add Contact")
    print("2. View Contact")
    print("3. Edit Contact")
    print("4. Delete Contact")
    print("5. List All Contacts")
    print("6. Exit")


def add_contact(contact_book):
    name = input()
    if name in contact_book:
        print("Contact already exists!")
        return
    phone = input()
    email = input()
    address = input()
    contact_book[name] = {"phone": phone, "email": email, "address": address}
    print("Contact added successfully!")

def view_contact(contact_book):
    name = input()

    if name in contact_book:
        print(f"Name: {name}")
        print(f"Phone: {contact_book[name]['phone']}")
        print(f"Email: {contact_book[name]['email']}")
        print(f"Address: {contact_book[name]['address']}")
    else:
        print("Contact not found!")

def edit_contact(contact_book):
    name = input()

    if name in contact_book:
        phone = input()
        email = input()
        address = input()

        if phone != '':
            contact_book[name]['phone'] = phone
        if email != '':
            contact_book[name]['email'] = email
        if address != '':
            contact_book[name]['address'] = address

        print("Contact updated successfully!")
    else:
        print("Contact not found!")

def delete_contact(contact_book):
    Delete_name = input()
    if Delete_name in contact_book:
        
        print("Contact deleted successfully!")
    else:
        print("Contact not found!")

def list_all_contacts(contact_book):
    if not contact_book:
        print("No contacts available.")
    else:
        for name, details in contact_book.items():
            print(f"Name: {name}")
            print(f"Phone: {details['phone']}")
            print(f"Email: {details['email']}")
            print(f"Address: {details['address']}")
            print()

contact_book = {}

while True:
    display_menu()
    choice = input("Enter your choice: ")

    if choice == '1':
        add_contact(contact_book)
    elif choice == '2':
        view_contact(contact_book)
    elif choice == '3':
        edit_contact(contact_book)
    elif choice == '4':
        delete_contact(contact_book)
    elif choice == '5':
        list_all_contacts(contact_book)
    elif choice == '6':
        print("Exiting Contact Book. Goodbye!")
        break
    else:
        print("Invalid choice. Please try again. ")
