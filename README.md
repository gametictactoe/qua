<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quà Tặng Ngày Quốc Tế Nam Giới</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f8bbd0; /* Pink background */
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            min-height: 100vh;
            overflow: hidden;
            box-sizing: border-box;
        }

        h3 {
            color: #333;
            margin-top: 20px; /* Đảm bảo khoảng cách giữa h3 và phần tử trên */
            font-size: 5vw; /* Đảm bảo h1 scale tốt trên điện thoại */
            text-align: center;
        }

        /* Khung chứa ảnh */
        .image-container {
            position: relative;
            display: inline-block;
            margin-bottom: 3vw;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .image-container img {
            width: 100%;
            height: auto;
            max-width: 25vw;
            border-radius: 15px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
        }

        /* Hiệu ứng khi hover */
        .image-container img:hover {
            animation: scale-rotate 1s ease-in-out;
            transform: scale(1.1) rotate(15deg);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        /* Gói quà vẽ tay */
        .gift {
            position: relative;
            width: 25vw;
            height: 25vw;
            max-width: 150px;
            max-height: 150px;
            margin: 2vw;
            background: linear-gradient(135deg, #ffc048, #ffdd87);
            border-radius: 10px;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
            cursor: pointer;
            transition: transform 0.3s ease;
            overflow: hidden;
        }

        /* Nắp hộp quà */
        .gift .lid {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 50%;
            background: #ff4747;
            border-radius: 10px 10px 0 0;
            transition: all 0.5s ease-in-out;
        }

        /* Hiệu ứng mở nắp */
        .gift.opened .lid {
            top: -50%;
            transform: rotateX(90deg);
        }

        /* Khung chứa gói quà */
        .gifts-container {
            display: flex;
            gap: 3vw;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 5vw; /* Dịch hộp quà xuống dưới ảnh */
        }

        /* Đám mây bồng bềnh */
        .cloud {
            position: absolute;
            background: url('cloud.png') no-repeat center center;
            background-size: contain;
            animation: cloudMove 10s ease-in-out infinite;
        }

        .cloud.small {
            width: 60px;
            height: 60px;
            top: 20px;
            left: 10%;
        }

        .cloud.medium {
            width: 100px;
            height: 60px;
            top: 10px;
            left: 40%;
        }

        .cloud.large {
            width: 140px;
            height: 80px;
            top: 5px;
            left: 70%;
        }

        .cloud.extra-small {
            width: 40px;
            height: 40px;
            top: 30px;
            left: 25%;
            animation: cloudMove 12s ease-in-out infinite;
        }

        .cloud.extra-large {
            width: 200px;
            height: 120px;
            top: 30px;
            left: 55%;
            animation: cloudMove 15s ease-in-out infinite;
        }

        .cloud.extra-small-two {
            width: 40px;
            height: 40px;
            top: 50px;
            left: 70%;
            animation: cloudMove 14s ease-in-out infinite;
        }

        .cloud.extra-large-two {
            width: 200px;
            height: 120px;
            top: 50px;
            left: 10%;
            animation: cloudMove 17s ease-in-out infinite;
        }

        .sun {
            position: absolute;
            width: 80px;
            height: 80px;
            top: 10px;
            right: 10%;
            background: url('sun.png') no-repeat center center;
            background-size: contain;
            box-shadow: 0 0 20px rgba(255, 193, 7, 0.7);
            animation: sunAnimation 3s infinite alternate;
        }

        /* Thỏ di chuyển */
        .rabbit {
            position: absolute;
            bottom: 5px;
            width: 30px; /* Reduced size for mobile */
            height: 30px;
            background: #fff;
            border-radius: 50%;
            box-shadow: 0 0 8px rgba(0, 0, 0, 0.2);
            animation: rabbitMove 4s linear infinite;
        }

        .rabbit::before, .rabbit::after {
            width: 6px;
            height: 6px;
            background: #000;
        }

        /* Thỏ bên trái */
        .rabbit-left {
            left: 0;
            animation-direction: normal;
        }

        /* Thỏ bên phải */
        .rabbit-right {
            right: 0;
            animation-direction: reverse;
        }

        /* Animations */
        @keyframes cloudMove {
            0% { transform: translateX(0); }
            50% { transform: translateX(20px); }
            100% { transform: translateX(0); }
        }

        @keyframes rabbitMove {
            0% { transform: translateX(0); }
            50% { transform: translateX(80px); }
            100% { transform: translateX(0); }
        }

        @keyframes sunAnimation {
            0% { transform: translateY(0); }
            100% { transform: translateY(10px); }
        }

        .image-container.left,
        .image-container.right {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
        }

        .image-container.left {
            left: 10px;
        }

        .image-container.right {
            right: 10px;
        }

        /* Thông điệp */
        #message {
            margin-top: 20px;
            font-size: 2.5vw;
            color: #333;
            text-align: center;
            opacity: 0;
            animation: fadeIn 2s forwards;
        }

        .gift-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            font-size: 1.2rem;
            font-weight: bold;
            text-align: center;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        /* Đảm bảo tính tương thích trên các kích thước màn hình */
        @media screen and (max-width: 1024px) {
            h3 {
                font-size: 6vw;
            }

            .gift {
                width: 30vw;
                height: 30vw;
                max-width: 120px;
                max-height: 120px;
            }

            .gift-text {
                font-size: 1rem;
            }
        }

        @media screen and (max-width: 768px) {
            .gift {
                width: 35vw;
                height: 35vw;
            }

            h3 {
                font-size: 7vw;
            }

            .gift-text {
                font-size: 0.9rem;
            }
        }

        @media screen and (max-width: 480px) {
            .gift {
                width: 40vw;
                height: 40vw;
            }

            h3 {
                font-size: 8vw;
            }

            .gift-text {
                font-size: 0.8rem;
            }
        }
    </style>
</head>
<body>
    <h3>HAPPY BOY’S DAY MAI QUY TAI</h3>

    <!-- Ảnh bên trái -->
    <div class="image-container left">
        <img src="maitai.png" alt="collection1">
    </div>

    <!-- Ảnh chính -->
    <div class="image-container">
        <img src="giua.png" alt="collection">
    </div>

    <!-- Ảnh bên phải -->
    <div class="image-container right">
        <img src="uyenthuong.png" alt="collection">
    </div>

    <!-- Cảnh thiên nhiên -->
    <div class="cloud small"></div>
    <div class="cloud medium"></div>
    <div class="cloud large"></div>
    <div class="cloud extra-small"></div>
    <div class="cloud extra-large"></div>
    <div class="cloud extra-small-two"></div> <!-- Mây thứ sáu -->
    <div class="cloud extra-large-two"></div> <!-- Mây thứ bảy -->
    <div class="sun"></div>

    <!-- Gói quà -->
    <div class="gifts-container">
        <div class="gift" onclick="showMessage(1)">
            <div class="lid"></div>
            <div class="gift-text">đạt được mục tiêu đã đặt ra </div>
        </div>
        <div class="gift" onclick="showMessage(2)">
            <div class="lid"></div>
            <div class="gift-text">vượt qua giải tích, đại số </div>
        </div>
        <div class="gift" onclick="showMessage(3)">
            <div class="lid"></div>
            <div class="gift-text">chịu được tính tôi</div>
        </div>
    </div>

    <!-- Thỏ di chuyển -->
    <div class="rabbit rabbit-left"></div>
    <div class="rabbit rabbit-right"></div>

    <!-- Lời chúc -->
    <div id="message"></div>

    <script>
        function showMessage(giftNumber) {
            const messages = [
                "Chúc bạn luôn mạnh mẽ và hạnh phúc!",
                "Hy vọng mọi điều tốt đẹp sẽ đến với bạn!",
                "Mong bạn luôn đạt được thành công trong mọi công việc!"
            ];

            // Hiển thị thông điệp
            document.getElementById("message").innerText = messages[giftNumber - 1];

            const gifts = document.querySelectorAll('.gift');
            const lids = document.querySelectorAll('.lid');
            const texts = document.querySelectorAll('.gift-text');

            // Mở nắp hộp quà khi nhấp vào
            gifts[giftNumber - 1].classList.add('opened');
            lids[giftNumber - 1].style.top = "-50%";  // Di chuyển nắp hộp lên trên khi mở
            lids[giftNumber - 1].style.transform = "rotateX(90deg)"; // Nắp quay lại khi mở

            // Hiển thị văn bản bên trong hộp
            texts[giftNumber - 1].style.opacity = 1;
        }
    </script>
</body>
</html>  
