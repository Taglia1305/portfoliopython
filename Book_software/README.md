# Digital Library Management System

This project is an interactive Python application designed to manage a professional book catalog. It simulates a library environment, allowing for real-time data entry, search, and status tracking of literary volumes.

## Project Overview
The software provides a command-line interface (CLI) that enables librarians or administrators to maintain a digital database of books. It handles everything from simple inventory logging to complex status updates such as loan tracking and availability management.

### Key Features
* **Dynamic Cataloging**: Allows for the real-time addition of new titles, including metadata such as author, ISBN, and genre.
* **Advanced Search Engine**: Implements filtering logic to locate specific volumes within the database based on multiple criteria.
* **Loan & Availability Tracking**: A dedicated system to update the status of each book (e.g., Available, Loaned, Under Maintenance), ensuring the database reflects the current state of the library.
* **Interactive CLI**: A user-friendly, loop-based interface that processes user commands at runtime without needing to restart the application.

### Technical Implementation
* **In-Memory Data Structures**: Utilizes nested dictionaries and lists to manage the library database efficiently during the session.
* **Runtime Input Validation**: Includes robust checks to ensure user inputs (such as IDs or dates) are correctly formatted before being committed to the system.
* **State Management**: Implements logic to handle the transition of book statuses, preventing errors like "double-loaning" a volume.
* **Modular Logic**: The code is structured into specific functions for data entry, search, and reporting, ensuring high maintainability.

---

## How it Works
The application runs in a continuous loop, presenting the user with a menu of options. Each action is processed through dedicated functions that interact with the central data structure, providing immediate feedback on the success of each operation.

### Future Improvements
* **Persistent Storage**: Integration with SQL or JSON files to save the catalog state between sessions.
* **User Authentication**: Implementation of different access levels for guests and administrators.
