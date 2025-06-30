# avall
این سایت دارای چهار تا از ابزار های ریاضی است
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ابزارهای ریاضی</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #4e54c8;
            --secondary: #8f94fb;
            --accent: #ff6b6b;
            --dark: #2c3e50;
            --light: #f8f9fa;
            --success: #1dd1a1;
            --warning: #feca57;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 30px 0;
            color: white;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
            animation: fadeInDown 1s ease;
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        header h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
        }
        
        header p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto;
            opacity: 0.9;
        }
        
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }
        
        .tool-card {
            background: rgba(255, 255, 255, 0.92);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            padding: 25px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease;
            animation-fill-mode: both;
        }
        
        .tool-card:nth-child(1) { animation-delay: 0.2s; }
        .tool-card:nth-child(2) { animation-delay: 0.4s; }
        .tool-card:nth-child(3) { animation-delay: 0.6s; }
        .tool-card:nth-child(4) { animation-delay: 0.8s; }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .tool-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        
        .tool-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
        }
        
        .tool-icon {
            font-size: 2.8rem;
            color: var(--primary);
            margin-bottom: 20px;
            text-align: center;
        }
        
        .tool-card h2 {
            color: var(--dark);
            font-size: 1.8rem;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .input-group {
            margin-bottom: 20px;
        }
        
        .input-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .input-group input {
            width: 100%;
            padding: 14px;
            border: 2px solid #e1e5f0;
            border-radius: 10px;
            font-size: 1.1rem;
            transition: border-color 0.3s;
        }
        
        .input-group input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(78, 84, 200, 0.2);
        }
        
        button {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            margin-top: 10px;
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 15px rgba(78, 84, 200, 0.4);
        }
        
        button:active {
            transform: translateY(0);
        }
        
        .result {
            margin-top: 20px;
            padding: 20px;
            background: rgba(241, 243, 246, 0.7);
            border-radius: 10px;
            text-align: center;
            font-size: 1.2rem;
            font-weight: 600;
            min-height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            color: var(--dark);
            transition: all 0.4s ease;
        }
        
        .prime-result {
            font-size: 1.4rem;
        }
        
        .factors {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 8px;
        }
        
        .factor-badge {
            background: var(--primary);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: 600;
            animation: popIn 0.3s ease;
        }
        
        @keyframes popIn {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: white;
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        @media (max-width: 768px) {
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            header h1 {
                font-size: 2.5rem;
            }
            
            header p {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-calculator"></i> ابزارهای ریاضی</h1>
            <p>مجموعه ابزارهای کاربردی برای محاسبات ریاضی - تمام ابزارها به صورت آنلاین و رایگان در دسترس شما هستند</p>
        </header>
        
        <div class="tools-grid">
            <!-- ابزار اول: بررسی عدد اول -->
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-crown"></i>
                </div>
                <h2>بررسی عدد اول</h2>
                <div class="input-group">
                    <label for="prime-input">عدد طبیعی مورد نظر را وارد کنید:</label>
                    <input type="number" id="prime-input" min="2" placeholder="مثال: 17">
                </div>
                <button id="check-prime-btn">بررسی اول بودن</button>
                <div class="result" id="prime-result">نتیجه اینجا نمایش داده می‌شود</div>
            </div>
            
            <!-- ابزار دوم: محاسبه ب.م.م -->
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-handshake"></i>
                </div>
                <h2>محاسبه بزرگترین مقسوم‌علیه مشترک (ب.م.م)</h2>
                <div class="input-group">
                    <label for="gcd-input1">عدد اول:</label>
                    <input type="number" id="gcd-input1" min="1" placeholder="مثال: 48">
                </div>
                <div class="input-group">
                    <label for="gcd-input2">عدد دوم:</label>
                    <input type="number" id="gcd-input2" min="1" placeholder="مثال: 36">
                </div>
                <button id="gcd-btn">محاسبه ب.م.م</button>
                <div class="result" id="gcd-result">نتیجه اینجا نمایش داده می‌شود</div>
            </div>
            
            <!-- ابزار سوم: محاسبه ک.م.م -->
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-infinity"></i>
                </div>
                <h2>محاسبه کوچکترین مضرب مشترک (ک.م.م)</h2>
                <div class="input-group">
                    <label for="lcm-input1">عدد اول:</label>
                    <input type="number" id="lcm-input1" min="1" placeholder="مثال: 15">
                </div>
                <div class="input-group">
                    <label for="lcm-input2">عدد دوم:</label>
                    <input type="number" id="lcm-input2" min="1" placeholder="مثال: 20">
                </div>
                <button id="lcm-btn">محاسبه ک.م.م</button>
                <div class="result" id="lcm-result">نتیجه اینجا نمایش داده می‌شود</div>
            </div>
            
            <!-- ابزار چهارم: تجزیه به عوامل اول -->
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-sitemap"></i>
                </div>
                <h2>تجزیه به عوامل اول</h2>
                <div class="input-group">
                    <label for="factors-input">عدد طبیعی مورد نظر را وارد کنید:</label>
                    <input type="number" id="factors-input" min="2" placeholder="مثال: 60">
                </div>
                <button id="factors-btn">تجزیه عدد</button>
                <div class="result" id="factors-result">نتیجه اینجا نمایش داده می‌شود</div>
            </div>
        </div>
        
        <div class="footer">
            <p>تمامی حقوق محفوظ است © ۲۰۲۳ - ابزارهای ریاضی</p>
        </div>
    </div>

    <script>
        // تابع بررسی عدد اول
        function isPrime(n) {
            if (n <= 1) return false;
            if (n <= 3) return true;
            if (n % 2 === 0 || n % 3 === 0) return false;
            
            let i = 5;
            while (i * i <= n) {
                if (n % i === 0 || n % (i + 2) === 0) return false;
                i += 6;
            }
            return true;
        }
        
        // تابع محاسبه ب.م.م با الگوریتم اقلیدسی
        function gcd(a, b) {
            if (b === 0) return Math.abs(a);
            return gcd(b, a % b);
        }
        
        // تابع محاسبه ک.م.م
        function lcm(a, b) {
            return Math.abs(a * b) / gcd(a, b);
        }
        
        // تابع تجزیه به عوامل اول
        function primeFactors(n) {
            const factors = {};
            let divisor = 2;
            
            while (n >= 2) {
                if (n % divisor === 0) {
                    factors[divisor] = (factors[divisor] || 0) + 1;
                    n = n / divisor;
                } else {
                    divisor++;
                }
            }
            return factors;
        }
        
        // تابع نمایش تجزیه به عوامل اول
        function formatFactors(factors) {
            let result = [];
            for (const [prime, exponent] of Object.entries(factors)) {
                if (exponent === 1) {
                    result.push(`${prime}`);
                } else {
                    result.push(`${prime}<sup>${exponent}</sup>`);
                }
            }
            return result.join(' × ');
        }
        
        // رویدادها
        document.getElementById('check-prime-btn').addEventListener('click', function() {
            const input = document.getElementById('prime-input');
            const num = parseInt(input.value);
            const resultElement = document.getElementById('prime-result');
            
            if (isNaN(num) || num < 2) {
                resultElement.innerHTML = '<span style="color: var(--accent);">لطفاً عددی طبیعی بزرگتر از 1 وارد کنید</span>';
                return;
            }
            
            if (isPrime(num)) {
                resultElement.innerHTML = `<span style="color: var(--success);" class="prime-result">${num} یک عدد اول است!</span>`;
            } else {
                resultElement.innerHTML = `<span style="color: var(--accent);" class="prime-result">${num} عدد اول نیست</span>`;
            }
        });
        
        document.getElementById('gcd-btn').addEventListener('click', function() {
            const input1 = document.getElementById('gcd-input1');
            const input2 = document.getElementById('gcd-input2');
            const num1 = parseInt(input1.value);
            const num2 = parseInt(input2.value);
            const resultElement = document.getElementById('gcd-result');
            
            if (isNaN(num1) || isNaN(num2) || num1 < 1 || num2 < 1) {
                resultElement.innerHTML = '<span style="color: var(--accent);">لطفاً دو عدد طبیعی معتبر وارد کنید</span>';
                return;
            }
            
            const result = gcd(num1, num2);
            resultElement.innerHTML = `<span style="color: var(--primary); font-size: 1.4rem;">ب.م.م (${num1}, ${num2}) = ${result}</span>`;
        });
        
        document.getElementById('lcm-btn').addEventListener('click', function() {
            const input1 = document.getElementById('lcm-input1');
            const input2 = document.getElementById('lcm-input2');
            const num1 = parseInt(input1.value);
            const num2 = parseInt(input2.value);
            const resultElement = document.getElementById('lcm-result');
            
            if (isNaN(num1) || isNaN(num2) || num1 < 1 || num2 < 1) {
                resultElement.innerHTML = '<span style="color: var(--accent);">لطفاً دو عدد طبیعی معتبر وارد کنید</span>';
                return;
            }
            
            const result = lcm(num1, num2);
            resultElement.innerHTML = `<span style="color: var(--primary); font-size: 1.4rem;">ک.م.م (${num1}, ${num2}) = ${result}</span>`;
        });
        
        document.getElementById('factors-btn').addEventListener('click', function() {
            const input = document.getElementById('factors-input');
            const num = parseInt(input.value);
            const resultElement = document.getElementById('factors-result');
            
            if (isNaN(num) || num < 2) {
                resultElement.innerHTML = '<span style="color: var(--accent);">لطفاً عددی طبیعی بزرگتر از 1 وارد کنید</span>';
                return;
            }
            
            const factors = primeFactors(num);
            if (Object.keys(factors).length === 0) {
                resultElement.innerHTML = `<span style="color: var(--success);">${num} یک عدد اول است</span>`;
            } else {
                resultElement.innerHTML = `
                    <div>عوامل اول ${num}:</div>
                    <div class="factors">${formatFactors(factors)}</div>
                `;
            }
        });
    </script>
</body>
</html>
