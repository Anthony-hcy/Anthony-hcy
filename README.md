<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>✨ 文艺 · 个人展示</title>
    <!-- 优雅字体 & 图标库 -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #fcf8f3;
            /* 奶白基底 */
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 2rem 1rem;
            font-family: 'Inter', 'JetBrains Mono', -apple-system, BlinkMacSystemFont, sans-serif;
            color: #2d2a24;
        }

        .card {
            max-width: 1000px;
            width: 100%;
            background: rgba(255, 252, 248, 0.75);
            backdrop-filter: blur(6px);
            -webkit-backdrop-filter: blur(6px);
            border-radius: 48px;
            padding: 2.8rem 2.8rem 2.2rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.04), 0 8px 24px rgba(0, 0, 0, 0.02), inset 0 1px 0 rgba(255, 255, 255, 0.6);
            border: 1px solid rgba(235, 225, 215, 0.5);
            transition: all 0.2s ease;
        }

        /* ===== 排版 ===== */
        .greeting {
            font-size: 1.9rem;
            font-weight: 350;
            letter-spacing: -0.02em;
            color: #3d352c;
            display: flex;
            flex-wrap: wrap;
            align-items: baseline;
            gap: 0.2rem 0.6rem;
            margin-bottom: 1.8rem;
            border-bottom: 1px solid rgba(210, 195, 180, 0.3);
            padding-bottom: 1.2rem;
        }
        .greeting .wave {
            display: inline-block;
            animation: wave 2s infinite;
            transform-origin: 70% 70%;
        }
        @keyframes wave {
            0% {
                transform: rotate(0deg);
            }
            10% {
                transform: rotate(14deg);
            }
            20% {
                transform: rotate(-8deg);
            }
            30% {
                transform: rotate(14deg);
            }
            40% {
                transform: rotate(-4deg);
            }
            50% {
                transform: rotate(10deg);
            }
            60%,
            100% {
                transform: rotate(0deg);
            }
        }

        .greeting .typing-wrapper {
            display: inline-flex;
            align-items: baseline;
            font-family: 'JetBrains Mono', monospace;
            font-weight: 350;
            font-size: 1.5rem;
            color: #6b5f53;
            background: rgba(235, 225, 215, 0.25);
            padding: 0.1rem 0.9rem 0.1rem 1.1rem;
            border-radius: 40px;
            border: 1px solid rgba(210, 195, 180, 0.2);
        }
        .greeting .typing-wrapper .cursor {
            display: inline-block;
            width: 2px;
            height: 1.2em;
            background: #b7a48e;
            margin-left: 6px;
            animation: blink 1s step-end infinite;
        }
        @keyframes blink {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0;
            }
        }

        /* ===== 双栏布局 ===== */
        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem 2.2rem;
            margin: 2.2rem 0 2rem;
        }

        @media (max-width: 700px) {
            .card {
                padding: 1.8rem 1.2rem;
            }
            .grid-2 {
                grid-template-columns: 1fr;
                gap: 1.8rem;
            }
            .greeting {
                font-size: 1.4rem;
                flex-direction: column;
                align-items: flex-start;
            }
            .greeting .typing-wrapper {
                font-size: 1.2rem;
                padding: 0.1rem 0.7rem;
            }
        }

        /* ===== Spotify 卡片 ===== */
        .spotify-card {
            background: #1e1a16;
            border-radius: 32px;
            padding: 1.4rem 1.4rem 1.2rem;
            color: #ece4db;
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.08);
            transition: transform 0.2s ease;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }
        .spotify-card:hover {
            transform: translateY(-2px);
        }
        .spotify-card .label {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.85rem;
            font-weight: 400;
            letter-spacing: 0.02em;
            text-transform: uppercase;
            color: #b7a696;
            margin-bottom: 0.9rem;
        }
        .spotify-card .label i {
            font-size: 1.2rem;
            color: #1db954;
        }
        .spotify-card iframe {
            border-radius: 20px;
            width: 100%;
            height: 80px;
            border: none;
            background: #0d0b09;
        }
        .spotify-card .track-meta {
            margin-top: 0.7rem;
            font-size: 0.8rem;
            color: #b7a696;
            display: flex;
            justify-content: space-between;
            letter-spacing: 0.01em;
        }
        .spotify-card .track-meta span i {
            margin-right: 4px;
            color: #7f6e5d;
        }

        /* ===== 头像 ===== */
        .avatar-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: rgba(235, 225, 215, 0.2);
            border-radius: 32px;
            padding: 1rem 1rem 1.2rem;
            border: 1px solid rgba(210, 195, 180, 0.2);
            backdrop-filter: blur(2px);
        }
        .avatar-card img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.04);
            border: 2px solid rgba(255, 255, 255, 0.5);
            transition: 0.2s;
        }
        .avatar-card img:hover {
            transform: scale(1.02);
        }
        .avatar-card .caption {
            margin-top: 0.7rem;
            font-size: 0.9rem;
            font-weight: 350;
            color: #5f5347;
            letter-spacing: 0.02em;
        }
        .avatar-card .caption i {
            margin: 0 3px;
            color: #b7a48e;
        }

        /* ===== 统计卡片 ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.2rem;
            margin: 1.6rem 0 2rem;
        }
        @media (max-width: 500px) {
            .stats-grid {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
        }

        .stat-card {
            background: rgba(255, 252, 248, 0.7);
            backdrop-filter: blur(4px);
            border-radius: 28px;
            padding: 1rem 1.2rem;
            border: 1px solid rgba(210, 195, 180, 0.25);
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.01);
            transition: 0.15s ease;
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        .stat-card:hover {
            border-color: rgba(180, 160, 140, 0.4);
            background: rgba(255, 252, 248, 0.9);
        }
        .stat-card .icon {
            font-size: 1.8rem;
            color: #8f7e6b;
            width: 2.4rem;
            text-align: center;
        }
        .stat-card .info {
            line-height: 1.3;
        }
        .stat-card .info .number {
            font-size: 1.5rem;
            font-weight: 400;
            letter-spacing: -0.02em;
            color: #2d2a24;
        }
        .stat-card .info .label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.04em;
            color: #8f7e6b;
            font-weight: 400;
        }

        /* ===== 项目展示 ===== */
        .projects {
            margin: 2rem 0 1.8rem;
        }
        .projects .section-title {
            font-size: 1rem;
            font-weight: 400;
            letter-spacing: 0.06em;
            text-transform: uppercase;
            color: #8f7e6b;
            margin-bottom: 1.2rem;
            border-bottom: 1px solid rgba(210, 195, 180, 0.2);
            padding-bottom: 0.6rem;
        }
        .project-list {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }
        .project-item {
            background: rgba(255, 252, 248, 0.6);
            border-radius: 40px;
            padding: 0.6rem 1.4rem 0.6rem 1.2rem;
            border: 1px solid rgba(210, 195, 180, 0.2);
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            color: #3d352c;
            text-decoration: none;
            transition: 0.15s;
            backdrop-filter: blur(2px);
        }
        .project-item i {
            color: #8f7e6b;
            font-size: 1rem;
        }
        .project-item:hover {
            background: rgba(255, 252, 248, 0.9);
            border-color: #c6b5a4;
            transform: translateY(-1px);
            box-shadow: 0 4px 14px rgba(0, 0, 0, 0.02);
        }

        /* ===== 社交 & 脚注 ===== */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem 1.8rem;
            margin-top: 1.8rem;
            padding-top: 1.2rem;
            border-top: 1px solid rgba(210, 195, 180, 0.2);
            justify-content: center;
        }
        .social-links a {
            color: #5f5347;
            text-decoration: none;
            font-size: 0.9rem;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: 0.15s;
            letter-spacing: 0.01em;
            font-weight: 350;
        }
        .social-links a i {
            font-size: 1.2rem;
            color: #8f7e6b;
            transition: 0.15s;
        }
        .social-links a:hover {
            color: #2d2a24;
        }
        .social-links a:hover i {
            color: #2d2a24;
        }

        .footer-note {
            text-align: center;
            margin-top: 1.8rem;
            font-size: 0.75rem;
            color: #b7a696;
            letter-spacing: 0.02em;
            font-weight: 300;
        }
        .footer-note i {
            margin: 0 4px;
            color: #c6b5a4;
        }

        /* ===== 小点缀 ===== */
        .dot-divider {
            display: inline-block;
            width: 4px;
            height: 4px;
            background: #d6c8bb;
            border-radius: 50%;
            margin: 0 8px;
            opacity: 0.5;
        }
        .badge-soft {
            background: rgba(210, 195, 180, 0.15);
            border-radius: 40px;
            padding: 0.1rem 0.9rem;
            font-size: 0.7rem;
            color: #6b5f53;
            letter-spacing: 0.04em;
            border: 1px solid rgba(210, 195, 180, 0.1);
        }
    </style>
