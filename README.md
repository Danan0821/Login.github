<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loading Animation</title>
    <style>
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(45deg, #3498db, #2ecc71);
        }

        #loading-container {
            text-align: center;
            color: #fff;
            display: none;
        }

        #loading-icon {
            width: 50px;
            height: 50px;
            border: 4px solid rgba(255, 255, 255, 0.3);
            border-top: 4px solid #fff;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        #login-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
            text-align: center;
        }

        h1 {
            color: #333;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 10px;
            background: #3498db;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background 0.3s ease;
        }

        button:hover {
            background: #2980b9;
        }
    </style>
</head>
<body>
    <div id="loading-container">
        <div id="loading-icon"></div>
        <p>Loading...</p>
    </div>

    <div id="login-container">
        <h1>Login</h1>
        <form id="login-form">
            <input type="text" id="username" placeholder="Username" required>
            <input type="password" id="password" placeholder="Password" required>
            <button type="button" onclick="authenticate()">Login</button>
        </form>
    </div>

    <script>
        function authenticate() {
            // Simulate loading by hiding login container and showing loading container
            document.getElementById('login-container').style.display = 'none';
            document.getElementById('loading-container').style.display = 'block';

            // Simulate authentication delay (you can replace this with actual authentication logic)
            setTimeout(function () {
                var username = document.getElementById('username').value;
                var password = document.getElementById('password').value;

                // Check if username and password match the expected values
                if (username === '123' && password === '123') {
                    // Redirect to the next page or perform other actions
                    alert('Login successful! Redirecting...');
                    window.location.href = 'profile.html';  // Replace with the actual page URL
                } else {
                    // Display an error message
                    document.getElementById('loading-container').style.display = 'none';
                    document.getElementById('login-container').style.display = 'block';
                    alert('Invalid username or password');
                }
            }, 2000); // Simulate 2 seconds delay
        }
    </script>
</body>
</html>
