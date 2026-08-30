---
layout: page
title: 马春娟 | 个人主页
permalink: /
---

<!-- 引入图标库 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<style>
    /* === 1. 全局重置：确保没有默认边距 === */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    body, html {
        height: 100%;
        width: 100%;
        font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
        background-color: #050505; /* 深黑背景 */
        color: #ffffff;
        overflow: hidden; /* 关键：禁止出现滚动条，由JS控制翻页 */
    }

    /* === 2. 动态星空背景（铺满全屏） === */
    .star-bg {
        position: fixed;
        top: 0; left: 0; 
        width: 100vw; height: 100vh; /* 强制占满视口 */
        background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
        z-index: -1;
    }
    
    /* 简单的星星动画 */
    .stars {
        position: fixed;
        top: 0; left: 0; width: 100%; height: 100%;
        background: transparent;
        z-index: -1;
        box-shadow: 
            10vw 10vh #fff, 20vw 50vh #fff, 80vw 10vh #fff, 
            50vw 80vh #fff, 90vw 90vh #fff, 30vw 30vh #fff;
        opacity: 0.5;
        animation: moveStars 100s linear infinite;
    }
    @keyframes moveStars { from { transform: translateY(0); } to { transform: translateY(-100vh); } }

    /* === 3. 左侧导航栏（电脑版显示，手机版优化） === */
    .sidebar {
        position: fixed;
        left: 0; top: 0; bottom: 0;
        width: 100px; /* 稍微宽一点，显得大气 */
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: rgba(0,0,0,0.3); /* 半透明 */
        backdrop-filter: blur(5px);
        z-index: 100;
        border-right: 1px solid rgba(255,255,255,0.05);
    }
    
    .nav-item {
        margin: 25px 0;
        cursor: pointer;
        opacity: 0.4;
        transition: all 0.3s ease;
        text-align: center;
        width: 100%;
    }
    
    .nav-item:hover, .nav-item.active { 
        opacity: 1; 
        transform: translateX(5px); /* 悬停时微微右移 */
        color: #00bfff; /* 科技蓝高亮 */
    }
    
    .nav-item i { font-size: 24px; display: block; margin-bottom: 5px; }
    .nav-text { font-size: 12px; letter-spacing: 1px; display: block; }

    /* === 4. 核心容器：解决“偏左”问题的关键 === */
    .container {
        height: 100vh;
        width: 100vw;
        transition: transform 0.8s cubic-bezier(0.645, 0.045, 0.355, 1);
    }

    section {
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center; /* 垂直居中 */
        align-items: center;     /* 水平居中 */
        position: relative;
        padding-left: 100px; /* 给左侧导航留出空间，但内容本身是居中的 */
    }

    /* === 5. 内容卡片样式（玻璃拟态） === */
    .content-box {
        background: rgba(255, 255, 255, 0.03);
        border: 1px solid rgba(255, 255, 255, 0.1);
        padding: 50px;
        border-radius: 20px;
        max-width: 800px; /* 限制最大宽度，防止在大屏上拉太长 */
        width: 90%;       /* 手机上占满，电脑上适中 */
        text-align: center;
        box-shadow: 0 20px 50px rgba(0,0,0,0.5);
        backdrop-filter: blur(10px);
        animation: fadeIn 1s ease-out;
    }

    h1 { font-size: 4rem; margin-bottom: 10px; text-shadow: 0 0 15px rgba(0,191,255,0.5); }
    h2 { font-size: 1.5rem; color: #00bfff; margin-bottom: 30px; letter-spacing: 2px; text-transform: uppercase; }
    p { font-size: 1.1rem; line-height: 1.8; color: #ddd; margin-bottom: 20px; }
    
    ul { list-style: none; text-align: left; display: inline-block; }
    li { margin-bottom: 15px; position: relative; padding-left: 25px; }
    li::before {
        content: '➤';
        position: absolute;
        left: 0;
        color: #00bfff;
    }

    .tag {
        display: inline-block;
        padding: 8px 16px;
        margin: 5px;
        border: 1px solid rgba(255,255,255,0.3);
        border-radius: 30px;
        font-size: 0.9rem;
        transition: 0.3s;
    }
    .tag:hover { background: #00bfff; color: #000; border-color: #00bfff; }

    /* === 6. 手机端适配（媒体查询） === */
    @media (max-width: 768px) {
        .sidebar { width: 60px; } /* 导航变窄 */
        section { padding-left: 60px; }
        .nav-text { display: none; } /* 手机隐藏文字 */
        h1 { font-size: 2.5rem; }
        .content-box { padding: 30px 20px; width: 95%; }
    }

    @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
</style>

<!-- 背景层 -->
<div class="star-bg"></div>
<div class="stars"></div>

<!-- 左侧导航 -->
<nav class="sidebar">
    <div class="nav-item active" onclick="scrollToSection(0)">
        <i class="fas fa-user-astronaut"></i>
        <span class="nav-text">首页</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(1)">
        <i class="fas fa-route"></i>
        <span class="nav-text">历程</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(2)">
        <i class="fas fa-bolt"></i>
        <span class="nav-text">能力</span>
    </div>
    <div class="nav-item" onclick="scrollToSection(3)">
        <i class="fas fa-graduation-cap"></i>
        <span class="nav-text">教育</span>
    </div>
</nav>

<!-- 滚动容器 -->
<div class="container" id="mainContainer">

    <!-- 第一屏：首页 -->
    <section>
        <div class="content-box" style="border:none; background:transparent; box-shadow:none;">
            <h1>马春娟</h1>
            <h2>塔里木大学 · 电气工程及其自动化</h2>
            <p style="font-size: 1.3rem; color: #fff;">保持谦卑，无限进步。<br>一名正在向未来发起冲击的大一新生。</p>
            <div style="margin-top: 40px;">
                <a href="mailto:3413634863@qq.com" class="tag" style="text-decoration:none; color:#fff;">联系我</a>
            </div>
        </div>
    </section>

    <!-- 第二屏：历程 -->
    <section>
        <div class="content-box">
            <h2><i class="fas fa-history"></i> 实践与成长</h2>
            <p style="color:#aaa; font-size:0.9rem;">WHERE TO ADVANCE</p>
            <ul>
                <li><strong>2026.07 - 2026.08 | 社区志愿服务</strong><br>
                <span style="font-size:0.9rem; color:#bbb;">协助策划“诚信教育”活动，利用PS设计海报，独立整理物资并拍摄记录。</span></li>
                <li><strong>高中时期 | 自律与领导</strong><br>
                <span style="font-size:0.9rem; color:#bbb;">长期担任数学/英语课代表，组建互助小组，保持高度自律考入塔里木大学。</span></li>
            </ul>
        </div>
    </section>

    <!-- 第三屏：能力 -->
    <section>
        <div class="content-box">
            <h2><i class="fas fa-microchip"></i> 核心技能</h2>
            <p style="color:#aaa; font-size:0.9rem;">WHAT TO MASTER</p>
            <div style="margin-top: 20px;">
                <span class="tag"><i class="fas fa-robot"></i> AI训练师认证</span>
                <span class="tag"><i class="fas fa-paint-brush"></i> PS海报设计</span>
                <span class="tag"><i class="fas fa-video"></i> 视频剪辑</span>
                <span class="tag"><i class="fab fa-python"></i> Python入门</span>
                <span class="tag"><i class="fas fa-cube"></i> 三维建模基础</span>
                <span class="tag"><i class="fas fa-file-excel"></i> Office办公</span>
            </div>
            <p style="margin-top: 30px; font-style: italic;">"不仅懂电路，更懂如何用设计和AI赋能工程。"</p>
        </div>
    </section>

    <!-- 第四屏：教育 -->
    <section>
        <div class="content-box">
            <h2><i class="fas fa-university"></i> 教育背景</h2>
            <p style="color:#aaa; font-size:0.9rem;">WHEN TO STUDY</p>
            <div style="text-align: left; margin-top: 20px;">
                <h3 style="color:#fff; margin-bottom:10px;">塔里木大学 <span style="font-size:0.8rem; font-weight:normal; color:#00bfff;">本科在读</span></h3>
                <p style="font-size: 0.95rem; margin-bottom: 10px;"><strong>专业：</strong> 电气工程及其自动化 (2026级)</p>
                <p style="font-size: 0.95rem;"><strong>主修课程：</strong> 电路原理、模电/数电、自动控制原理、电机与拖动。</p>
                <p style="font-size: 0.95rem;"><strong>自学计划：</strong> 正在系统进修Office全套及雅思课程。</p>
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
        // 核心修改：使用 vh 单位确保移动距离准确
        container.style.transform = `translateY(-${currentSection * 100}vh)`;
        
        navItems.forEach((item, index) => {
            if(index === currentSection) item.classList.add('active');
            else item.classList.remove('active');
        });

        setTimeout(() => { isScrolling = false; }, 1000);
    }
</script>
