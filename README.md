**Image Gallery App – FastAPI & React**

### **📌 Project Overview**
This project is a simple image gallery application that allows users to upload images via a FastAPI backend and view them in a React frontend. The uploaded images are stored locally, with metadata managed in a JSON file. The app provides a smooth UI for browsing uploaded images, making it a great starter project for integrating FastAPI with React.

---

### **🖼️ Expected UI Output**
The final result should look like this:

```
+---------------------------------------+
| Image Gallery                         |
+---------------------------------------+
| [Upload Image]                        |
|                                       |
| [ 🖼 Image1 ]  [ 🖼 Image2 ]  [ 🖼 Image3 ] |
| [ 🖼 Image4 ]  [ 🖼 Image5 ]  [ 🖼 Image6 ] |
|                                       |
+---------------------------------------+
```

The UI consists of:
- An **Upload Image** button to select and upload images.
- A **grid of uploaded images** fetched dynamically from the backend.
- Clickable images that can be viewed in full size.

---

## **Backend (FastAPI) Setup**

### **1️⃣ Create the Backend Folder**
Open a terminal and create a new project folder:
```sh
mkdir image-gallery
cd image-gallery
mkdir backend
cd backend
```

---

### **2️⃣ Install FastAPI & Required Packages**
FastAPI is a modern Python framework for building APIs. Install it along with Uvicorn (for running the server) and `python-multipart` (for handling file uploads):
```sh
pip install fastapi uvicorn python-multipart
```

---

### **3️⃣ Create an `images/` Folder**
This folder will store all uploaded images. Run:
```sh
mkdir images
```

---

### **4️⃣ Create a `metadata.json` File**
This file will store image metadata such as filenames and paths e.g. data.json can be used as an example. Create a file named `metadata.json` inside `backend/` and initialize it with an empty list:
```json
[]
```

---

### **5️⃣ Create `main.py` for the Backend**
Inside `backend/`, create a Python file called `main.py`. This file will:
- Accept file uploads.
- Store metadata in `metadata.json`.
- Serve images via API.

---

### **6️⃣ Start the FastAPI Server**
To run the backend server, use the following command inside the `backend/` folder:
```sh
uvicorn main:app --reload
```
✅ The backend is now running at `http://127.0.0.1:8000`.

---

### **7️⃣ Test API Endpoints**
Use **cURL**, **Postman**, or a browser to test the API.

#### **Upload an Image**
```sh
curl -X 'POST' 'http://127.0.0.1:8000/upload/' -F 'file=@path/to/image.jpg'
```
✔️ This uploads an image and adds metadata to `metadata.json`.

#### **Get List of Images**
```sh
curl -X 'GET' 'http://127.0.0.1:8000/images/'
```
✔️ This returns a list of all uploaded images.

#### **Fetch an Image**
```sh
curl -X 'GET' 'http://127.0.0.1:8000/images/image.jpg'
```
✔️ This serves the requested image.

---

## **Frontend (React) Setup**

### **8️⃣ Create the Frontend Folder**
Go back to the `image-gallery` project root and create a new folder for the frontend:
```sh
cd ..
mkdir frontend
cd frontend
```

---

### **9️⃣ Initialize a React App**
Run the following command to create a new React project:
```sh
npx create-react-app .
```

---

### **🔟 Install Axios for API Requests**
Axios is used to send HTTP requests to the FastAPI backend. Install it using:
```sh
npm install axios
```

---

### **1️⃣1️⃣ Create `ImageUploader.js`**
Inside `frontend/src/components/`, create a new file called `ImageUploader.js`.  
This component will allow users to select and upload images.

---

### **1️⃣2️⃣ Create `ImageGallery.js`**
Inside `frontend/src/components/`, create `ImageGallery.js`.  
This component will fetch images from the backend and display them.

---

### **1️⃣3️⃣ Modify `App.js`**
Replace the contents of `frontend/src/App.js` to include `ImageUploader.js` and `ImageGallery.js`.

---

### **1️⃣4️⃣ Start the React App**
Inside the `frontend/` folder, run:
```sh
npm start
```
✅ The frontend is now running at `http://localhost:3000`.

---

## **🎯 Summary**
- **Backend**: FastAPI handles image uploads, serves images, and stores metadata.  
- **Frontend**: React fetches image metadata and displays images dynamically.  

🚀 **Now you have a working Image Gallery App!**

