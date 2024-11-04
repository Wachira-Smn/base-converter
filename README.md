# <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website with Theme Switcher</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Global Styles */
        body {
            background-image: url(//chameliom.avif);
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
           position: relative; /* For absolute positioning of dropdown */
            transition: background-color 0.3s, color 0.3s; /* Transition for theme change */
            padding-bottom: 60px; /* Add padding for the social icons */
        }

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: #333;
            color: #3f0606;
        }

        /* Navbar Styles */
        .navbar {
            display: flex;
            justify-content: space-around; /* Evenly space the items */
            align-items: center;
            background-color: #333;
            padding: 15px;
        }

        .navbar a {
            color: white;
            text-decoration: none;
            padding: 10px 20px;
            font-size: 18px;
            transition: background-color 0.3s ease;
        }

        .navbar a:hover {
            background-color: #575757;
            border-radius: 5px;
        }

        .navbar i {
            margin-right: 5px; /* Space between icon and text */
        }

        /* Welcoming Text Styles */
        .welcome {
            text-align: center;
            margin: 40px 0;
            font-size: 24px;
            color: #333;
        }

        /* Settings Section */
        .settings {
            display: none; /* Hidden by default */
            padding: 20px;
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
            margin-top: 20px;
        }

        .theme-switcher {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .theme-switcher input[type="checkbox"] {
            appearance: none;
            width: 50px;
            height: 25px;
            background: #ccc;
            border-radius: 15px;
            position: relative;
            outline: none;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .theme-switcher input[type="checkbox"]:checked {
            background: #4CAF50;
        }

        .theme-switcher input[type="checkbox"]:checked:before {
            transform: translateX(25px);
        }

        .theme-switcher input[type="checkbox"]:before {
            content: "";
            position: absolute;
            width: 23px;
            height: 23px;
            background: white;
            border-radius: 50%;
            transition: transform 0.3s ease;
        }

        /* Content Container for Games */
        .content {
            display: none; /* Hidden by default */
            padding: 20px;
            text-align: left;
            margin-top: 20px; /* Space below the navbar */
        }

        /* Game List Styles */
        .game-list {
            list-style-type: none;
            padding: 0;
        }

        .game-list li {
            background-color: #e0e0e0;
            margin: 10px 0;
            padding: 10px;
            border-radius: 5px;
            transition: background-color 0.3s;
            display: flex;
            align-items: center; /* Center items vertically */
        }

        .game-list li:hover {
            background-color: #d0d0d0; /* Change background on hover */
        }

        .game-list i {
            margin-right: 10px; /* Space between icon and text */
        }

        /* Social Media Icons Styles */
        .social-media {
            position: fixed;
            bottom: 0; /* Fixed to the bottom of the screen */
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            padding: 10px 0;
            background-color: #333;
        }

        .social-media a {
            color: white;
            text-decoration: none;
            padding: 10px;
            font-size: 24px; /* Icon size */
            transition: color 0.3s ease;
        }

        .social-media a:hover {
            color: #1e90ff; /* Change color on hover */
        }
    </style>
</head>
<body>

<!-- Navigation Bar -->
<nav class="navbar">
    <a href="#home" onclick="showHome()"><i class="fas fa-home"></i>Home</a>
    <a href="#games" onclick="showGames()"><i class="fas fa-gamepad"></i>Games</a>
    <a href="#settings" onclick="showSettings()"><i class="fas fa-cog"></i>Settings</a>
    <a href="rateus.html" onclick="showRateus()"><i class="fas fa-star"></i>rate us</a>
</nav>

<!-- Welcoming Text -->
<div class="welcome" id="homeContent">
    <h1>Welcome to Our Gaming Website!</h1>
    <p>Your adventure starts here. Explore our games and enjoy your time!</p>
</div>

<!-- Settings Section -->
<div class="settings" id="settingsContent">
    <h2>Settings</h2>
    <div class="theme-switcher">
        <label for="themeToggle">Dark Mode:</label>
        <input type="checkbox" id="themeToggle" onchange="toggleTheme()">
    </div>
</div>

<!-- Content Container for Games -->
<div class="content" id="gamesContent">
    <h2>Explore Our Games</h2>
    <ul class="game-list">
        <li>
            <a href="snake.html" target="_blank"><i class="fas fa-dragon"></i>Snake Game </a>
          </li>
        <li>
            <a href="sudoku.html" target="_blank"> <i class="fas fa-puzzle-piece"></i>SUDOKU</a>
            </li>
        <li><i class="fas fa-gamepad"></i>Game 3</li>
    </ul>
</div>

<!-- JavaScript to handle content switching -->
<script>
    // Function to show home content
    function showHome() {
        document.getElementById('homeContent').style.display = 'block';
        document.getElementById('settingsContent').style.display = 'none';
        document.getElementById('gamesContent').style.display = 'none';
    }

    // Function to show games content
    function showGames() {
        document.getElementById('homeContent').style.display = 'none';
        document.getElementById('settingsContent').style.display = 'none';
        document.getElementById('gamesContent').style.display = 'block';
    }

    // Function to show settings content
    function showSettings() {
        document.getElementById('homeContent').style.display = 'none';
        document.getElementById('settingsContent').style.display = 'block';
        document.getElementById('gamesContent').style.display = 'none';
    }

    // Function to toggle the theme
    function toggleTheme() {
        document.body.classList.toggle('dark-mode');
    }

    // Show home content by default
    showHome();
</script>

<!-- Social Media Icons -->
<div class="social-media">
    <a href="https://facebook.com" target="_blank"><i class="fab fa-facebook-f"></i></a>
    <a href="https://twitter.com" target="_blank"><i class="fab fa-twitter"></i></a>
    <a href="https://wa.me/qr/UJFE2AS37BLNF1" target="_blank"><i class="fab fa-whatsapp"></i></a>
</div>

</body>
</html>project-1
