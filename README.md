# Pratzz's Blog

Welcome to Pratzz's Blog, a simple and elegant blogging website built using Flask. This website allows users to read blog posts, learn about the author, and contact the author via a contact form. The website is styled using Bootstrap, ensuring a responsive and modern design.

## Features

- **Home Page**: Displays a list of all blog posts.
- **About Page**: Provides information about the author.
- **Contact Page**: Allows users to send a message to the author.
- **Individual Post Page**: Displays the full content of a blog post.

## Technologies Used

- **Flask**: A lightweight WSGI web application framework in Python.
- **HTML/CSS**: For the structure and styling of the web pages.
- **Bootstrap**: For responsive design and layout.
- **SMTP**: For sending emails via the contact form.

## Project Structure

```
PratzzBlog/
│
├── static/
│   ├── assets/
│   │   ├── img/
│   │   │   ├── home-bg.jpg
│   │   │   ├── about-bg.jpg
│   │   │   ├── contact-bg.jpg
│   ├── css/
│   │   ├── styles.css
│   ├── js/
│   │   ├── scripts.js
│
├── templates/
│   ├── about.html
│   ├── contact.html
│   ├── footer.html
│   ├── header.html
│   ├── index.html
│   ├── post.html
│
├── main.py
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.x
- Flask
- Requests

### Installation

1. Clone the repository:

```bash
git clone https://github.com/Prathamesh326/blog-with-contact-form.git
cd blog-with-contact-form
```

2. Install the required packages:

```bash
pip install flask requests
```

3. Update the email credentials and npoint URL in `main.py`:

```python
my_email = "your_email@gmail.com"
password = "your_email_password"
posts = requests.get("https://api.npoint.io/your_npoint_endpoint").json()
```

4. Run the application:

```bash
python main.py
```

5. Open your browser and navigate to `http://127.0.0.1:5001`.

## Contact Form

The contact form in `contact.html` allows users to send messages directly to the author's email. The form gathers details such as the user's name, email, phone number, and message. Upon submission, the data is processed and sent via email using the SMTP protocol.

## SMTP Configuration

The `send_mail` function in `main.py` handles the email sending process:

```python
def send_mail(name, email, phone, msg):
    email_message = f"Subject:New Message\n\nName: {name}\nEmail: {email}\nPhone: {phone}\nMessage:{msg}"
    with smtplib.SMTP("smtp.gmail.com", port=587) as connection:
        connection.starttls()
        connection.login(my_email, password)
        connection.sendmail(my_email, my_email, email_message)
```

Make sure to replace `my_email` and `password` with your actual email credentials.

---

Thank you for visiting Pratzz's Blog! Feel free to explore and reach out via the contact form if you have any questions or feedback.
