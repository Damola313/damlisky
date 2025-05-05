# Hands-on Lab: Using Git to Track and Manage Changes for a Simple Form

## ✅ Project Overview

This project demonstrates how to use Git to manage and track changes in a simple web form. The form allows users to submit their name, email, phone number, and a message. You will use Git for version control, manage feature changes, and practice essential commands like branching and reverting.

---

## 🧰 Prerequisites

- Git installed on your machine
- Basic knowledge of Git commands
- A GitHub account with an existing repository
- Project files: `form.html` and `style.css`

---

## 📂 File Breakdown

### 1. `form.html`

This HTML file creates the structure of a contact form.

#### Key Elements:
- **Text Input for Name**
- **Email Input Field**
- **Phone Number Field**
- **Textarea for Message**
- **Submit Button**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Contact Form</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="form-container">
        <h2>Contact Us</h2>
        <form action="#" method="POST">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="phone">Phone Number:</label>
            <input type="tel" id="phone" name="phone">

            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4" required></textarea>

            <button type="submit">Send</button>
        </form>
    </div>
</body>
</html>
```

---

### 2. `style.css`

This CSS file styles the contact form for better visual presentation.

#### Key Styling:
- **Centered form layout**
- **Rounded inputs and button**
- **Light background and shadow effect**
- **Hover effect on the button**

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}

.form-container {
    background-color: white;
    max-width: 500px;
    margin: 50px auto;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #333;
}

form label {
    display: block;
    margin-top: 10px;
    font-weight: bold;
}

form input,
form textarea {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

form button {
    margin-top: 15px;
    width: 100%;
    padding: 10px;
    background-color: #0077cc;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

form button:hover {
    background-color: #005fa3;
}
```

---

## 🧪 Git Workflow Summary

1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/simple-form.git
    cd simple-form
    ```

2. **Add and Commit Initial Files**
    ```bash
    git add form.html style.css
    git commit -m "Initial commit with form and styles"
    git push origin main
    ```

3. **Make and Commit Changes**
    - Add new fields or styling
    ```bash
    git add .
    git commit -m "Updated form layout and styles"
    git push origin main
    ```

4. **Create a Feature Branch**
    ```bash
    git checkout -b feature-add-captcha
    ```

5. **Merge Feature Branch**
    ```bash
    git checkout main
    git merge feature-add-captcha
    git push origin main
    ```

6. **Undo Local Changes**
    ```bash
    git checkout -- style.css
    ```

7. **Revert to a Previous Version**
    ```bash
    git checkout <commit-hash> -- form.html
    ```

---

## 📌 Outcome

After completing this project, you will have practiced:
- Setting up Git for a real-world web project
- Tracking and committing code changes
- Using branches for feature development
- Reverting to older versions
- Managing your project through GitHub

---

## 🔗 Useful Resources

- [GitHub Docs](https://docs.github.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)

---

## 👤 Author

**Ariyo Damola David**  
Critical Thinking Hands-on Lab  
May 2025
