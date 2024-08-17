This HTML document is a simple web-based dashboard that allows users to manage (add, update, remove, and find) products in a shop. It uses Firebase Realtime Database to store and retrieve product data. Here’s a detailed explanation of the code:

### Overview:
1.	**Webpage:**
 
 ![image](https://github.com/user-attachments/assets/f1122287-ce56-4173-a54b-abc07a936932)

2.	**Add function:**

![image](https://github.com/user-attachments/assets/c3d89149-617e-4734-bee7-270fb67dbe18)
![image](https://github.com/user-attachments/assets/4ce61e63-5392-4602-bf6d-6f828a1aa56c)

3.	**Update function:**

![image](https://github.com/user-attachments/assets/2da1082b-b8cd-43c7-8aa2-29127955e519)
![image](https://github.com/user-attachments/assets/7aad4025-2133-4f08-be5b-5b9f7f748ebf)

4.	**Remove function:**
 
![image](https://github.com/user-attachments/assets/edecd5f7-3f66-45c0-8b0f-a61a5bb96b44)
![image](https://github.com/user-attachments/assets/56f225b7-76df-497f-94c9-117ef7e102d1)

5.	**Search:**

![image](https://github.com/user-attachments/assets/6e0278a0-30e4-4c02-bd69-b06c10a43803)
 



### HTML Structure:
1. **DOCTYPE and Basic Setup:**
   - `<!DOCTYPE html>` declares the document type as HTML5.
   - `<html lang="en">` defines the language as English.

2. **Head Section:**
   - Contains metadata, links to external stylesheets (like Bootstrap for styling), and scripts.
   - `meta charset="UTF-8"` defines the character encoding as UTF-8.
   - `meta name="viewport" content="width=device-width, initial-scale=1.0"` makes the webpage responsive on mobile devices.
   - `link rel="stylesheet"` and `script src` tags load external resources:
     - **Bootstrap CSS**: Provides styling and responsive design.
     - **jQuery**: A JavaScript library for DOM manipulation and event handling.
     - **Popper.js** and **Bootstrap JS**: Required for Bootstrap's JavaScript components.
     - **Font Awesome**: Adds icon support.
     - **Google Fonts**: Loads custom fonts.
   - `<link rel="stylesheet" href="style.css">` includes a custom CSS file (`style.css`) for additional styling.

3. **Body Section:**
   - Contains two main divisions: `#enterdetails` for entering product details and `#finddetails` for finding products by ID.

#### `#enterdetails`:
   - A form-like section where users can input:
     - `ID`: Unique identifier for the product.
     - `Product`: Name of the product.
     - `Cost`: Price of the product.
     - `Brand`: Brand name of the product.
     - `Quantity`: Available quantity of the product.
   - Three buttons for managing the data:
     - `Add` button (`#insert`): Adds a new product to the database.
     - `Update` button (`#update`): Updates an existing product’s details.
     - `Remove` button (`#remove`): Deletes a product from the database.

#### `#finddetails`:
   - A section for finding a product by its `ID`.
   - Contains an input field for entering the `ID` and a `Find` button (`#find`).
   - Displays the product details (`Name`, `Cost`, `Brand`, `Quantity`) if found.

### JavaScript (Embedded in `<script type="module">`):
   - The script uses **Firebase** to interact with the Realtime Database.
   - **Firebase SDKs** are imported for initializing the app and interacting with the database.

#### Firebase Setup:
   - `firebaseConfig` contains the configuration for connecting to your Firebase project.
   - `initializeApp(firebaseConfig)` initializes Firebase with the given configuration.
   - `getDatabase()` initializes the connection to the Firebase Realtime Database.

#### JavaScript Variables:
   - The script selects HTML elements (like input fields and buttons) using `document.querySelector` and assigns them to variables for later use.

#### Functions:
1. **InsertData()**:
   - Uses the `set` method from Firebase to add a new product to the database under the path `Shop/{ID}`.
   - The data includes `ID`, `Product`, `Cost`, `Brand`, and `Quantity`.
   - On success, it alerts the user that the data was added successfully; otherwise, it shows an error.

2. **FindData()**:
   - Uses the `get` method to retrieve product data from the database using the entered `ID`.
   - If the product exists, it displays the product details on the page; otherwise, it alerts the user that no data was found.

3. **UpdateData()**:
   - Uses the `update` method to modify an existing product's details in the database.
   - On success, it alerts the user that the data was updated successfully; otherwise, it shows an error.

4. **RemoveData()**:
   - Uses the `remove` method to delete a product from the database based on the entered `ID`.
   - On success, it alerts the user that the data was removed successfully; otherwise, it shows an error.

#### Event Listeners:
   - `insertBtn`, `findBtn`, `updateBtn`, and `removeBtn` are linked to their respective functions (`InsertData`, `FindData`, `UpdateData`, `RemoveData`) using `addEventListener("click", functionName)`.

### Summary:
- **Purpose**: The code provides a simple interface for managing product data in a shop using Firebase Realtime Database.
- **Technologies Used**: HTML, CSS (Bootstrap), JavaScript (jQuery, Firebase), and Firebase Realtime Database.
- **Functionalities**: Add, update, remove, and find products by ID with real-time data storage and retrieval using Firebase.
