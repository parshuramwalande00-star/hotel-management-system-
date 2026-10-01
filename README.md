#include <iostream>
#include <fstream>
#include <vector>
#include <string>
using namespace std;

// Room Class
class Room {
private:
    int roomNumber;
    string type;
    bool booked;
    string customerName;

public:
    Room(int number = 0, string roomType = "Standard") {
        roomNumber = number;
        type = roomType;
        booked = false;
        customerName = "";
    }

    int getRoomNumber() const {
        return roomNumber;
    }

    bool isBooked() const {
        return booked;
    }

    string getCustomerName() const {
        return customerName;
    }

    void bookRoom(string name) {
        booked = true;
        customerName = name;
    }

    void checkout() {
        booked = false;
        customerName = "";
    }

    void display() const {
        cout << "Room No: " << roomNumber
             << " | Type: " << type
             << " | Status: ";

        if (booked)
            cout << "Booked by " << customerName << endl;
        else
            cout << "Available" << endl;
    }
};

// Customer Class
class Customer {
private:
    string name;
    string phone;
    int roomNumber;

public:
    Customer(string n = "", string p = "", int r = 0) {
        name = n;
        phone = p;
        roomNumber = r;
    }

    string getName() const {
        return name;
    }

    int getRoomNumber() const {
        return roomNumber;
    }

    void display() const {
        cout << "Name: " << name
             << " | Phone: " << phone
             << " | Room: " << roomNumber << endl;
    }
};

// Hotel Management Class
class Hotel {
private:
    vector<Room> rooms;
    vector<Customer> customers;

public:

    Hotel() {
        // Create rooms
        for (int i = 101; i <= 105; i++)
           # hotel-management-system-