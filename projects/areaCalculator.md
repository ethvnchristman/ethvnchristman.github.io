---
layout: project
type: project
image: img/Area-of-a-Square-1.png
title: "Area Calculator"
date: 2023
published: true
labels:
  - C
  - Solo Project
  - ICS 212
summary: "A lone project for my ICS 212 course which the objective is to calculate the areas of shapes."
---

This program written in C has the objective of calculating the area of shapes. The user would input their choice of shape they would like to find an area of, and must provide some dimension of value for the program to use in its calculations. Returned would be the area of the shape of their choice. This was one of my midterm projects for my ICS 212 course, and was reflective of all I had learned so far until that point.  

The following code is the entirety of the project. 

<hr>

<pre>

/* @Ethan finished Room class */
  
class Room {
  protected:
    string type, comfort, size;
    int roomNum, dailyRate;
    bool available;

  public:
    Room() {} // default constructor - @Ciara

    // @Ashton's constructor, @Ciara changed dailyRate
    Room(int number, string ac, string c, string s, int dr) {
        roomNum = number;
        available = true;
        type = ac;
        comfort = c;
        size = s;
        dailyRate = dr;
        //setDailyRate(ac, c, s);
    }

    // setters - @Ethan
    void setRoomNumber(int rn) { roomNum = rn; }
    void setType(string t) { type = t; }
    void setComfort(string c) { comfort = c; }
    void setSize(string s) { size = s; }
    void setAvailability(bool a) { available = a; }
    void setDailyRate(int dr){
        dailyRate = dr;
    }
    // getters - @Ethan
    string getType() { return type; }
    string getComfort() { return comfort; }
    string getSize() { return size; }
    int getDailyRate() { return dailyRate; }
    int getRoomNumber() { return roomNum; }
    bool getAvailability() { return available; }
};

// @Ethan finished addRoom function
    void addRoom(vector<Room>& rooms) {
      int roomNum, DailyRate, num;
      string inputType, inputComfort, inputSize, inputDailyRate;
      cout << "\nEnter Room Number: ";
      cin >> roomNum;
      cin.ignore();
      for (int i = 0; i < rooms.size(); i++) { //main loop that starts at begining  
           //check each if room number already exists
              if (rooms[i].getRoomNumber() == roomNum) {
                  cout << "Room Number Already Exists";
                  return; //if exists exit function without adding room
              }
          }
      cout << "\nType AC/No AC (A/N) : ";
      getline(cin,inputType);
      if (inputType != "A" && inputType != "N") {
        cout << "\nInvalid Input.\n";
        return;
      }
      cout << "\nType Comfort (S/N) : ";
      getline(cin,inputComfort);
      if (inputComfort != "S" && inputComfort != "N") {
        cout << "\nInvalid Input.\n";
        return;
      }
      cout << "\nType Size (B/S) : ";
      getline(cin, inputSize);
      if (inputSize != "B" && inputSize != "S") {
        cout << "\nInvalid Input.\n";
        return;
      }
      
      cout << "\nDaily Rate: ";
      cin >> inputDailyRate;
      istringstream dr(inputDailyRate);
      if (!(dr >> num)) {
        cout << "Invalid input. Please enter an integer." << endl;
        return;
      }
      DailyRate = stoi(inputDailyRate);
      cout << "Room successfully added!\n";
      Room newRoom(roomNum, inputType, inputComfort, inputSize, DailyRate); //new room object
      newRoom.setAvailability(true);
      rooms.push_back(newRoom); //add new room object to end of room vector
    }

    void deleteRoom(vector<Room>& rooms){
      int roomNum;
      cout << "Enter room number to delete: ";
      cin >> roomNum;
      cin.ignore();
      for(int i = 0; i < rooms.size(); i++){
        if(rooms[i].getRoomNumber() == roomNum){
          cout << "\nRoom Details to Delete\n\n";
          cout << "Room number: " << rooms[i].getRoomNumber() << "\n";
          cout << "Room with AC/No AC (A/N): " << rooms[i].getType() << "\n";
          cout << "Type of Comfort (S/N): " << rooms[i].getComfort() << "\n";
          cout << "Room Size (B/S): " << rooms[i].getSize() << "\n";
          cout << "Daily Rate: " << rooms[i].getDailyRate() << "\n";

          rooms.erase(rooms.begin()+i);
          cout << "Room Deleted Successfully!";
          return;
        }
      }
      cout << "Room Not Found";

    }

    // @Ethan finished search room funcion
    void searchRoom(vector<Room>& rooms) {
      int roomNum;
      cin.ignore();
      cout << "\nEnter Room Number: ";
      cin >> roomNum;
      cin.ignore();

      bool roomFound = false;  // Flag to check if the room is found
      for (int i = 0; i < rooms.size(); i++) {
          if (rooms[i].getRoomNumber() == roomNum) {
              roomFound = true;  // Set the flag to true if the room is found
              cout << "Room Details" << endl;
              if (rooms[i].getAvailability()) {
                  cout << "\nRoom is available" << endl;
              } else {
                  cout << "\nRoom is not available" << endl;
              }

              cout << "Room Number: " << rooms[i].getRoomNumber() << endl;
              cout << "Type AC/No AC (A/N) " << rooms[i].getType() << endl;
              cout << "Comfort (S/N) " << rooms[i].getComfort() << endl;
              cout << "Size (B/S) " << rooms[i].getSize() << endl;
              cout << "Daily Rate: " << rooms[i].getDailyRate() << endl;
              break;
          }
      }

      // Print the "not found" message only if the room is not found
      if (!roomFound) {
          cout << "\nRoom does not exist, try again." << endl;
      }
  };
                                                

<>
</pre>

<hr>
