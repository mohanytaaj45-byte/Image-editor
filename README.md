<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TradeRiser - Live Trading Platform</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', sans-serif;
        }

        body {
            background-color: #f4f7fa;
            color: #333;
        }

        /* Navigation Bar */
        .navbar {
            background-color: #1a3c6e;
            padding: 15px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            color: #fff;
            font-size: 24px;
            font-weight: bold;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        .nav-links li a {
            color: #fff;
            text-decoration: none;
            font-size: 16px;
            padding: 10px;
            border-radius: 5px;
        }

        .nav-links li a:hover, .nav-links li a.active {
            background-color: #00cc88;
            color: #fff;
        }

        .hamburger {
            display: none;
            color: #fff;
            font-size: 24px;
            cursor: pointer;
        }

        /* Tab Content */
        .tab-content {
            display: none;
            padding: 50px 20px;
        }

        .tab-content.active {
            display: block;
        }

        /* Hero Section */
        .hero-section {
            background: linear-gradient(to right, #1a3c6e, #00cc88);
            color: #fff;
            text-align: center;
            padding: 100px 20px;
        }

        .hero-content h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .hero-content p {
            font-size: 18px;
            margin-bottom: 30px;
        }

        .cta-button {
            background-color: #fff;
            color: #1a3c6e;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
        }

        .cta-button:hover {
            background-color: #00cc88;
            color: #fff;
        }

        /* News Section */
        .news-section, .market-section, .chat-section, .about-section, .contact-section {
            text-align: center;
        }

        .news-container, .market-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .news-card, .market-card {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: left;
        }

        .news-card h3, .market-card h3 {
            color: #1a3c6e;
            margin-bottom: 10px;
        }

        .news-card img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        .price, .change {
            font-weight: bold;
        }

        .change.positive {
            color: #00cc88;
        }

        .change.negative {
            color: #ff4d4d;
        }

        /* News Submission Form */
        .news-form {
            max-width: 600px;
            margin: 20px auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .news-form input, .news-form textarea {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .news-form button {
            background-color: #1a3c6e;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .news-form button:hover {
            background-color: #00cc88;
        }

        /* Chat Section */
        .chat-container {
            max-width: 600px;
            margin: 0 auto;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .chat-box {
            height: 300px;
            overflow-y: auto;
            padding: 20px;
            border-bottom: 1px solid #ddd;
        }

        .chat-message {
            margin-bottom: 10px;
            padding: 10px;
            background-color: #f1f1f1;
            border-radius: 5px;
        }

        .chat-input {
            display: flex;
            padding: 10px;
        }

        .chat-input input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .chat-input button {
            background-color: #1a3c6e;
            color: #fff;
            border: none;
            padding: 10px 20px;
            margin-left: 10px;
            border-radius: 5px;
            cursor: pointer;
        }

        .chat-input button:hover {
            background-color: #00cc88;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-form input, .contact-form textarea {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .contact-form button {
            background-color: #1a3c6e;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .contact-form button:hover {
            background-color: #00cc88;
        }

        /* Footer */
        footer {
            background-color: #1a3c6e;
            color: #fff;
            text-align: center;
            padding: 20px;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 60px;
                right: 20px;
                background-color: #1a3c6e;
                padding: 20px;
                border-radius: 5px;
            }

            .nav-links.active {
                display: flex;
            }

            .hamburger {
                display: block;
            }

            .hero-content h1 {
                font-size: 32px;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar">
        <div class="logo">TradeRiser</div>
        <ul class="nav-links">
            <li><a href="#home" class="tab-link active" onclick="openTab('home')">Home</a></li>
            <li><a href="#live-news" class="tab-link" onclick="openTab('live-news')">Live News</a></li>
            <li><a href="#market-data" class="tab-link" onclick="openTab('market-data')">Market Data</a></li>
            <li><a href="#chat" class="tab-link" onclick="openTab('chat')">Chat</a></li>
            <li><a href="#about" class="tab-link" onclick="openTab('about')">About</a></li>
            <li><a href="#contact" class="tab-link" onclick="openTab('contact')">Contact</a></li>
        </ul>
        <div class="hamburger" onclick="toggleMenu()">☰</div>
    </nav>

    <!-- Home Section -->
    <section id="home" class="hero-section tab-content active">
        <div class="hero-content">
            <h1>Welcome to TradeRiser</h1>
            <p>Get real-time trading insights, live news, and community discussions.</p>
            <a href="#live-news" class="cta-button" onclick="openTab('live-news')">Explore Live Updates</a>
        </div>
    </section>

    <!-- Live News Section -->
    <section id="live-news" class="news-section tab-content">
        <h2>Live Market News</h2>
        <form class="news-form" onsubmit="addNews(event)">
            <input type="text" id="news-title" placeholder="News Title" required>
            <textarea id="news-description" placeholder="News Description" required></textarea>
            <input type="file" id="news-image" accept="image/*">
            <button type="submit">Add News</button>
        </form>
        <div class="news-container" id="news-feed">
            <!-- News will be dynamically populated via JavaScript/API -->
            <div class="news-card">
                <h3>Market Update</h3>
                <p>Loading news...</p>
            </div>
        </div>
    </section>

    <!-- Market Data Section -->
    <section id="market-data" class="market-section tab-content">
        <h2>Real-Time Market Data</h2>
        <div class="market-container" id="market-feed">
            <!-- Stock data will be dynamically populated via JavaScript/API -->
            <div class="market-card">
                <h3>NIFTY 50</h3>
                <p>Price: <span class="price">Loading...</span></p>
                <p>Change: <span class="change">Loading...</span></p>
            </div>
        </div>
    </section>

    <!-- Chat Section -->
    <section id="chat" class="chat-section tab-content">
        <h2>Community Chat</h2>
        <div class="chat-container">
            <div class="chat-box" id="chat-box">
                <!-- Chat messages will be dynamically populated -->
                <div class="chat-message">Welcome to the trading community!</div>
            </div>
            <div class="chat-input">
                <input type="text" id="chat-input" placeholder="Type your message...">
                <button onclick="sendMessage()">Send</button>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section tab-content">
        <h2>About Us</h2>
        <p>TradeRiser is your go-to platform for real-time trading insights, market news, and community discussions. Join thousands of traders to stay ahead in the market.</p>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section tab-content">
        <h2>Contact Us</h2>
        <form class="contact-form">
            <input type="text" placeholder="Name" required>
            <input type="email" placeholder="Email" required>
            <textarea placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 TradeRiser. All rights reserved.</p>
    </footer>

    <script>
        // Hamburger Menu Toggle
        function toggleMenu() {
            document.querySelector('.nav-links').classList.toggle('active');
        }
        document.querySelector('.hamburger').addEventListener('click', toggleMenu);

        // Tab Functionality
        function openTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.remove('active');
            });
            document.querySelectorAll('.tab-link').forEach(link => {
                link.classList.remove('active');
            });
            document.getElementById(tabId).classList.add('active');
            document.querySelector(`.tab-link[href="#${tabId}"]`).classList.add('active');
        }

        // Placeholder for Live News API
        function fetchNews() {
            const newsFeed = document.getElementById('news-feed');
            newsFeed.innerHTML = ''; // Clear existing content
            // Example API call (replace with real API, e.g., NewsAPI.org)
            /*
            fetch('https://newsapi.org/v2/top-headlines?category=business&apiKey=YOUR_API_KEY')
                .then(response => response.json())
                .then(data => {
                    data.articles.forEach(article => {
                        const newsCard = document.createElement('div');
                        newsCard.classList.add('news-card');
                        newsCard.innerHTML = `
                            <h3>${article.title}</h3>
                            ${article.urlToImage ? `<img src="${article.urlToImage}" alt="News Image">` : ''}
                            <p>${article.description}</p>
                            <a href="${article.url}" target="_blank">Read More</a>
                        `;
                        newsFeed.appendChild(newsCard);
                    });
                });
            */
            // Placeholder data
            const placeholderNews = [
                { title: 'Market Surges 2%', description: 'NIFTY 50 hits record high.' },
                { title: 'Global Markets Update', description: 'US stocks rally after Fed announcement.' }
            ];
            placeholderNews.forEach(news => {
                const newsCard = document.createElement('div');
                newsCard.classList.add('news-card');
                newsCard.innerHTML = `<h3>${news.title}</h3><p>${news.description}</p>`;
                newsFeed.appendChild(newsCard);
            });
        }

        // Add News with Image Functionality
        function addNews(event) {
            event.preventDefault();
            const newsTitle = document.getElementById('news-title').value.trim();
            const newsDescription = document.getElementById('news-description').value.trim();
            const newsImage = document.getElementById('news-image').files[0];
            const newsFeed = document.getElementById('news-feed');

            if (newsTitle && newsDescription) {
                const newsCard = document.createElement('div');
                newsCard.classList.add('news-card');

                // Handle image if uploaded
                let imageHtml = '';
                if (newsImage) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        newsCard.innerHTML = `
                            <h3>${newsTitle}</h3>
                            <img src="${e.target.result}" alt="News Image">
                            <p>${newsDescription}</p>
                        `;
                        newsFeed.prepend(newsCard); // Add new news at the top
                    };
                    reader.readAsDataURL(newsImage);
                } else {
                    newsCard.innerHTML = `
                        <h3>${newsTitle}</h3>
                        <p>${newsDescription}</p>
                    `;
                    newsFeed.prepend(newsCard); // Add new news at the top
                }

                // Clear form
                document.getElementById('news-title').value = '';
                document.getElementById('news-description').value = '';
                document.getElementById('news-image').value = '';

                // For persistent storage, send to backend API here
                /*
                const formData = new FormData();
                formData.append('title', newsTitle);
                formData.append('description', newsDescription);
                if (newsImage) formData.append('image', newsImage);
                fetch('your-backend-api/news', {
                    method: 'POST',
                    body: formData
                });
                */
            }
        }

        // Placeholder for Live Market Data API
        function fetchMarketData() {
            const marketFeed = document.getElementById('market-feed');
            marketFeed.innerHTML = ''; // Clear existing content
            // Example API call (replace with real API, e.g., Alpha Vantage or Yahoo Finance)
            /*
            fetch('https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=RELIANCE.BSE&interval=5min&apikey=YOUR_API_KEY')
                .then(response => response.json())
                .then(data => {
                    // Parse and display stock data
                });
            */
            // Placeholder data
            const placeholderStocks = [
                { symbol: 'NIFTY 50', price: 24300.50, change: 1.5 },
                { symbol: 'RELIANCE', price: 2900.75, change: -0.8 }
            ];
            placeholderStocks.forEach(stock => {
                const marketCard = document.createElement('div');
                marketCard.classList.add('market-card');
                marketCard.innerHTML = `
                    <h3>${stock.symbol}</h3>
                    <p>Price: <span class="price">₹${stock.price}</span></p>
                    <p>Change: <span class="change ${stock.change >= 0 ? 'positive' : 'negative'}">${stock.change}%</span></p>
                `;
                marketFeed.appendChild(marketCard);
            });
        }

        // Chat Functionality (Frontend-only, backend needed for real-time)
        function sendMessage() {
            const chatInput = document.getElementById('chat-input');
            const chatBox = document.getElementById('chat-box');
            const message = chatInput.value.trim();
            if (message) {
                const messageDiv = document.createElement('div');
                messageDiv.classList.add('chat-message');
                messageDiv.textContent = `User: ${message}`;
                chatBox.appendChild(messageDiv);
                chatBox.scrollTop = chatBox.scrollHeight; // Scroll to bottom
                chatInput.value = '';
                // For real-time chat, integrate WebSocket or backend API here
                /*
                const socket = new WebSocket('ws://your-backend-server');
                socket.send(JSON.stringify({ message }));
                socket.onmessage = (event) => {
                    const newMessage = document.createElement('div');
                    newMessage.classList.add('chat-message');
                    newMessage.textContent = event.data;
                    chatBox.appendChild(newMessage);
                };
                */
            }
        }

        // Fetch data on page load
        document.addEventListener('DOMContentLoaded', () => {
            fetchNews();
            fetchMarketData();
            // Refresh data every 60 seconds
            setInterval(fetchNews, 60000);
            setInterval(fetchMarketData, 60000);
        });
    </script>
</body>
</html>
