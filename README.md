TYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>اعتذار لأبويا</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap');

body {
    margin: 0;
    font-family: 'Cairo', sans-serif;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ffe6cc, #ffd699);
    overflow: hidden;
}

/* الخلفية المتحركة للكلمات */
.background-text {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    pointer-events: none;
    z-index: 0;
    color: rgba(0,0,0,0.03);
    font-size: 80px;
    animation: floatText 35s linear infinite;
}

.background-text span {
    margin: 50px;
    user-select: none;
}

@keyframes floatText {
    0% { transform: translateY(0) rotate(0deg); }
    50% { transform: translateY(-20%) rotate(180deg); }
    100% { transform: translateY(0) rotate(360deg); }
}

/* مربع تسجيل الدخول */
#loginBox {
    position: relative;
    z-index: 2;
    text-align: center;
    background: rgba(255,255,255,0.7);
    padding: 50px;
    border-radius: 30px;
    box-shadow: 0 0 30px rgba(0,0,0,0.3);
    max-width: 400px;
    width: 90%;
    transition: all 0.5s ease;
}

#loginBox h2 {
    color: #ff6600;
    margin-bottom: 25px;
    font-size: 24px;
}

#loginBox input {
    width: 70%;
    padding: 12px;
    font-size: 18px;
    border-radius: 12px;
    border: 1px solid #ccc;
    margin-bottom: 20px;
}

#loginBox button {
    padding: 12px 30px;
    font-size: 18px;
    border-radius: 12px;
    border: none;
    background-color: #ff6600;
    color: #fff;
    font-weight: bold;
    cursor: pointer;
}

/* صندوق الرسالة */
.container {
    display: none;
    position: relative;
    z-index: 2;
    text-align: center;
    background: rgba(255,255,255,0.85);
    padding: 50px;
    border-radius: 30px;
    box-shadow: 0 0 40px rgba(0,0,0,0.3);
    max-width: 600px;
    width: 90%;
    animation: fadeIn 2s ease forwards;
}

@keyframes fadeIn {
    0% {opacity: 0; transform: translateY(50px);}
    100% {opacity: 1; transform: translateY(0);}
}

.message {
    font-size: 28px;
    font-weight: bold;
    color: #ff6600;
    margin-bottom: 25px;
    text-shadow: 0 0 10px #ff9900, 0 0 20px #ffcc00;
}

/* توقيعك */
.signature {
    font-size: 18px;
    color: #333;
    font-weight: bold;
    margin-top: 15px;
}
</style>
</head>
<body>

<!-- الخلفية المتحركة -->
<div class="background-text" id="bgText">
    <span>متزعلش ي حج</span>
    <span>متزعلش ي حج</span>
    <span>متزعلش ي حج</span>
    <span>متزعلش ي حج</span>
</div>

<!-- تسجيل الدخول -->
<div id="loginBox">
    <h2>ادخل تاريخ ميلادك للوصول</h2>
    <input type="password" id="pass" placeholder="تاريخ ميلادك">
    <br>
    <button onclick="checkPass()">دخول</button>
</div>

<!-- رسالة الاعتذار -->
<div class="container" id="content">
    <div class="message">
        بابا الغالي، حقك عليا ي حج، أنا آسف من كل قلبي على أي حاجة زعلتك فيها.
    </div>
    <div class="signature">
        by eng youssef ahmed mostafa
    </div>
</div>

<script>
function checkPass() {
    let password = document.getElementById('pass').value;
    let correctPass = "101283"; // ضع هنا تاريخ ميلادك
    if(password === correctPass) {
        document.getElementById('loginBox').style.display = 'none';
        document.getElementById('content').style.display = 'block';
        document.getElementById('bgText').style.display = 'flex';
    } else {
        alert("مش فاكر تاريخ ميلادك؟");
    }
}
</script>

</body>
</html>
