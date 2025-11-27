# 🍽️ Restaurant Dashboard - Deployment Guide

A Streamlit web application for exploring restaurant data in London with interactive maps and database queries.

## 🌐 Live Demo
[View Live App](https://your-app-url.streamlit.app) *(Update this after deployment)*

---

## 🚀 Deploy to Streamlit Community Cloud (FREE)

### Prerequisites
1. GitHub account (free)
2. Streamlit Community Cloud account (free) - Sign up at [share.streamlit.io](https://share.streamlit.io)
3. Your database credentials

---

### Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **+** icon (top right) → **New repository**
3. Repository settings:
   - **Name:** `restaurant-dashboard` (or your choice)
   - **Description:** "Interactive restaurant dashboard with maps and database queries"
   - **Public** (required for free Streamlit deployment)
   - **Add README:** ✅ Check this box
4. Click **Create repository**

---

### Step 2: Upload Your Files

**Option A: Using GitHub Web Interface (Easier)**

1. On your new repository page, click **Add file** → **Upload files**
2. Drag and drop these files:
   - `app_Barber_Bryan.py`
   - `requirements.txt`
   - `.gitignore`
   - `secrets.toml.example`
   - `README.md` (this file)
3. **IMPORTANT:** Do NOT upload any file with actual database passwords!
4. Click **Commit changes**

**Option B: Using Git Command Line**

```bash
# Navigate to your project folder
cd "C:\Users\bryan\...\Restaurant_App"

# Initialize git
git init

# Add files
git add app_Barber_Bryan.py requirements.txt .gitignore secrets.toml.example README.md

# Commit
git commit -m "Initial commit: Restaurant dashboard"

# Connect to GitHub (replace with your repository URL)
git remote add origin https://github.com/YOUR_USERNAME/restaurant-dashboard.git

# Push
git branch -M main
git push -u origin main
```

---

### Step 3: Set Up Streamlit Community Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io)
2. Click **Sign in with GitHub**
3. Authorize Streamlit to access your repositories
4. Click **New app**

---

### Step 4: Configure Deployment

Fill in the deployment form:

- **Repository:** Select `your-username/restaurant-dashboard`
- **Branch:** `main`
- **Main file path:** `app_Barber_Bryan.py`
- **App URL:** Choose a custom URL (e.g., `bryan-restaurant-dashboard`)

---

### Step 5: Add Database Secrets (CRITICAL!)

Before clicking "Deploy", you MUST add your database credentials:

1. Click **Advanced settings**
2. In the **Secrets** section, paste this (with YOUR actual credentials):

```toml
[database]
host = "db-mysql-itom-do-user-28250611-0.j.db.ondigitalocean.com"
port = 25060
user = "restaurant_readonly"
password = "SecurePassword123!"
database = "restaurant"
```

3. Click **Save**

---

### Step 6: Deploy!

1. Click **Deploy!**
2. Wait 2-3 minutes while Streamlit builds and deploys your app
3. You'll get a URL like: `https://bryan-restaurant-dashboard.streamlit.app`
4. Share this URL with anyone!

---

## 🔧 Local Development Setup

If you want to run the app locally:

### Step 1: Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/restaurant-dashboard.git
cd restaurant-dashboard
```

### Step 2: Create virtual environment
```bash
# Using conda
conda create -n restaurant_app python=3.12
conda activate restaurant_app

# OR using venv
python -m venv .venv
source .venv/bin/activate  # Mac/Linux
.venv\Scripts\activate     # Windows
```

### Step 3: Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Add database secrets
Create a file at `.streamlit/secrets.toml`:

```toml
[database]
host = "your-database-host"
port = 25060
user = "your-username"
password = "your-password"
database = "restaurant"
```

### Step 5: Run the app
```bash
streamlit run app_Barber_Bryan.py
```

---

## 📁 Project Structure

```
restaurant-dashboard/
├── app_Barber_Bryan.py          # Main Streamlit application
├── requirements.txt              # Python dependencies
├── .gitignore                    # Git ignore file
├── secrets.toml.example          # Secrets template (DO NOT add real credentials!)
└── README.md                     # This file
```

---

## 🎨 Features

### Tab 1: HW Summary
- Project overview and approach
- Customizations documentation
- Technologies used

### Tab 2: Database Query (Q1)
- Search restaurants by name pattern
- Filter by vote range (0 to max)
- Display results with summary statistics
- Shows: Restaurant name, votes, city, address, rating

### Tab 3: Interactive Map (Q2)
- Auto-displays map of London restaurants
- Custom CartoDB Positron tiles
- Blue markers with cutlery icons
- Click markers for detailed popups
- 20 restaurants mapped

---

## 🎯 Customizations

1. **Layout & Styling (7 pts)**
   - Custom CSS with dark blue sidebar (#1e3a5f)
   - Professional color scheme
   - Button hover effects
   - Responsive column layouts

2. **Map Tiles (7 pts)**
   - CartoDB Positron tiles (clean, modern)
   - Better contrast than default OpenStreetMap

3. **Data Display (6 pts)**
   - Formatted vote counts: "150 👍"
   - Star ratings: "⭐ 4.5"
   - Summary statistics
   - Color-coded messages

---

## 🛠️ Technologies Used

- **Frontend:** Streamlit 1.29.0
- **Database:** MySQL with mysql-connector-python
- **Data Processing:** Pandas 2.1.4
- **Mapping:** Folium 0.15.1 + streamlit-folium
- **Hosting:** Streamlit Community Cloud

---

## 🔐 Security Notes

- Database credentials are stored in Streamlit secrets (not in code)
- `.gitignore` prevents committing sensitive files
- Read-only database user for security
- Public deployment uses environment-based configuration

---

## 📝 Assignment Information

- **Course:** ITOM6265 - Database Management
- **Assignment:** HW2 - Restaurant Dashboard
- **Student:** Bryan Barber
- **Features:** Database queries, interactive maps, custom visualizations

---

## 📸 Screenshots

*(Add screenshots here after deployment)*

### HW Summary Page
![HW Summary](screenshots/hw_summary.png)

### Database Query
![Database Query](screenshots/db_query.png)

### Interactive Map
![Interactive Map](screenshots/map.png)

---

## 🐛 Troubleshooting

### "Database connection failed"
- Check that secrets are properly configured in Streamlit Cloud
- Verify database credentials are correct
- Ensure database allows connections from Streamlit's IP ranges

### "Module not found"
- Check that `requirements.txt` includes all dependencies
- Redeploy the app to reinstall packages

### "App is taking too long to load"
- Streamlit apps sleep after 7 days of inactivity
- First load after sleep takes ~30 seconds
- Subsequent loads are instant

---

## 🎓 Learning Outcomes

This project demonstrates:
- Streamlit web application development
- MySQL database integration
- Interactive data visualization with Folium
- Secure credential management
- Cloud deployment best practices
- SQL queries (SELECT, WHERE, LIKE, BETWEEN, ORDER BY)

---

## 📄 License

Educational project for ITOM6265 coursework.

---

## 🙏 Acknowledgments

- ITOM6265 course materials
- Streamlit documentation
- Folium mapping library
- CartoDB for map tiles

---

## 📧 Contact

For questions about this project, contact Bryan Barber.

---

**Deployed with ❤️ using Streamlit Community Cloud**
