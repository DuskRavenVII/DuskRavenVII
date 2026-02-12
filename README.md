<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DuskRavenVII - Bug-Driven Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            color: #e6e6e6;
            line-height: 1.8;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .header::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #ff0000, #ff6b6b);
            border-radius: 2px;
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, #ff0000, #ff6b6b);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #ff0000, #ff6b6b, #ffcc00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .subtitle {
            font-size: 1.2em;
            color: #ff6b6b;
            margin-bottom: 30px;
        }

        .philosophy-card {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 4px solid #ff0000;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .philosophy-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 0, 0, 0.2);
        }

        .philosophy-card h2 {
            color: #ff0000;
            margin-bottom: 15px;
            font-size: 1.8em;
        }

        .philosophy-list {
            list-style: none;
        }

        .philosophy-list li {
            padding: 10px;
            margin: 8px 0;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            transition: background 0.3s;
        }

        .philosophy-list li:hover {
            background: rgba(255, 0, 0, 0.1);
        }

        .skills-section {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
        }

        .skills-section h2 {
            color: #ff0000;
            margin-bottom: 20px;
            font-size: 1.8em;
        }

        .skill-category {
            margin-bottom: 20px;
        }

        .skill-category h3 {
            color: #ff6b6b;
            margin-bottom: 10px;
            font-size: 1.3em;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: rgba(255, 0, 0, 0.1);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9em;
            transition: all 0.3s;
        }

        .skill-tag:hover {
            background: rgba(255, 0, 0, 0.2);
            transform: scale(1.05);
        }

        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-card img {
            width: 100%;
            max-width: 400px;
            border-radius: 10px;
            transition: filter 0.3s;
        }

        .stat-card img:hover {
            filter: brightness(1.2);
        }

        .connect-section {
            background: rgba(255, 255, 255, 0.08);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
        }

        .connect-section h2 {
            color: #ff0000;
            margin-bottom: 20px;
            font-size: 1.8em;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 25px;
            background: rgba(255, 0, 0, 0.1);
            border-radius: 25px;
            color: #e6e6e6;
            text-decoration: none;
            transition: all 0.3s;
            font-size: 1.1em;
        }

        .social-link:hover {
            background: rgba(255, 0, 0, 0.2);
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(255, 0, 0, 0.3);
        }

        .social-link i {
            color: #ff0000;
            font-size: 1.3em;
        }

        .bug-counter {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: rgba(255, 0, 0, 0.2);
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 0.9em;
            color: #ff6b6b;
            z-index: 1000;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .typing-effect {
            overflow: hidden;
            border-right: 3px solid #ff0000;
            white-space: nowrap;
            animation: typing 3s steps(30, end), blink 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink {
            50% { border-color: transparent }
        }

        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            .stats-section {
                grid-template-columns: 1fr;
            }
            
            .avatar {
                width: 120px;
                height: 120px;
                font-size: 45px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="avatar">
                <i class="fas fa-crow"></i>
            </div>
            <h1>🪶 DuskRavenVII</h1>
            <p class="subtitle typing-effect">Bug-Driven Developer 🐛 – I don't write bugs, they write me!</p>
        </div>

        <div class="philosophy-card">
            <h2>😅 فلسفه کدنویسی من</h2>
            <ul class="philosophy-list">
                <li>99% باگ، 1% کد – <strong>کمال حاصل شد</strong></li>
                <li>اگر کامپایل شد، من از قبل مشکوکم 👀</li>
                <li>دیباگ کردن کاردیو من است 🏃‍♂️</li>
            </ul>
        </div>

        <div class="skills-section">
            <h2>🔧 مهارت‌ها و ابزارها</h2>
            <div class="skill-category">
                <h3>زبان‌های برنامه‌نویسی:</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Python</span>
                    <span class="skill-tag">JavaScript</span>
                    <span class="skill-tag">Rust</span>
                    <span class="skill-tag">C++</span>
                    <span class="skill-tag">Go</span>
                    <span class="skill-tag">TypeScript</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>ابزارها:</h3>
                <div class="skill-tags">
                    <span class="skill-tag">Git</span>
                    <span class="skill-tag">Docker</span>
                    <span class="skill-tag">VS Code</span>
                    <span class="skill-tag">Linux</span>
                </div>
            </div>
            <div class="skill-category">
                <h3>تخصص:</h3>
                <div class="skill-tags">
                    <span class="skill-tag">ایجاد باگ‌های افسانه‌ای</span>
                    <span class="skill-tag">حل مسائل پیچیده</span>
                    <span class="skill-tag">بهینه‌سازی عملکرد</span>
                </div>
            </div>
        </div>

        <div class="stats-section">
            <div class="stat-card">
                <h3>📊 آمار گیت‌هاب</h3>
                <img src="https://github-states-generator.vercel.app/api?username=DuskRavenVII&theme=react&show_icons=true&show=prs_merged%2Creviews&bg_color=000000&title_color=ff0000" alt="GitHub Stats">
            </div>
            <div class="stat-card">
                <h3>🌙 زبان‌های پرکاربرد</h3>
                <img src="https://github-states-generator.vercel.app/api/top-langs/?username=DuskRavenVII&theme=react&bg_color=000000&title_color=ff0000" alt="Top Languages">
            </div>
        </div>

        <div class="connect-section">
            <h2>📫 ارتباط با من</h2>
            <div class="social-links">
                <a href="https://discord.com/users/_amir_persian" class="social-link" target="_blank">
                    <i class="fab fa-discord"></i>
                    Discord: _amir_persian
                </a>
                <a href="https://github.com/DuskRavenVII" class="social-link" target="_blank">
                    <i class="fab fa-github"></i>
                    GitHub
                </a>
            </div>
        </div>
    </div>

    <div class="bug-counter" id="bugCounter">
        <i class="fas fa-bug"></i> تعداد باگ‌های امروز: <span id="bugCount">0</span>
    </div>

    <script>
        // Counter animation
        function animateCounter(element, start, end, duration) {
            let startTimestamp = null;
            const step = (timestamp) => {
                if (!startTimestamp) startTimestamp = timestamp;
                const progress = Math.min((timestamp - startTimestamp) / duration, 1);
                const value = Math.floor(progress * (end - start) + start);
                element.textContent = value;
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            };
            window.requestAnimationFrame(step);
        }

        // Initialize bug counter
        const bugCountElement = document.getElementById('bugCount');
        const randomBugCount = Math.floor(Math.random() * 100) + 50;
        animateCounter(bugCountElement, 0, randomBugCount, 2000);

        // Typing effect enhancement
        const typingElement = document.querySelector('.typing-effect');
        const originalText = typingElement.textContent;
        typingElement.textContent = '';
        
        let i = 0;
        const typeWriter = () => {
            if (i < originalText.length) {
                typingElement.textContent += originalText.charAt(i);
                i++;
                setTimeout(typeWriter, 50);
            }
        };
        
        setTimeout(typeWriter, 1000);

        // Interactive elements
        document.querySelectorAll('.skill-tag').forEach(tag => {
            tag.addEventListener('click', function() {
                this.style.transform = 'scale(1.1)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 300);
            });
        });

        // Confetti effect on hover
        document.querySelector('.avatar').addEventListener('click', function() {
            createConfetti();
        });

        function createConfetti() {
            const colors = ['#ff0000', '#ff6b6b', '#ffcc00', '#00ff00', '#00ccff'];
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'fixed';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-20px';
                confetti.style.zIndex = '9999';
                document.body.appendChild(confetti);
                
                const animationDuration = Math.random() * 3 + 2;
                const animationDelay = Math.random() * 1;
                
                confetti.style.animation = `fall ${animationDuration}s ease-in ${animationDelay}s forwards`;
                
                setTimeout(() => {
                    confetti.remove();
                }, (animationDuration + animationDelay) * 1000);
            }
            
            const style = document.createElement('style');
            style.textContent = `
                @keyframes fall {
                    to {
                        transform: translateY(100vh) rotate(360deg);
                        opacity: 0;
                    }
                }
            `;
            document.head.appendChild(style);
        }

        // Dark mode toggle (auto based on system preference)
        const prefersDarkScheme = window.matchMedia('(prefers-color-scheme: dark)');
        if (!prefersDarkScheme.matches) {
            document.body.style.background = 'linear-gradient(135deg, #f5f5f5 0%, #e0e0e0 50%, #d0d0d0 100%)';
            document.body.style.color = '#333';
            document.querySelectorAll('.container, .philosophy-card, .skills-section, .stat-card, .connect-section').forEach(el => {
                el.style.background = 'rgba(255, 255, 255, 0.95)';
                el.style.boxShadow = '0 8px 32px rgba(0, 0, 0, 0.1)';
            });
        }
    </script>
</body>
</html>
