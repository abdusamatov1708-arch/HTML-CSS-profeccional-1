# HTML-CSS-profeccional-1
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animatsiyalar va Spinner</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <!-- 1. Transition bilan hover effektli tugma -->
        <div class="card">
            <h2>Transition Tugma</h2>
            <p>Silliq rang va o'lcham o'zgarishi.</p>
            <button class="animated-btn">Bosing</button>
        </div>

        <!-- 2. @keyframes bilan cheksiz aylanadigon spinner -->
        <div class="card">
            <h2>Yuklanish Spinner</h2>
            <p>Aylanuvchi yuklanish belgisi.</p>
            <div class="spinner-container">
                <div class="spinner"></div>
            </div>
        </div>

        <!-- 3. Kartaga hover ko'tarilish effekti -->
        <div class="card hover-card">
            <h2>Karta Effekti</h2>
            <p>Kursorni ustiga olib boring va ko'tarilishini ko'ring.</p>
        </div>
    </div>

</body>
</html>

CSS
/* Umumiy sozlamalar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f0f2f5;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

.container {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    justify-content: center;
    padding: 20px;
}

/* Kartaning asosiy ko'rinishi */
.card {
    background-color: #ffffff;
    padding: 30px;
    border-radius: 16px;
    width: 280px;
    text-align: center;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), 
                box-shadow 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}

.card h2 {
    font-size: 20px;
    color: #333333;
    margin-bottom: 10px;
}

.card p {
    font-size: 14px;
    color: #666666;
    margin-bottom: 20px;
}

/* 1. Transition bilan hover effektli tugma */
.animated-btn {
    background-color: #4f46e5;
    color: #ffffff;
    border: none;
    padding: 12px 24px;
    font-size: 16px;
    font-weight: 600;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease, 
                transform 0.3s ease, 
                box-shadow 0.3s ease;
}

.animated-btn:hover {
    background-color: #4338ca;
    transform: scale(1.08);
    box-shadow: 0 8px 20px rgba(79, 70, 229, 0.4);
}

.animated-btn:active {
    transform: scale(1.02);
}

/* 2. @keyframes bilan cheksiz aylanadigon spinner */
.spinner-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50px;
}

.spinner {
    width: 40px;
    height: 40px;
    border: 4px solid #e5e7eb;
    border-top: 4px solid #4f46e5;
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}

/* 3. Kartaga hover ko'tarilish effekti (translateY + box-shadow) */
.hover-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 20px 30px rgba(0, 0, 0, 0.12);
}
