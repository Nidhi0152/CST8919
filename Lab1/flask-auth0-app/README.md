
#  Flask Auth0 Integration App

This is a simple Python web application built with **Flask** and **Authlib**, using **Auth0** for secure authentication. It demonstrates how to:
- Log in and log out with Auth0
- Access a protected route only when authenticated

---

##  Features

- User login with Auth0
- Session management with Flask
- Protected route (`/protected`) for authenticated users
- Basic UI using Jinja2 templates

---

##  Tech Stack

- **Python 3**
- **Flask**
- **Authlib**
- **Auth0**
- **dotenv** (for managing secrets)
- **WSL or Linux environment**

---

##  Setup Instructions

### 1.  Clone the project

```bash
git clone https://github.com/your-username/flask-auth0-app.git
cd flask-auth0-app
```

### 2.  Create and activate a virtual environment

```bash
sudo apt install python3-venv  # if not already installed
python3 -m venv venv
source venv/bin/activate
```

### 3.  Install dependencies

```bash
pip install -r requirements.txt
```

---

##  Why `requirements.txt`?

The `requirements.txt` file lists all the Python packages needed to run the project. It allows you to install all dependencies with a single command:

```bash
pip install -r requirements.txt
```

This ensures your app has the correct libraries for Flask, Auth0 authentication, and environment variable management.

---

##  Configure Auth0

1. Go to [Auth0 Dashboard](https://manage.auth0.com)
2. Create a **Regular Web Application**
3. Copy the following values:
   - **Domain**
   - **Client ID**
   - **Client Secret**
4. In Application Settings:
   - Allowed Callback URLs → `http://localhost:3000/callback`
   - Allowed Logout URLs → `http://localhost:3000`
5. Save your changes.

---

##  Configure `.env` File

Create a `.env` file in the project root:

```env
AUTH0_CLIENT_ID=your-client-id
AUTH0_CLIENT_SECRET=your-client-secret
AUTH0_DOMAIN=your-domain.auth0.com
APP_SECRET_KEY=your-random-secret
```

Generate a secure `APP_SECRET_KEY` with:

```bash
openssl rand -hex 32
```

---

##  Run the App

```bash
python server.py
```

Visit: [http://localhost:3000](http://localhost:3000)

---

##  Protected Route

- Go to [http://localhost:3000/protected](http://localhost:3000/protected)
- You must be logged in to access it
- If not logged in, you'll be redirected to the login page

---

##  Example User Info

After logging in, your user profile data will look something like this:

```json
{
  "name": "you@example.com",
  "nickname": "you",
  "picture": "https://...",
  "sub": "auth0|abc123"
}
```

---

##  Demo Video

- Got to [https://youtu.be/vuUO0gIeRR0]
---


