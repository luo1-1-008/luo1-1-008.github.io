---
layout: page
title: 马春娟 | 个人主页
permalink: /
---

<!-- 引入图标库 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<style>
    /* === 全局重置与字体 === */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, html {
        height: 100%;
        font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
        background-color: #000;
        color: #fff;
        overflow: hidden; /* 隐藏默认滚动条 */
    }

    /* === 动态星空背景 === */
    .star-bg {
        position: fixed;
        top: 0; left: 0; width: 100%; height: 100%;
        background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
        z-index: -1;
    }
    /* 模拟星星 */
    .stars {
        width: 1px; height: 1px;
        background: transparent;
        box-shadow: 100px 200px #FFF, 400px 600px #FFF, 800px 100px #FFF, 1200px 300px #FFF, 1600px 800px #FFF;
        animation: animStar 50s linear infinite;
    }
    @keyframes animStar { from { transform: translateY(0px); } to { transform: translateY(-2000px); } }

    /* === 左侧导航栏 === */
    .sidebar {
        position: fixed;
        left: 0; top: 0; bottom: 0;
        width: 80px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: rgba(0,0,0,0.5);
        backdrop-filter: blur(5px);
        z-index: 100;
        border-right: 1px solid rgba(255,255,255,0.1);
    }
    .nav-item {
        margin: 20px 0;
        cursor: pointer;
        opacity: 0.5;
        transition: 0.3s;
        text-align: center;
    }
    .nav-item:hover, .nav-item.active { opacity: 1; transform: scale(1.1); color: #00bfff; }
    .nav-text {
        display: block;
        font-size: 12px;
        margin-top: 5px;
        letter-spacing: 1px;
    }

    /* === 全屏滚动容器 === */
    .container {
        height: 100vh;
        transition: transform 1s cubic-bezier(0.645, 0.045, 0.355, 1); /* 平滑滚动效果 */
    }
    section {
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        position: relative;
        padding-left: 80px; /* 给左侧导航留位置 */
    }

    /* === 内容样式设计 === */
    h1 { font-size: 4rem; font-weight: 700; letter-spacing: 5px; text-shadow: 0 0 20px rgba(0,191,255,0.7); margin-bottom: 10px; }
    .subtitle { font-size: 1.5rem; color: #00bfff; margin-bottom: 30px; font-weight: 300; }
    
    /* 卡片样式 */
    .card {
        background: rgba(255, 255, 255, 0.05);
        padding: 40px;
        border-radius: 15px;
        border: 1px solid rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px);
        text-align: left;
        max-width: 900px;
        width: 90%;
        box-shadow: 0 15px 35px rgba(0,0,0,0.5);
        overflow-y: auto; /* 内容过多时可内部滚动 */
        max-height: 80vh;
    }
    
    /* 列表与文本优化 */
    ul { list-style: none; margin-top: 20px; }
    li { margin-bottom: 15px; line-height: 1.6; position: relative; padding-left: 20px; }
    li::before { content: "•"; color: #00bfff; position: absolute; left: 0; font-weight: bold; }
    strong { color: #fff; font-weight: 600; }
    .highlight { color: #00bfff; }
    
    /* 技能标签 */
    .tags-container { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 20px; }
    .tag {
        padding: 8px 16px;
        background: rgba(0, 191, 255, 0.1);
        border: 1px solid #00bfff;
        color: #00bfff;
        border-radius: 20px;
        font-size: 0.9rem;
    }

    /* 底部提示 */
    .scroll-tip {
        position: absolute;
        bottom: 30px;
        animation: bounce 2s infinite;
        opacity: 0.7;
        font-size: 0.8rem;
    }
    @keyframes bounce { 0%, 20%, 50%, 80%, 100% {transform: translateY(0);} 40% {transform: translateY(-10px);} 60% {transform: translateY(-5px);} }

    /* 响应式调整 */
    @media (max-width: 768px) {
        h1 { font-size: 2.5rem; }
        .sidebar { width: 50px; }
        section { padding-left: 50px; }
        .nav-text { display: none; }
        .card { padding: 20px; }
    }
</style>

<!-- 背景层 -->
<div class="star-bg"></div>
<div class="stars"></div>

<!-- 左侧导航 -->
<nav class="sidebar">
    <div class="nav-item active" onclick="scrollToSection(0)">
        <i class="fas fa-user-astronaut fa-lg"></i>
        <span class="nav-text">首页</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(1)">
        <i class="fas fa-route fa-lg"></i>
        <span class="nav-text">历程</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(2)">
        <i class="fas fa-bolt fa-lg"></i>
        <span class="nav-text">能力</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(3)">
        <i class="fas fa-graduation-cap fa-lg"></i>
        <span class="nav-text">教育</span>
    </div>
</nav>

<!-- 滚动容器 -->
<div class="container" id="mainContainer">

    <!-- 第一屏：首页 -->
    <section>
        <h1>马春娟</h1>
        <div class="subtitle">电气工程及其自动化 · AI训练师 · 创意设计者</div>
        <p style="max-width: 600px; text-align: center; line-height: 1.8; color: #ccc;">
            "致力于将电气工程的严谨逻辑与人工智能的创新思维相结合。<br>
            保持谦卑，无限进步，正在从一名新手向专业领域发起冲击。"
        </p>
        <div class="scroll-tip">向下滑动探索 <i class="fas fa-chevron-down"></i></div>
    </section>

    <!-- 第二屏：历程 (经历+成长) -->
    <section>
        <div class="card">
            <h2 style="color:#00bfff; margin-bottom:20px;"><i class="fas fa-history"></i> 实践与成长</h2>
            
            <div style="margin-bottom: 30px;">
                <h3 style="font-size:1.2rem; margin-bottom:10px;">🛠️ 社区志愿服务 | 策划与执行</h3>
                <p style="font-size:0.9rem; color:#aaa; margin-bottom:10px;">2026.07 - 2026.08 | 居住地社区</p>
                <ul>
                    <li><strong>活动策划：</strong>协助落地"诚信教育"暑期主题实践，负责宣传方案策划。</li>
                    <li><strong>视觉设计：</strong>利用 <strong>Photoshop</strong> 独立设计宣传海报与标语，直观传递活动理念。</li>
                    <li><strong>现场执行：</strong>引导青少年及家长互动，独立整理物资并拍摄记录，获社区好评。</li>
                </ul>
            </div>

            <div>
                <h3 style="font-size:1.2rem; margin-bottom:10px;">🌱 个人成长轨迹</h3>
                <ul>
                    <li><strong>自律坚韧：</strong>中学时期保持高度自律，克服干扰专注学业，考入塔里木大学。</li>
                    <li><strong>领导力：</strong>长期担任数学/英语课代表及学习委员，组建互助小组，营造班风。</li>
                    <li><strong>跨界探索：</strong>持续探索人工智能与创意设计交叉领域，立志在电气自动化方向深耕。</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- 第三屏：能力 (技能+证书) -->
    <section>
        <div class="card">
            <h2 style="color:#00bfff; margin-bottom:20px;"><i class="fas fa-microchip"></i> 核心竞争力</h2>
            
            <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
                <div>
                    <h3 style="font-size:1.1rem; margin-bottom:10px; color:#fff;">🤖 人工智能 & 编程</h3>
                    <ul>
                        <li>持有<strong>阿里云达摩院初级AI训练师</strong>认证。</li>
                        <li>具备数据标注、模型训练基础。</li>
                        <li>主动学习 <strong>Python</strong>，用于自动化与数据分析入门。</li>
                    </ul>
                </div>
                <div>
                    <h3 style="font-size:1.1rem; margin-bottom:10px; color:#fff;">🎨 设计 & 办公</h3>
                    <ul>
                        <li>熟练运用 <strong>Photoshop</strong> 进行图像处理与海报设计。</li>
                        <li>掌握视频剪辑（剪映/Premiere），可独立完成短视频制作。</li>
                        <li>系统学习 Office 全套，提升文档处理与数据统计效率。</li>
                    </ul>
                </div>
            </div>

            <div style="margin-top: 30px;">
                <h3 style="font-size:1.1rem; margin-bottom:10px; color:#fff;">🏆 获奖与证书</h3>
                <div class="tags-container">
                    <span class="tag">阿里云AI训练师认证</span>
                    <span class="tag">校级三好学生</span>
                    <span class="tag">校级刻苦奋进奖</span>
                    <span class="tag">三维建模基础</span>
                </div>
            </div>
        </div>
    </section>

    <!-- 第四屏：教育 & 联系 -->
    <section>
        <div class="card">
            <h2 style="color:#00bfff; margin-bottom:20px;"><i class="fas fa-university"></i> 教育背景</h2>
            
            <div style="margin-bottom: 30px;">
                <h3 style="font-size:1.3rem; color:#fff;">塔里木大学</h3>
                <p style="color:#00bfff; margin-bottom: 10px;">电气工程及其自动化 | 本科（2026级）</p>
                <p style="font-size:0.9rem; color:#ccc; line-height:1.6;">
                    <strong>主修课程：</strong>电路原理、模拟电子技术、数字电子技术、自动控制原理、电机与拖动等。<br>
                    <strong>英语能力：</strong>自主学习雅思课程（目标6.5分），阅读与听力模考稳定于6.0-6.5区间。
                </p>
            </div>

            <div style="border-top: 1px solid rgba(255,255,255,0.1); padding-top: 20px;">
                <h3 style="font-size:1.1rem; margin-bottom:15px; color:#fff;">📞 联系方式</h3>
                <p><i class="fas fa-phone"></i> 178-8112-8493</p>
                <p><i class="fas fa-envelope"></i> 3413634863@qq.com</p>
                <p><i class="fab fa-weixin"></i> ma150990</p>
            </div>
        </div>
    </section>

</div>

<script>
    let currentSection = 0;
    const sections = document.querySelectorAll('section');
    const container = document.getElementById('mainContainer');
    const navItems = document.querySelectorAll('.nav-item');
    let isScrolling = false;

    // 监听鼠标滚轮
    window.addEventListener('wheel', (e) => {
        if (isScrolling) return;
        
        if (e.deltaY > 0) {
            if (currentSection < sections.length - 1) {
                currentSection++;
                updateView();
            }
        } else {
            if (currentSection > 0) {
                currentSection--;
                updateView();
            }
        }
    });

    // 点击导航跳转
    function scrollToSection(index) {
        currentSection = index;
        updateView();
    }

    // 更新视图函数
    function updateView() {
        isScrolling = true;
        container.style.transform = `translateY(-${currentSection * 100}vh)`;
        
        navItems.forEach((item, index) => {
            if(index === currentSection) item.classList.add('active');
            else item.classList.remove('active');
        });

        setTimeout(() => { isScrolling = false; }, 1000);
    }
</script>
