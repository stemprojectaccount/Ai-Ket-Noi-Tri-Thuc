<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trang Web Trò Chơi</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
            color: #fff;
        }
        
        .container {
            max-width: 1200px;
            width: 100%;
        }
        
        header {
            text-align: center;
            margin-bottom: 50px;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 15px;
            background: linear-gradient(90deg, #ff6b6b, #ffd166, #06d6a0, #118ab2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }
        
        .tagline {
            font-size: 1.2rem;
            color: #b8c1ec;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .game-gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .game-card {
            flex: 1;
            min-width: 300px;
            max-width: 350px;
            background: linear-gradient(145deg, #1e2a47, #2d3b5e);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255,255,255,0.1);
            cursor: pointer;
        }
        
        .game-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.4);
        }
        
        .game-image {
            width: 100%;
            height: 220px;
            overflow: hidden;
            position: relative;
        }
        
        .game-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .game-card:hover .game-image img {
            transform: scale(1.08);
        }
        
        .game-info {
            padding: 20px;
        }
        
        .game-info h3 {
            color: #ffd166;
            margin-bottom: 10px;
            font-size: 1.5rem;
        }
        
        .game-info p {
            color: #b8c1ec;
            line-height: 1.6;
            margin-bottom: 15px;
        }
        
        .play-btn {
            display: inline-block;
            background: linear-gradient(90deg, #06d6a0, #118ab2);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(6, 214, 160, 0.3);
        }
        
        .play-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(6, 214, 160, 0.4);
        }
        
        .featured-section {
            background: rgba(255, 255, 255, 0.05);
            padding: 40px;
            border-radius: 15px;
            margin-top: 30px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .featured-section h2 {
            color: #ffd166;
            margin-bottom: 20px;
            font-size: 2rem;
        }
        
        .featured-section p {
            color: #b8c1ec;
            max-width: 700px;
            margin: 0 auto 25px;
            line-height: 1.6;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(90deg, #ff6b6b, #ff8e8e);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.3);
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.4);
        }
        
        footer {
            margin-top: 50px;
            text-align: center;
            color: #b8c1ec;
            font-size: 0.9rem;
            padding: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            width: 100%;
        }
        
        @media (max-width: 768px) {
            .game-gallery {
                flex-direction: column;
                align-items: center;
            }
            
            .game-card {
                max-width: 100%;
            }
            
            h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>GAME HUB</h1>
            <p class="tagline">Khám phá thế giới trò chơi đầy màu sắc và thú vị</p>
        </header>
        
        <div class="game-gallery">
            <!-- Card 1 - Click to open Vũ Trụ Tri Thức -->
            <div class="game-card" id="card1">
                <div class="game-image">
                    <img src="https://i.postimg.cc/4Nbrm7hC/Thi-t-k-ch-a-c-t-n-5.png" alt="Vũ Trụ Tri Thức">
                </div>
                <div class="game-info">
                    <h3>Vũ Trụ Tri Thức</h3>
                    <p>Khám phá vũ trụ tri thức với những bài học thú vị và kiến thức bổ ích.</p>
                    <div class="play-btn">Khám Phá Ngay</div>
                </div>
            </div>
            
            <!-- Card 2 - Click to open VNDiceGame -->
            <div class="game-card" id="card2">
                <div class="game-image">
                    <img src="https://i.postimg.cc/2yHSDcmp/Thi-t-k-ch-a-c-t-n-4.png" alt="VN Dice Game">
                </div>
                <div class="game-info">
                    <h3>VN Dice Game</h3>
                    <p>Thử thách may mắn với trò chơi xúc xắc đầy hấp dẫn và kịch tính.</p>
                    <div class="play-btn">Chơi Ngay</div>
                </div>
            </div>
            
            <!-- Card 3 - Regular play button -->
            <div class="game-card">
                <div class="game-image">
                    <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Trò chơi thể thao">
                </div>
                <div class="game-info">
                    <h3>Đua Xe Tốc Độ</h3>
                    <p>Trải nghiệm cảm giác tốc độ với những siêu xe đua hiện đại nhất.</p>
                    <a href="#" class="play-btn">Chơi Ngay</a>
                </div>
            </div>
        </div>
        
        <div class="featured-section">
            <h2>Trải Nghiệm kiến thức mới qua trò chơi  Mỗi Ngày</h2>
            <p>Tham gia các hoạt động bừa học vừa chơi thôi nào </p>
            <a href="#" class="cta-button"> Cùng học thôi nào </a>
        </div>
    </div>

    <footer>
        <p> </p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Card 1 - Vũ Trụ Tri Thức
            const card1 = document.getElementById('card1');
            card1.addEventListener('click', function() {
                window.open('https://stemprojectaccount.github.io/vu-tru-tri-thuc/', '_blank');
            });
            
            // Card 2 - VNDiceGame
            const card2 = document.getElementById('card2');
            card2.addEventListener('click', function() {
                window.open('https://stemprojectaccount.github.io/VNDiceGame/', '_blank');
            });
            
            // Card 3 - Giữ nguyên hành vi mặc định (nút "Chơi Ngay")
        });
    </script>
</body>
</html>
