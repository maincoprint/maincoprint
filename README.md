<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
<body>
  <header>
  <img src="logo.png" alt="Main & Co. Logo" style="width: 250px; height: auto; margin-bottom: 40px; display: block; margin-left: auto; margin-right: auto;">
  <h1>Main & Co. Custom Printing and Design</h1>
  <p>High-Quality Custom Printing for Every Project</p>
</header>

  <nav>
    <a href="#services">Services</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>

  <section id="services" class="services">
    <h2>Our Services</h2>
    <ul>
      <li>Business Cards, Door Hangers, Flyers & Brochures</li>
      <li>Banners, Posters, and Yard Signs</li>
      <li>Custom Apparel (T-Shirts, Hoodies, etc.)</li>
      <li>Stickers, Labels, and Packaging</li>
      <li>Custom one off projects</li>
      <li>Step & Repeat Banners</li>
      <li>Church & Event Tradeshow Materials</li>
      <li>Contact Us Below To Make Your Project Come To Life</li>
    </ul>
    <a href="#contact" class="cta-button">Get a Quote</a>
  </section>

  <section id="about" class="services">
    <h2>About Us</h2>
    <p>At Main & Co., we’re a passionate and dependable print shop committed to helping your business, ministry, or personal brand stand out. Whether you're ordering in bulk or need a single custom piece, we deliver with unmatched quality, speed, and service you can trust.</p>
  </section>

  <section id="contact" class="contact">
    <h2>Contact Us</h2>
    <p>Ready to place your order or have questions? Fill out the form below and we'll get in touch shortly.</p>
    <form name="submit-to-google-sheet">
      <input type="text" name="name" placeholder="Your Name" required>
      <input type="email" name="email" placeholder="Your Email" required>
      <input type="text" name="phone" placeholder="Your Phone Number">
      <textarea name="message" placeholder="Tell us what you need printed..." rows="5" required></textarea>
      <button type="submit">Submit Request</button>
      <p id="form-message"></p>
    </form>
    <script>
      const scriptURL = 'https://script.google.com/macros/s/AKfycbzYFupJtyLkSdKg3jm0D-XuIqHHs8vJ_ERsFh9i3JpPAbxGb6vq2OW9KQ1DL4-b0gJ9/exec';
      const form = document.forms['submit-to-google-sheet'];
      const message = document.getElementById('form-message');

      form.addEventListener('submit', e => {
        e.preventDefault();
        fetch(scriptURL, { method: 'POST', body: new FormData(form) })
          .then(response => {
            message.style.display = 'block';
            message.style.color = 'green';
            message.textContent = '✅ Thank you! Your request has been submitted.';
            form.reset();
          })
          .catch(error => {
            message.style.display = 'block';
            message.style.color = 'red';
            message.textContent = '⚠️ Something went wrong. Please try again.';
          });
      });
    </script>
  </section>

  <footer>
    <p>&copy; 2024 Main & Co. Custom Printing and Design. All rights reserved.</p>
  </footer>
</body>
</html>
