# shadow-sketches
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shadow Sketches</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #111;
            color: white;
            text-align: center;
        }
        header {
            padding: 40px 20px;
            background: #000;
            box-shadow: 0 0 20px rgba(255,255,255,0.1);
        }
        h1 {
            font-size: 48px;
            letter-spacing: 2px;
        }
        .welcome {
            margin-top: 10px;
            font-size: 22px;
            color: #ccc;
        }

        /* Slider Section */
        .sample-section {
            padding: 40px 10px;
        }
        .slider {
            position: relative;
            max-width: 800px;
            margin: 20px auto;
            overflow: hidden;
            border-radius: 10px;
        }
        .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }
        .slides img {
            width: 100%;
            border-radius: 10px;
        }
        .prev, .next {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(255,255,255,0.7);
            color: #000;
            padding: 10px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: bold;
        }
        .prev { left: 10px; }
        .next { right: 10px; }

        /* Order Buttons */
        .order-buttons {
            margin: 40px 0;
        }
        .order-buttons a {
            display: block;
            margin: 10px auto;
            padding: 15px 20px;
            width: 250px;
            background: #fff;
            color: #000;
            text-decoration: none;
            font-size: 18px;
            border-radius: 10px;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        .order-buttons a:hover {
            background: #ffcc00;
            color: #000;
            transform: scale(1.05);
        }

        footer {
            padding: 20px;
            background: #000;
            color: #777;
            margin-top: 40px;
        }

        @media (max-width: 600px) {
            .order-buttons a {
                width: 80%;
            }
        }
    </style>
</head>
<body>

<header>
    <h1>Shadow Sketches</h1>
    <p class="welcome">Welcome to the Official Sketch Ordering Website</p>
</header>

<section class="sample-section">
    <h2>Sketch Samples</h2>
    <div class="slider">
        <div class="slides">
            <img src="sample1.jpg" alt="Sketch 1">
            <img src="sample2.jpg" alt="Sketch 2">
            <img src="sample3.jpg" alt="Sketch 3">
        </div>
        <span class="prev">&#10094;</span>
        <span class="next">&#10095;</span>
    </div>
</section>

<section class="order-buttons">
    <a href="https://wa.me/919876543210" target="_blank">Order on WhatsApp</a>
    <a href="https://www.snapchat.com/add/yourusername" target="_blank">Order on Snapchat</a>
</section>

<footer>
    © 2025 Shadow Sketches — All Rights Reserved
</footer>

<script>
    const slides = document.querySelector('.slides');
    const images = document.querySelectorAll('.slides img');
    const prev = document.querySelector('.prev');
    const next = document.querySelector('.next');

    let counter = 0;

    function showSlide() {
        slides.style.transform = 'translateX(' + (-counter * 100) + '%)';
    }

    next.addEventListener('click', () => {
        counter = (counter + 1) % images.length;
        showSlide();
    });

    prev.addEventListener('click', () => {
        counter = (counter - 1 + images.length) % images.length;
        showSlide();
    });

    // Auto-slide every 3 seconds
    setInterval(() => {
        counter = (counter + 1) % images.length;
        showSlide();
    }, 3000);
</script>

</body>
</html>
