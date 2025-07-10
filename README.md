<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to GitHub - Where Code Comes to Life</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #21262d 100%);
            color: #f0f6fc;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 50% 50%, rgba(56, 189, 248, 0.1) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.6; }
        }

        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .hero-text {
            animation: slideInLeft 1s ease-out;
        }

        .hero-visual {
            animation: slideInRight 1s ease-out;
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #38bdf8 0%, #06b6d4 50%, #0891b2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.3rem;
            color: #8b949e;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #238636 0%, #2ea043 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(35, 134, 54, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(35, 134, 54, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: #f0f6fc;
            border: 2px solid #30363d;
        }

        .btn-secondary:hover {
            background: #30363d;
            transform: translateY(-2px);
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin-top: 40px;
        }

        .stat-item {
            text-align: center;
            padding: 20px;
            background: rgba(33, 38, 45, 0.5);
            border-radius: 12px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(48, 54, 61, 0.3);
            transition: transform 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #38bdf8;
            display: block;
        }

        .stat-label {
            color: #8b949e;
            font-size: 0.9rem;
            margin-top: 5px;
        }

        .code-visual {
            background: #0d1117;
            border-radius: 12px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            line-height: 1.6;
            border: 1px solid #30363d;
            position: relative;
            overflow: hidden;
        }

        .code-visual::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 30px;
            background: linear-gradient(90deg, #f85149 0%, #f1c40f 33%, #2ea043 66%, #38bdf8 100%);
            border-radius: 12px 12px 0 0;
        }

        .code-content {
            margin-top: 30px;
        }

        .code-line {
            display: flex;
            align-items: center;
            margin-bottom: 8px;
            opacity: 0;
            animation: typewriter 0.5s ease-out forwards;
        }

        .code-line:nth-child(1) { animation-delay: 0.5s; }
        .code-line:nth-child(2) { animation-delay: 1s; }
        .code-line:nth-child(3) { animation-delay: 1.5s; }
        .code-line:nth-child(4) { animation-delay: 2s; }

        @keyframes typewriter {
            from { opacity: 0; transform: translateX(-10px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .line-number {
            color: #6e7681;
            width: 30px;
            text-align: right;
            margin-right: 15px;
        }

        .keyword { color: #ff7b72; }
        .string { color: #a5d6ff; }
        .comment { color: #8b949e; }
        .function { color: #d2a8ff; }

        .floating-elements {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }

        .floating-icon {
            position: absolute;
            font-size: 1.5rem;
            color: rgba(56, 189, 248, 0.3);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .floating-icon:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .floating-icon:nth-child(2) { top: 60%; left: 80%; animation-delay: 2s; }
        .floating-icon:nth-child(3) { top: 80%; left: 20%; animation-delay: 4s; }

        @media (max-width: 768px) {
            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .stats {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-icon">⚡</div>
        <div class="floating-icon">🚀</div>
        <div class="floating-icon">💻</div>
    </div>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Build the future with code</h1>
                    <p>Join over 100 million developers using GitHub to create, collaborate, and ship amazing software together. Your next breakthrough starts here.</p>
                    
                    <div class="cta-buttons">
                        <a href="#" class="btn btn-primary">
                            🚀 Start coding
                        </a>
                        <a href="#" class="btn btn-secondary">
                            📚 Explore projects
                        </a>
                    </div>

                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number">100M+</span>
                            <span class="stat-label">Developers</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">330M+</span>
                            <span class="stat-label">Repositories</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">28M+</span>
                            <span class="stat-label">Organizations</span>
                        </div>
                    </div>
                </div>

                <div class="hero-visual">
                    <div class="code-visual">
                        <div class="code-content">
                            <div class="code-line">
                                <span class="line-number">1</span>
                                <span class="keyword">const</span> <span class="function">developer</span> = <span class="string">"you"</span>;
                            </div>
                            <div class="code-line">
                                <span class="line-number">2</span>
                                <span class="keyword">const</span> <span class="function">possibilities</span> = <span class="string">"infinite"</span>;
                            </div>
                            <div class="code-line">
                                <span class="line-number">3</span>
                                <span class="comment">// Welcome to GitHub! 🎉</span>
                            </div>
                            <div class="code-line">
                                <span class="line-number">4</span>
                                <span class="function">build</span>(<span class="string">"amazing-things"</span>);
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Add smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            // Add interactive hover effects to buttons
            const buttons = document.querySelectorAll('.btn');
            buttons.forEach(button => {
                button.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-2px) scale(1.05)';
                });
                
                button.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });

            // Animate stats on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'slideInLeft 0.6s ease-out forwards';
                    }
                });
            }, observerOptions);

            document.querySelectorAll('.stat-item').forEach(stat => {
                observer.observe(stat);
            });
        });
    </script>
</body>
</html>
