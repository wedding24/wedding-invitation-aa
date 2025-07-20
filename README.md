<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Приглашение на нашу свадьбу</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Montserrat:wght@300;400&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Montserrat', sans-serif;
            background: #fff9f9;
            color: #555;
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .heart {
            position: fixed;
            font-size: 20px;
            color: #ff6b81;
            animation: float 5s ease-in-out infinite;
            z-index: -1;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
        }
        
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 40px 20px;
            text-align: center;
        }
        
        h1 {
            font-family: 'Playfair Display', serif;
            color: #d23669;
            font-size: 2.8rem;
            margin-bottom: 10px;
            animation: fadeIn 2s;
        }
        
        .date {
            font-size: 1.5rem;
            margin: 20px 0;
            color: #ff6b81;
            animation: fadeIn 2s 0.5s both;
        }
        
        .message {
            font-size: 1.1rem;
            margin: 30px 0;
            animation: fadeIn 2s 1s both;
        }
        
        .names {
            font-size: 3rem;
            font-family: 'Playfair Display', serif;
            color: #d23669;
            margin: 40px 0;
            position: relative;
            display: inline-block;
            animation: fadeIn 2s 1.5s both;
        }
        
        .names:after {
            content: "";
            position: absolute;
            width: 100%;
            height: 2px;
            background: linear-gradient(to right, transparent, #ff6b81, transparent);
            bottom: -10px;
            left: 0;
        }
        
        .btn {
            display: inline-block;
            background: #ff6b81;
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 1.1rem;
            margin-top: 30px;
            transition: all 0.3s;
            animation: fadeIn 2s 2s both;
            box-shadow: 0 4px 15px rgba(255,107,129,0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255,107,129,0.4);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        footer {
            margin-top: 60px;
            font-size: 0.9rem;
            color: #aaa;
            animation: fadeIn 2s 2.5s both;
        }
    </style>
</head>
<body>
    <!-- Плавающие сердечки -->
    <div id="hearts-container"></div>
    
    <div class="container">
        <h1>Мы женимся!</h1>
        
        <div class="date">15 августа 2024 года</div>
        
        <div class="message">
            Дорогие друзья и родные,<br>
            Мы хотим разделить с вами самый важный день в нашей жизни.
        </div>
        
        <div class="names">
            Анна<br> 
            <span style="font-size: 1.5rem;">и</span><br>
            Иван
        </div>
        
        <div class="message">
            Ждём вас в ресторане "Лазурный"<br>
            Начало в 16:00
        </div>
        
        <a href="#rsvp" class="btn">Подтвердить присутствие</a>
        
        <footer>
            Ваше присутствие — самый ценный подарок для нас
        </footer>
    </div>

    <script>
        // Создаем плавающие сердечки
        function createHearts() {
            const container = document.getElementById('hearts-container');
            const heartCount = 20;
            
            for (let i = 0; i < heartCount; i++) {
                const heart = document.createElement('div');
                heart.innerHTML = '❤';
                heart.classList.add('heart');
                
                // Случайная позиция
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.top = Math.random() * 100 + 'vh';
                
                // Случайная задержка анимации
                heart.style.animationDelay = Math.random() * 5 + 's';
                
                container.appendChild(heart);
            }
        }
        
        // Показываем форму RSVP при клике на кнопку
        document.querySelector('.btn').addEventListener('click', function(e) {
            e.preventDefault();
            alert('Форма подтверждения будет здесь!\nМожно подключить Google Forms или другую службу.');
        });
        
        // Запускаем создание сердечек при загрузке
        window.onload = createHearts;
    </script>
</body>
</html>