</head>
<body>

    <div class="card">

        <!-- ======== 问候 + 打字 ======== -->
        <div class="greeting">
            <span class="wave">👋</span>
            <span>你好，我是</span>
            <span style="font-weight:450; color:#2d2a24;">Anthony</span>
            <span class="dot-divider"></span>
            <span class="typing-wrapper">
                <span id="typed-text">Privet!</span>
                <span class="cursor"></span>
            </span>
        </div>

        <!-- ======== 双栏：Spotify + 头像 ======== -->
        <div class="grid-2">
            <!-- 左侧 Spotify -->
            <div class="spotify-card">
                <div class="label">
                    <i class="fab fa-spotify"></i> 此刻旋律
                    <span style="margin-left:auto; font-weight:300; font-size:0.7rem; opacity:0.5;">· 近况</span>
                </div>
                <!-- 嵌入 Spotify 播放器 (替换为你的 iframe) -->
                <iframe
                src="https://open.spotify.com/embed/playlist/37i9dQZF1DXcBWIGoYBM5M?utm_source=generator&theme=0"
                allow="encrypted-media"
                loading="lazy">
            </iframe>
            <div class="track-meta">
                <span><i class="fas fa-headphones"></i> 正在播放 · 氛围歌单</span>
                <span><i class="fas fa-music"></i> 今日推荐</span>
            </div>
        </div>

        <!-- 右侧 头像 + 签名 -->
        <div class="avatar-card">
            <!-- 替换为你的头像链接 -->
            <img src="https://api.dicebear.com/7.x/thumbs/svg?seed=Anthony&backgroundColor=f5ede6" alt="avatar" />
            <div class="caption">
                <i class="fas fa-feather-alt"></i> 写代码 · 听风 · 煮咖啡
                <span style="display:inline-block; margin-left:6px;" class="badge-soft">🌿 慢生活</span>
            </div>
            <div style="margin-top:0.3rem; font-size:0.75rem; color:#b7a696;">
                <i class="fas fa-map-pin"></i> 武汉 · 晴
            </div>
        </div>
    </div>

    <!-- ======== 统计卡片 ======== -->
    <div class="stats-grid">
        <div class="stat-card">
            <div class="icon"><i class="fas fa-code"></i></div>
            <div class="info">
                <div class="number">8</div>
                <div class="label">公共仓库</div>
            </div>
        </div>
        <div class="stat-card">
            <div class="icon"><i class="fas fa-star"></i></div>
            <div class="info">
                <div class="number">126</div>
                <div class="label">Star 累积</div>
            </div>
        </div>
        <div class="stat-card">
            <div class="icon"><i class="fas fa-pen-fancy"></i></div>
            <div class="info">
                <div class="number">14</div>
                <div class="label">技术笔记</div>
            </div>
        </div>
        <div class="stat-card">
            <div class="icon"><i class="fas fa-mug-saucer"></i></div>
            <div class="info">
                <div class="number">∞</div>
                <div class="label">咖啡消耗</div>
            </div>
        </div>
    </div>

    <!-- ======== 项目 ======== -->
    <div class="projects">
        <div class="section-title"><i class="fas fa-archive" style="margin-right:8px;"></i> 近期项目</div>
        <div class="project-list">
            <a href="#" class="project-item"><i class="fas fa-robot"></i> Visual-Simulation-OpenCV</a>
            <a href="#" class="project-item"><i class="fas fa-cloud-moon"></i> 天气小站</a>
            <a href="#" class="project-item"><i class="fas fa-palette"></i> 调色板工具</a>
            <a href="#" class="project-item"><i class="fas fa-leaf"></i> 植物笔记</a>
        </div>
    </div>

    <!-- ======== 社交链接 ======== -->
    <div class="social-links">
        <a href="#"><i class="fab fa-github"></i> GitHub</a>
        <a href="#"><i class="fab fa-bilibili"></i> Bilibili</a>
        <a href="#"><i class="fas fa-rss"></i> 博客</a>
        <a href="#"><i class="fas fa-envelope"></i> 邮件</a>
        <a href="#"><i class="fab fa-twitter"></i> Twitter</a>
    </div>

    <!-- ======== 脚注 ======== -->
    <div class="footer-note">
        <i class="fas fa-feather"></i> 保持好奇 · 保持温柔
        <span style="margin:0 6px;">·</span>
        <i class="fas fa-crown" style="opacity:0.3;"></i> 2026
    </div>

