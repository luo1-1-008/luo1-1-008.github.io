---
layout: page
title: 马春娟的个人主页
permalink: /
---

<style>
    /* 全局科技感样式 */
    body {
        background-color: #0d1117; /* 深色背景 */
        color: #c9d1d9;
        font-family: 'Courier New', Courier, monospace; /* 代码字体 */
    }
    
    /* 主容器 */
    .tech-container {
        max-width: 800px;
        margin: 50px auto;
        padding: 40px;
        background: #161b22;
        border: 1px solid #30363d;
        border-radius: 12px;
        box-shadow: 0 0 20px rgba(0, 255, 255, 0.1); /* 淡淡的蓝光阴影 */
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
    }

    /* 左侧文字区 */
    .content-area {
        flex: 1;
        min-width: 300px;
        padding-right: 20px;
    }

    /* 右侧头像区 */
    .avatar-area {
        flex: 0 0 200px;
        text-align: center;
        margin-bottom: 20px;
    }

    /* 头像样式 - 增加科技光环 */
    .tech-avatar {
        width: 180px;
        height: 180px;
        border-radius: 50%;
        border: 3px solid #58a6ff; /* 科技蓝边框 */
        box-shadow: 0 0 15px rgba(88, 166, 255, 0.6);
        object-fit: cover;
        transition: transform 0.3s ease;
    }
    
    .tech-avatar:hover {
        transform: scale(1.05) rotate(2deg);
    }

    /* 名字样式 */
    h1.name {
        font-size: 2.5em;
        margin-bottom: 10px;
        color: #58a6ff;
        text-shadow: 0 0 5px rgba(88, 166, 255, 0.5);
    }

    /* 标签样式 */
    .tag {
        display: inline-block;
        background: #238636;
        color: white;
        padding: 4px 10px;
        border-radius: 20px;
        font-size: 0.8em;
        margin-right: 10px;
        margin-bottom: 10px;
    }

    /* 列表样式 */
    ul.tech-list {
        list-style: none;
        padding: 0;
    }
    ul.tech-list li {
        margin-bottom: 10px;
        border-left: 3px solid #58a6ff;
        padding-left: 15px;
    }
    
    /* 链接按钮 */
    .btn-tech {
        display: inline-block;
        margin-top: 20px;
        padding: 10px 20px;
        background: transparent;
        border: 1px solid #58a6ff;
        color: #58a6ff;
        text-decoration: none;
        border-radius: 5px;
        transition: all 0.3s;
    }
    .btn-tech:hover {
        background: #58a6ff;
        color: #0d1117;
        box-shadow: 0 0 10px #58a6ff;
    }
</style>

<div class="tech-container">
    
    <!-- 左侧内容 -->
    <div class="content-area">
        <p style="color: #8b949e;">// Hello World, I am</p>
        <h1 class="name">马春娟</h1>
        
        <div style="margin-bottom: 20px;">
            <span class="tag">🎓 塔里木大学</span>
            <span class="tag">⚡ 电气工程及其自动化</span>
            <span class="tag">🐣 大一新生</span>
        </div>

        <p>
            你好！我是一名刚刚踏入大学校园的电气工程专业学生。<br>
            对代码世界充满好奇，正在努力从 "Hello World" 进阶到改变世界。<br>
            喜欢探索新技术，期待在这里记录我的成长轨迹。
        </p>

        <h3 style="border-bottom: 1px dashed #30363d; padding-bottom: 5px; color: #fff;">🛠️ 技能树加载中...</h3>
        <ul class="tech-list">
            <li><strong>编程语言：</strong> C语言 (入门中), Python (探索中)</li>
            <li><strong>专业基础：</strong> 电路原理, 高等数学</li>
            <li><strong>兴趣爱好：</strong> 网页设计, AI绘画, 摄影</li>
        </ul>

        <a href="mailto:你的邮箱@example.com" class="btn-tech">📧 联系我</a>
    </div>

    <!-- 右侧头像 -->
    <div class="avatar-area">
        <!-- 这里的 src 指向你刚才上传的 avatar.jpg -->
        <img src="/assets/img/avatar.jpg" alt="马春娟" class="tech-avatar">
        <p style="font-size: 0.8em; color: #58a6ff; margin-top: 10px;">System Status: Online</p>
    </div>

</div>
