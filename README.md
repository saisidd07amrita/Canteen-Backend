# Canteen Menu Management System (Backend)

This is the backend for a canteen menu management system using Flask and MongoDB. It provides APIs for retrieving, updating, and deleting menu items for different canteens.

## Features
- Fetch menu items for a specific canteen.
- Add or update menu items dynamically.
- Delete menu items.
- Pre-populated default menu items for each canteen if the database is empty.

## Tech Stack
- **Backend:** Flask
- **Database:** MongoDB Atlas
- **API Testing:** Postman (optional)
- **Frontend Integration:** Supports CORS for seamless frontend communication

## Setup Instructions

### 1. Clone the repository
```sh
git clone https://github.com/yourusername/canteen-menu-backend.git
cd canteen-menu-backend
```

### 2. Install dependencies
Ensure you have Python installed (preferably Python 3.x). Then, install the required dependencies:
```sh
pip install flask flask-cors pymongo
```

### 3. Configure MongoDB Atlas
Modify the connection string in the `app.py` file to match your MongoDB Atlas credentials:
```python
client = MongoClient("your-mongodb-connection-string")
db = client["canteen"]
```

### 4. Run the Flask server
```sh
python app.py
```
By default, the server runs on `http://127.0.0.1:5000/`.

## API Endpoints

### 1. Get Menu Items
**Endpoint:** `GET /menu/<canteen>`

**Description:** Retrieves all menu items for a specific canteen.

**Example Request:**
```sh
GET http://127.0.0.1:5000/menu/IT
```

**Example Response:**
```json
[
  { "name": "Chicken Biryani", "price": 150 },
  { "name": "Mutton Biryani", "price": 200 }
]
```

### 2. Add/Update a Menu Item
**Endpoint:** `POST /menu/<canteen>`

**Description:** Adds or updates a menu item for a specific canteen.

**Example Request:**
```sh
POST http://127.0.0.1:5000/menu/IT
Content-Type: application/json

{
  "name": "Paneer Biryani",
  "price": 160
}
```

**Example Response:**
```json
{ "message": "IT menu updated" }
```

### 3. Delete a Menu Item
**Endpoint:** `DELETE /menu/<canteen>/<item_name>`

**Description:** Deletes a menu item from a specific canteen.

**Example Request:**
```sh
DELETE http://127.0.0.1:5000/menu/IT/Chicken%20Biryani
```

**Example Response:**
```json
{ "message": "Item deleted from IT menu" }
```

## Deployment
To deploy this project, consider using platforms like **Heroku**, **Render**, or **AWS EC2**. Ensure to update CORS settings accordingly.

## License
This project is licensed under the MIT License.

---
Made by Sai Siddharth

