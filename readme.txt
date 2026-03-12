import os

def create_document():
    file_name = "document.txt"
    text = input("Enter text for the document: ")

    with open(file_name, "w") as file:
        file.write(text)

    print("Document created successfully.")


def edit_document():
    file_name = "document.txt"

    if os.path.exists(file_name):
        text = input("Enter text to add: ")

        with open(file_name, "a") as file:
            file.write("\n" + text)

        print("Document edited successfully.")
    else:
        print("Document does not exist.")


def delete_document():
    file_name = "document.txt"

    if os.path.exists(file_name):
        os.remove(file_name)
        print("Document deleted successfully.")
    else:
        print("Document not found.")


while True:
    print("\nDocument Manager")
    print("1. Create Document")
    print("2. Edit Document")
    print("3. Delete Document")
    print("4. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        create_document()
    elif choice == "2":
        edit_document()
    elif choice == "3":
        delete_document()
    elif choice == "4":
        print("Exiting program...")
        break
    else:
        print("Invalid option.")
