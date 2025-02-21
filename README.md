<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reyansh Velvet Vantage Villas - Food Delivery</title>
    <link rel="stylesheet" href="clone.css"> <!-- Link to your CSS file -->
    <script src="clone.js" defer></script> <!-- Link to your JavaScript file -->
</head>
<body>
    <header>
        <h1>Reyansh Velvet Vantage Villas</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#about">About Us</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <div id="cart-info">
            <span id="cart-count">0</span> items in cart
        </div>
    </header>

    <main>
        <section id="home">
            <h2>Welcome to Reyansh Velvet Vantage Villas</h2>
            <p>Your favorite food delivered to your doorstep!</p>
        </section>

        <section id="menu">
            <h2>Our Menu</h2>
            <div class="menu-item">
                <h3>Dish Name</h3>
                <p>Description of the dish.</p>
                <span>Price: Rs. 100.00</span>
                <button class="add-to-cart">Add to Cart</button>
            </div>
            <!-- Repeat for more menu items -->
        </section>

        <section id="about">
            <h2>About Us</h2>
            <p>We are dedicated to providing the best food delivery service in the area.</p>
        </section>

        <section id="contact">
            <h2>Contact Us</h2>
            <form id="contact-form" action="#" method="post">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>
                
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                
                <label for="message">Message:</label>
                <textarea id="message" name="message" required></textarea>
                
                <button type="submit">Send Message</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Reyansh Velvet Vantage Villas. All rights reserved.</p>
    </footer>
</body>
</html>



/* General Styles */
body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    line-height: 1.6;
    background-color: #f4f4f4;
    color: #333;
}

header {
    background-color: #4CAF50;
    color: white;
    padding: 20px 0;
    text-align: center;
}

nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

nav ul li a:hover {
    text-decoration: underline;
}

/* Main Section Styles */
main {
    max-width: 800px;
    margin: 20px auto;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

section {
    margin-bottom: 20px;
}

h2 {
    color: #4CAF50;
}

/* Menu Item Styles */
.menu-item {
    border: 1px solid #ccc;
    border-radius: 5px;
    margin: 10px 0;
    padding: 15px;
    background-color: #f9f9f9;
    transition: background-color 0.3s;
}

.menu-item:hover {
    background-color: #e9e9e9;
}

.menu-item h3 {
    margin: 0;
}

.menu-item button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s;
}



// clone.js

// Initialize cart count
let cartCount = 0;

// Function to update the cart count display
function updateCartCount() {
    const cartCountDisplay = document.getElementById('cart-info');
    if (cartCountDisplay) {
        cartCountDisplay.textContent = `${cartCount} items in cart`;
    }
}

// Function to handle adding items to the cart
function setupAddToCartButtons() {
    const addToCartButtons = document.querySelectorAll('.menu-item button');

    addToCartButtons.forEach(button => {
        button.addEventListener('click', () => {
            cartCount++;
            updateCartCount();
            alert('Item added to cart!');
        });
    });
}

// Function to validate the contact form
function setupContactFormValidation() {
    const contactForm = document.querySelector('form');

    contactForm.addEventListener('submit', (event) => {
        const name = document.getElementById('name').value.trim();
        const email = document.getElementById('email').value.trim();
        const message = document.getElementById('message').value.trim();

        if (!name || !email || !message) {
            alert('Please fill in all fields.');
            event.preventDefault(); // Prevent form submission
        } else {
            alert('Thank you for your message!');
        }
    });
}

// Function to implement smooth scrolling for navigation links
function setupSmoothScrolling() {
    const links = document.querySelectorAll('nav ul li a');

    links.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            const targetId = link.getAttribute('href');
            const targetElement = document.querySelector(targetId);

            if (targetElement) {
                targetElement.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }
        });
    });
}

// Initialize all functionalities when the DOM is fully loaded
document.addEventListener('DOMContentLoaded', () => {
    // Create and display cart info
    const cartInfoDiv = document.createElement('div');
    cartInfoDiv.id = 'cart-info';
    cartInfoDiv.style.textAlign = 'center';
    cartInfoDiv.style.marginTop = '10px';
    document.querySelector('header').appendChild(cartInfoDiv);
    updateCartCount();

    // Set up event listeners
    setupAddToCartButtons();
    setupContactFormValidation();
    setupSmoothScrolling();
});

addToCartButtons.forEach(button => {
    button.addEventListener('click', () => {
        cartCount++;
        updateCartCount();
        alert('Item added to cart!');
    });
});# zomato-clone-websites
