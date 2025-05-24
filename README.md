# Images to Video Converter App
### Access the Application  
[Click here to open the app](https://project-amigos.onrender.com/)

## Introduction

This web-based **Image to Video Converter** application is developed using Flask. It enables users to upload images, convert them into a video format, and enhance the video with audio. User management through authentication, image database storage, and audio retrieval are also integrated.

---

## Key Features

### User Registration and Login

- **User Signup**
  - **Route**: `/signup`
  - Allows new users to register by submitting a username, full name, email, and password. Passwords are securely hashed using bcrypt before being stored.

- **User Login**
  - **Route**: `/login`
  - Existing users can log in with their username and password. A JWT token is created on successful login and stored in the session.

### Uploading and Saving Images

- **Upload Images**
  - **Route**: `/upload_files`
  - Enables uploading multiple image files to the server and stores them in the database.

- **Upload Selected Images**
  - **Route**: `/upload_seleted_files`
  - Lets users upload only selected images. These are also stored server-side and in the database.

### Image Retrieval

- **Retrieve Images**
  - **Route**: `/user_profile/<username>`
  - Retrieves all images uploaded by the user and displays them on the user's profile page.

- **Retrieve Selected Images**
  - **Route**: `/selectedImages`
  - Fetches the selected images from the database and returns them as a JSON object.

### Video and Audio Processing

- **Generate Video**
  - **Function**: `create_video`
  - Combines uploaded images into a video file, which is saved on the server.

- **Merge Audio**
  - **Route**: `/get_audio_path`
  - Merges an audio track with the created video and stores the final version on the server.

### Audio Retrieval

- **Fetch Audio Files**
  - **Function**: `retrieve_audio_files`
  - Retrieves audio files from the database and saves them to the server.

### User Profile

- **User Profile**
  - Route: `/user_profile/<username>`
  - Displays the user's profile with all uploaded images.

### Logout and Cleanup

- **Logout and Delete**
  - Route: `/logout_and_delete`
  - Logs out the user and deletes the selected images and merged video from the server.

## Technical Overview

### Database Integration

- **Connecting to Database**
  - **Function**: `db_config`
  - Establishes a secure database connection using the provided credentials and certificate.

- **Closing Connection**
  - **Function**: `close_connection`
  - Closes the active database session.

### Token Authentication with JWT

- **Creating Tokens**
  - **Function**: `generate_token`
  - Produces a JWT token for authenticated sessions.

- **Validating Tokens**
  - **Function**: `verify_token`
  - Ensures the authenticity of the stored JWT token.

---

## Flask Application Routes

- `/` – Home page.
- `/signup` – Handles user registration.
- `/login` – Authenticates users.
- `/user_profile/<username>` – Displays the user's profile.
- `/upload_files` – Handles image uploads.
- `/upload_seleted_files` – Handles selected image uploads.
- `/selectedImages` – Retrieves selected images.
- `/video` – Generates a video from uploaded images.
- `/get_audio_path` – Adds audio to the created video.
- `/logout_and_delete` – Logs out the user and deletes selected images and merged video.                    

---

## Deployment Information

This application is deployed on **Render** and can be accessed at:  
[Images to Video Converter App](https://project-amigos.onrender.com/)


---

## How to Run the Application

1. **Install Packages**  
   Use the command `pip install -r requirements.txt` to install all necessary Python packages.

2. **Configure Database**  
   Update the `db_config` function with your database credentials.

3. **Run the App** 
   Start the server using `python app.py`.

4. **Access the App**  
   Open a web browser and navigate to `http://localhost:5007` to access the app.

---
