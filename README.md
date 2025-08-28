**🏨 Hotel Management System in C**

This project is a Hotel Management System built using the C programming language.
It allows managing hotel operations such as adding customers, displaying customer details, searching, checking out customers, and displaying all room information.

The project uses dynamic memory allocation (malloc, realloc, free) to manage rooms efficiently.

📌 Features

✅ Add a new customer with details (Name, Check-in, Check-out, Rent)

✅ Display customer information by room number

✅ Search customer (by room number)

✅ Check-out customer and free up room

✅ Display all occupied rooms

✅ Dynamic room allocation (automatic resizing of room capacity)

🛠️ Technologies Used

Language: C

Headers Used: stdio.h, stdlib.h, string.h

Concepts:

Structures in C (typedef struct)

Dynamic memory allocation (malloc, realloc, free)

Array handling

Menu-driven programming

🚀 How to Run

Clone or download this repository.

Open the project folder in your terminal.

Compile the program:

gcc hotel_management.c -o hotel_management


Run the executable:

./hotel_management

📂 Project Structure
hotel-management-system/
│── hotel_management.c    # Main source code
│── README.md             # Project documentation

📖 Sample Menu
Hotel Management System
1. Add Customer
2. Display Customer Info
3. Search Customer
4. Check Out Customer
5. Display All Rooms
6. Exit

📸 Example Output
Hotel Management System
1. Add Customer
2. Display Customer Info
3. Search Customer
4. Check Out Customer
5. Display All Rooms
6. Exit
Enter your choice: 1

Enter customer details:
Customer Name: John Doe
Check-in Date (YYYY-MM-DD): 2025-08-28
Check-out Date (YYYY-MM-DD): 2025-08-30
Room Rent: 5000
Customer added successfully!

📖 Future Improvements

🏷️ Add file handling to save customer data permanently.

💳 Add billing with taxes and discounts.

🌐 Develop a GUI version in C++/Java/Python.

👨‍💻 Author
Aditya Prakash
