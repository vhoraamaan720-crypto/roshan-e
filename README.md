<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roshan Courier Service - Admin Login</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        .login-container {
            background: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 400px;
            text-align: center;
        }
        .logo {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
        }
        .logo h1 {
            font-size: 2.2em;
            margin-bottom: 10px;
        }
        .logo p {
            font-size: 1.1em;
            opacity: 0.9;
        }
        h2 {
            color: #333;
            margin-bottom: 30px;
            font-size: 1.8em;
        }
        .input-group {
            margin-bottom: 20px;
            position: relative;
        }
        input {
            width: 100%;
            padding: 18px 20px;
            border: 2px solid #e1e5e9;
            border-radius: 12px;
            font-size: 1.1em;
            transition: all 0.3s ease;
            background: #f8f9fa;
        }
        input:focus {
            outline: none;
            border-color: #667eea;
            background: white;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }
        .login-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
        }
        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }
        .error {
            color: #ff4757;
            margin-top: 15px;
            display: none;
        }
        @media (max-width: 480px) {
            .login-container {
                padding: 30px 20px;
                margin: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="login-container">
        <div class="logo">
            <h1>🌟 ROSHAN COURIER</h1>
            <p>Khambhat - Gujarat</p>
        </div>
        <h2>🔐 Admin Login</h2>
        <form id="loginForm">
            <div class="input-group">
                <input type="text" id="username" placeholder="👤 Username" required>
            </div>
            <div class="input-group">
                <input type="password" id="password" placeholder="🔒 Password" required>
            </div>
            <button type="submit" class="login-btn">🚀 Login</button>
            <div id="errorMsg" class="error">❌ Invalid Username or Password!</div>
        </form>
    </div>

    <script>
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorMsg = document.getElementById('errorMsg');
            
            // ONE CREDENTIAL ONLY: admin / roshan123
            if (username === 'admin' && password === 'roshan123') {
                localStorage.setItem('isAdmin', 'true');
                window.location.href = 'main.html';
            } else {
                errorMsg.style.display = 'block';
                setTimeout(() => errorMsg.style.display = 'none', 3000);
            }
        });
    </script>
</body>
</html>
