<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WISDOM PORTAL - Cyberpunk Gateways</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: 
                radial-gradient(circle at 20% 80%, rgba(120, 0, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 0, 120, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(0, 200, 255, 0.05) 0%, transparent 50%),
                linear-gradient(135deg, #0a0a12 0%, #0f0f1a 50%, #0a0a12 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 40px 20px;
            color: #fff;
            overflow-x: hidden;
            position: relative;
            font-family: 'Rajdhani', 'Orbitron', sans-serif;
        }
        
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                repeating-linear-gradient(
                    0deg,
                    rgba(0, 200, 255, 0.02) 0px,
                    rgba(0, 200, 255, 0.02) 1px,
                    transparent 1px,
                    transparent 3px
                );
            pointer-events: none;
            z-index: 0;
        }
        
        .container {
            max-width: 1400px;
            width: 100%;
            position: relative;
            z-index: 1;
        }
        
        header {
            text-align: center;
            margin-bottom: 70px;
            position: relative;
        }
        
        .cyber-grid {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                linear-gradient(90deg, transparent 99%, rgba(0, 200, 255, 0.05) 99%),
                linear-gradient(0deg, transparent 99%, rgba(0, 200, 255, 0.05) 99%);
            background-size: 40px 40px;
            z-index: -1;
            opacity: 0.3;
        }
        
        /* Tiêu đề tối giản với hiệu ứng lấp lánh */
        .simple-title {
            font-size: 4rem;
            margin-bottom: 20px;
            font-weight: 700;
            position: relative;
            font-family: 'Orbitron', monospace;
            color: #e0f7ff;
            text-shadow: 
                0 0 5px rgba(0, 200, 255, 0.5),
                0 0 10px rgba(0, 200, 255, 0.3);
            animation: gentleGlow 4s ease-in-out infinite;
            letter-spacing: 2px;
        }
        
        .simple-title::before {
            content: 'WISDOM PORTAL';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent 0%, 
                rgba(0, 255, 204, 0.1) 20%,
                rgba(0, 204, 255, 0.1) 50%,
                rgba(255, 0, 204, 0.1) 80%,
                transparent 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shimmer 6s linear infinite;
            z-index: -1;
        }
        
        .simple-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 204, 0.6), transparent);
            animation: linePulse 3s ease-in-out infinite;
        }
        
        .tagline {
            font-size: 1.3rem;
            color: #a0f0ff;
            max-width: 700px;
            margin: 0 auto;
            text-shadow: 0 0 5px rgba(0, 200, 255, 0.3);
            letter-spacing: 0.5px;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 400;
            line-height: 1.6;
        }
        
        .portal-gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-bottom: 60px;
        }
        
        .portal-card {
            flex: 1;
            min-width: 280px;
            max-width: 320px;
            background: 
                radial-gradient(circle at top left, rgba(0, 255, 204, 0.08) 0%, transparent 50%),
                radial-gradient(circle at bottom right, rgba(255, 0, 204, 0.08) 0%, transparent 50%),
                rgba(15, 20, 40, 0.6);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 
                0 0 15px rgba(0, 200, 255, 0.15),
                inset 0 0 15px rgba(0, 200, 255, 0.05);
            transition: all 0.4s ease;
            border: 1px solid rgba(0, 200, 255, 0.2);
            cursor: pointer;
            position: relative;
            backdrop-filter: blur(5px);
        }
        
        .portal-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #00ffcc, #ff00cc);
            box-shadow: 0 0 8px rgba(0, 255, 204, 0.5);
            z-index: 2;
        }
        
        .portal-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 
                0 0 25px rgba(0, 200, 255, 0.25),
                0 0 40px rgba(255, 0, 204, 0.15),
                inset 0 0 20px rgba(0, 200, 255, 0.1);
            border: 1px solid rgba(0, 255, 204, 0.4);
        }
        
        .portal-frame {
            width: 100%;
            height: 220px;
            overflow: hidden;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            background: rgba(10, 15, 25, 0.7);
        }
        
        .portal-gate {
            width: 160px;
            height: 160px;
            border-radius: 50%;
            background: linear-gradient(135deg, #00ffcc, #00ccff, #ff00cc);
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            box-shadow: 
                0 0 15px rgba(0, 255, 204, 0.5),
                0 0 30px rgba(0, 204, 255, 0.3),
                0 0 45px rgba(255, 0, 204, 0.2);
            animation: portalRotate 15s linear infinite, portalPulse 4s ease-in-out infinite alternate;
        }
        
        .portal-gate::before {
            content: '';
            position: absolute;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: 
                radial-gradient(circle at 30% 30%, rgba(15, 20, 35, 0.9) 0%, rgba(10, 15, 25, 1) 70%);
            z-index: 1;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.7);
        }
        
        .portal-image {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            object-fit: cover;
            position: relative;
            z-index: 2;
            transition: all 0.5s ease;
            filter: brightness(1.05) contrast(1.1);
        }
        
        .portal-card:hover .portal-image {
            transform: scale(1.1);
            filter: brightness(1.2) contrast(1.2);
        }
        
        .portal-info {
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .portal-info h3 {
            color: #00ffcc;
            margin-bottom: 12px;
            font-size: 1.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
            text-shadow: 0 0 8px rgba(0, 255, 204, 0.5);
            font-family: 'Orbitron', monospace;
            position: relative;
        }
        
        .portal-info h3::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 1px;
            background: linear-gradient(90deg, transparent, #00ffcc, transparent);
            box-shadow: 0 0 5px rgba(0, 255, 204, 0.5);
        }
        
        .portal-info p {
            color: #b0e0ff;
            line-height: 1.5;
            margin-bottom: 18px;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 400;
            font-size: 1rem;
        }
        
        .enter-btn {
            display: inline-block;
            background: linear-gradient(90deg, #00ffcc, #00ccff);
            color: #0a0a12;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 0 12px rgba(0, 255, 204, 0.4);
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
            position: relative;
            overflow: hidden;
            z-index: 1;
            font-family: 'Rajdhani', sans-serif;
        }
        
        .enter-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: all 0.5s ease;
            z-index: -1;
        }
        
        .enter-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 15px rgba(0, 255, 204, 0.6), 0 0 25px rgba(0, 204, 255, 0.4);
        }
        
        .enter-btn:hover::before {
            left: 100%;
        }
        
        .featured-section {
            background: 
                radial-gradient(circle at top left, rgba(0, 255, 204, 0.08) 0%, transparent 50%),
                radial-gradient(circle at bottom right, rgba(255, 0, 204, 0.08) 0%, transparent 50%),
                rgba(15, 20, 40, 0.6);
            padding: 40px;
            border-radius: 12px;
            margin-top: 40px;
            text-align: center;
            border: 1px solid rgba(0, 200, 255, 0.2);
            box-shadow: 
                0 0 20px rgba(0, 200, 255, 0.15),
                inset 0 0 20px rgba(0, 200, 255, 0.05);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
        }
        
        .featured-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #00ffcc, #ff00cc);
            box-shadow: 0 0 8px rgba(0, 255, 204, 0.5);
        }
        
        .featured-section h2 {
            color: #00ffcc;
            margin-bottom: 20px;
            font-size: 2rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 8px rgba(0, 255, 204, 0.5);
            font-family: 'Orbitron', monospace;
            position: relative;
            animation: gentleGlow 4s ease-in-out infinite;
        }
        
        .featured-section p {
            color: #b0e0ff;
            max-width: 800px;
            margin: 0 auto 25px;
            line-height: 1.6;
            font-size: 1.1rem;
            font-family: 'Rajdhani', sans-serif;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(90deg, #ff00cc, #ff0066);
            color: white;
            padding: 12px 30px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px rgba(255, 0, 204, 0.4);
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
            z-index: 1;
            font-family: 'Rajdhani', sans-serif;
        }
        
        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: all 0.5s ease;
            z-index: -1;
        }
        
        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 20px rgba(255, 0, 204, 0.6), 0 0 30px rgba(255, 0, 102, 0.4);
        }
        
        .cta-button:hover::before {
            left: 100%;
        }
        
        footer {
            margin-top: 60px;
            text-align: center;
            color: #7080ff;
            font-size: 0.9rem;
            padding: 25px;
            border-top: 1px solid rgba(0, 200, 255, 0.2);
            width: 100%;
            text-shadow: 0 0 5px rgba(0, 100, 255, 0.3);
            font-family: 'Rajdhani', sans-serif;
            letter-spacing: 0.5px;
        }
        
        /* Animations đơn giản */
        @keyframes gentleGlow {
            0%, 100% {
                text-shadow: 
                    0 0 5px rgba(0, 200, 255, 0.5),
                    0 0 10px rgba(0, 200, 255, 0.3);
            }
            50% {
                text-shadow: 
                    0 0 8px rgba(0, 200, 255, 0.7),
                    0 0 15px rgba(0, 200, 255, 0.4),
                    0 0 20px rgba(0, 200, 255, 0.2);
            }
        }
        
        @keyframes shimmer {
            0% {
                background-position: -200% 0;
            }
            100% {
                background-position: 200% 0;
            }
        }
        
        @keyframes linePulse {
            0%, 100% {
                opacity: 0.6;
                width: 200px;
            }
            50% {
                opacity: 1;
                width: 250px;
            }
        }
        
        @keyframes portalRotate {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        
        @keyframes portalPulse {
            0% {
                box-shadow: 
                    0 0 15px rgba(0, 255, 204, 0.5),
                    0 0 30px rgba(0, 204, 255, 0.3),
                    0 0 45px rgba(255, 0, 204, 0.2);
            }
            100% {
                box-shadow: 
                    0 0 20px rgba(0, 255, 204, 0.6),
                    0 0 35px rgba(0, 204, 255, 0.4),
                    0 0 50px rgba(255, 0, 204, 0.3);
            }
        }
        
        /* Scanline effect tinh tế */
        .scanline {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 204, 0.6), transparent);
            box-shadow: 0 0 8px rgba(0, 255, 204, 0.5);
            animation: scan 5s linear infinite;
            z-index: 100;
            pointer-events: none;
            opacity: 0.7;
        }
        
        @keyframes scan {
            0% {
                top: 0%;
            }
            100% {
                top: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .portal-gallery {
                flex-direction: column;
                align-items: center;
            }
            
            .portal-card {
                max-width: 100%;
            }
            
            .simple-title {
                font-size: 2.5rem;
            }
            
            .featured-section h2 {
                font-size: 1.6rem;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700&family=Rajdhani:wght@300;400;500;600&display=swap" rel="stylesheet">
</head>
<body>
    <div class="scanline"></div>
    <div class="container">
        <header>
            <div class="cyber-grid"></div>
            <h1 class="simple-title">WISDOM PORTAL</h1>
            <p class="tagline">Kết nối với các chiều không gian tri thức - Trải nghiệm tương lai của giáo dục</p>
        </header>
        
        <div class="portal-gallery">
            <!-- Cổng 1 - Vũ Trụ Tri Thức -->
            <div class="portal-card" id="portal1">
                <div class="portal-frame">
                    <div class="portal-gate">
                        <img src="https://i.postimg.cc/4Nbrm7hC/Thi-t-k-ch-a-c-t-n-5.png" alt="Vũ Trụ Tri Thức" class="portal-image">
                    </div>
                </div>
                <div class="portal-info">
                    <h3>Vũ Trụ Tri Thức</h3>
                    <p>Khám phá vũ trụ tri thức với những bài học thú vị và kiến thức bổ ích từ nhiều lĩnh vực khác nhau.</p>
                    <div class="enter-btn">Kích Hoạt</div>
                </div>
            </div>
            
            <!-- Cổng 2 - VNDiceGame -->
            <div class="portal-card" id="portal2">
                <div class="portal-frame">
                    <div class="portal-gate">
                        <img src="https://i.postimg.cc/2yHSDcmp/Thi-t-k-ch-a-c-t-n-4.png" alt="VN Dice Game" class="portal-image">
                    </div>
                </div>
                <div class="portal-info">
                    <h3>VN Dice Game</h3>
                    <p>Thử thách may mắn với trò chơi xúc xắc đầy hấp dẫn và kịch tính, rèn luyện tư duy xác suất.</p>
                    <div class="enter-btn">Kích Hoạt</div>
                </div>
            </div>
            
            <!-- Cổng 3 - Đua Xe Tốc Độ -->
            <div class="portal-card" id="portal3">
                <div class="portal-frame">
                    <div class="portal-gate">
                        <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Trò chơi thể thao" class="portal-image">
                    </div>
                </div>
                <div class="portal-info">
                    <h3>Đua Xe Tốc Độ</h3>
                    <p>Trải nghiệm cảm giác tốc độ với những siêu xe đua hiện đại nhất và thách thức bản thân.</p>
                    <div class="enter-btn">Kích Hoạt</div>
                </div>
            </div>
            
            <!-- Cổng 4 - Thế Giới Toán Học -->
            <div class="portal-card" id="portal4">
                <div class="portal-frame">
                    <div class="portal-gate">
                        <img src="https://images.unsplash.com/photo-1635070041078-e363dbe005cb?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Thế giới toán học" class="portal-image">
                    </div>
                </div>
                <div class="portal-info">
                    <h3>Thế Giới Toán Học</h3>
                    <p>Khám phá vẻ đẹp của toán học qua những câu đố, thử thách logic và bài toán hấp dẫn.</p>
                    <div class="enter-btn">Kích Hoạt</div>
                </div>
            </div>
        </div>
        
        <div class="featured-section">
            <h2>Trải Nghiệm Giáo Dục Tương Lai</h2>
            <p>Wisdom Portal mang đến một chiều không gian mới cho việc học tập - nơi tri thức và công nghệ hội tụ để tạo ra những trải nghiệm giáo dục đột phá. Mỗi cánh cổng là một chiều không gian tri thức độc đáo.</p>
            <a href="#" class="cta-button">Kết Nối Hệ Thống</a>
        </div>
    </div>

    <footer>
        <p>WISDOM PORTAL - Hệ thống cánh cổng tri thức | Đã kích hoạt</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Xử lý sự kiện click cho các cổng
            const portal1 = document.getElementById('portal1');
            portal1.addEventListener('click', function() {
                window.open('https://stemprojectaccount.github.io/vu-tru-tri-thuc/', '_blank');
            });
            
            const portal2 = document.getElementById('portal2');
            portal2.addEventListener('click', function() {
                window.open('https://stemprojectaccount.github.io/VNDiceGame/', '_blank');
            });
            
            const portal3 = document.getElementById('portal3');
            portal3.addEventListener('click', function() {
                alert('Trò chơi Đua Xe Tốc Độ đang được phát triển!');
            });
            
            const portal4 = document.getElementById('portal4');
            portal4.addEventListener('click', function() {
                alert('Thế Giới Toán Học sẽ sớm ra mắt!');
            });
            
            // Thêm hiệu ứng scanline
            const scanline = document.querySelector('.scanline');
            setInterval(() => {
                scanline.style.animation = 'none';
                setTimeout(() => {
                    scanline.style.animation = 'scan 5s linear infinite';
                }, 10);
            }, 5000);
        });
    </script>
</body>
</html>