</div>

<!-- ===== 打字效果脚本 ===== -->
<script>
    (function() {
        const phrases = [
            'Privet! 🌿',
            'Bonjour! ☕',
            'Konnichiwa! 🌸',
            '你好呀 🍃',
            'Ciallo～ (∠・ω< )⌒★'
        ];
        let idx = 0;
        let charIdx = 0;
        let isDeleting = false;
        const el = document.getElementById('typed-text');
        let timer;

        function type() {
            const current = phrases[idx];
            if (!isDeleting) {
                // 打字
                el.textContent = current.slice(0, charIdx + 1);
                charIdx++;
                if (charIdx === current.length) {
                    isDeleting = true;
                    clearTimeout(timer);
                    timer = setTimeout(type, 2200);
                    return;
                }
                timer = setTimeout(type, 80 + Math.random() * 40);
            } else {
                // 删除
                el.textContent = current.slice(0, charIdx - 1);
                charIdx--;
                if (charIdx === 0) {
                    isDeleting = false;
                    idx = (idx + 1) % phrases.length;
                    clearTimeout(timer);
                    timer = setTimeout(type, 400);
                    return;
                }
                timer = setTimeout(type, 50 + Math.random() * 30);
            }
        }

        // 初始启动
        timer = setTimeout(type, 600);
    })();
</script>

</body>
</html>
