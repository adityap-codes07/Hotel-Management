#include <stdio.h>
#include <stdlib.h>
#include <string.h>


typedef struct {
    int room_no;
    char *customer_name;
    char *check_in_date;
    char *check_out_date;
    float room_rent;
} Room; 

Room* rooms; 
int num_rooms = 0;
int max_rooms = 0; 

void add_customer();
void display_customer_info();
void search_customer();
void check_out_customer();
void display_all_rooms();
void increase_room_capacity();

int main() {
    int choice;

   
    max_rooms = 10;
    rooms = (Room*)malloc(max_rooms * sizeof(Room));
    if (rooms == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    do {
        printf("\nHotel Management System\n");
        printf("1. Add Customer\n");
        printf("2. Display Customer Info\n");
        printf("3. Search Customer\n");
        printf("4. Check Out Customer\n");
        printf("5. Display All Rooms\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                add_customer();
                break;
            case 2:
                display_customer_info();
                break;
            case 3:
                search_customer();
                break;
            case 4:
                check_out_customer();
                break;
            case 5:
                display_all_rooms();
                break;
            case 6:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice!\n");
        }
    } while (choice != 6);

    for (int i = 0; i < num_rooms; i++) {
        free(rooms[i].customer_name);
        free(rooms[i].check_in_date);
        free(rooms[i].check_out_date);
    }
    free(rooms);

    return 0;
}

void add_customer() {
    if (num_rooms >= max_rooms) {
        increase_room_capacity(); 
    }

    rooms[num_rooms].room_no = num_rooms + 1; 

    // Allocate memory for dynamically allocated members
    rooms[num_rooms].customer_name = (char*)malloc(50 * sizeof(char));
    rooms[num_rooms].check_in_date = (char*)malloc(11 * sizeof(char));
    rooms[num_rooms].check_out_date = (char*)malloc(11 * sizeof(char));

    printf("\nEnter customer details:\n");
    printf("Customer Name: ");
    scanf(" %[^\n]", rooms[num_rooms].customer_name); 
    printf("Check-in Date (YYYY-MM-DD): ");
    scanf("%s", rooms[num_rooms].check_in_date);
    printf("Check-out Date (YYYY-MM-DD): ");
    scanf("%s", rooms[num_rooms].check_out_date);
    printf("Room Rent: ");
    scanf("%f", &rooms[num_rooms].room_rent);

    num_rooms++;
    printf("Customer added successfully!\n");
}

void increase_room_capacity() {
    max_rooms *= 2; // Double the capacity
    Room* temp = (Room*)realloc(rooms, max_rooms * sizeof(Room));
    if (temp == NULL) {
        printf("Memory reallocation failed.\n");
        return;
    }
    rooms = temp;
}

void display_customer_info() {
    int room_no;

    printf("Enter room number: ");
    scanf("%d", &room_no);

    for (int i = 0; i < num_rooms; i++) {
        if (rooms[i].room_no == room_no) {
            printf("\n Customer Information:\n");
            printf("Room No: %d\n", rooms[i].room_no);
            printf("Customer Name: %s\n", rooms[i].customer_name);
            printf("Check-in Date: %s\n", rooms[i].check_in_date);
            printf("Check-out Date: %s\n", rooms[i].check_out_date);
            printf("Room Rent: %.2f\n", rooms[i].room_rent);
            return;
        }
    }

    printf("Room not found.\n");
}

void search_customer() {
    display_customer_info();
}

void check_out_customer() {
    int room_no;

    printf("Enter room number: ");
    scanf("%d", &room_no);

    for (int i = 0; i < num_rooms; i++) {
        if (rooms[i].room_no == room_no) {
            printf("Customer checked out successfully.\n");
            for (int j = i; j < num_rooms - 1; j++) {
                rooms[j] = rooms[j + 1];
            }
            num_rooms--;
            return;
        }
    }

    printf("Room not found.\n");
}

void display_all_rooms() {
    if (num_rooms == 0) {
        printf("No rooms occupied.\n");
        return;
    }

    printf("\nRoom Information:\n");
    for (int i = 0; i < num_rooms; i++) {
        printf("Room No: %d\n", rooms[i].room_no);
        printf("Customer Name: %s\n", rooms[i].customer_name);
        printf("Check-in Date: %s\n", rooms[i].check_in_date);
        printf("Check-out Date: %s\n", rooms[i].check_out_date);
        printf("Room Rent: %.2f\n", rooms[i].room_rent);
        printf("---------------------\n");
    }
}

