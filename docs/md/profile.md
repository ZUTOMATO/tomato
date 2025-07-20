<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZUTOMATO - 个人介绍</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #022f7bff;
            --secondary: #10B981;
            --dark: #1F2937;
            --light: #F9FAFB;
            --card-blue: #EFF6FF;
            --card-green: #ECFDF5;
            --card-purple: #F5F3FF;
            --accent: #8B5CF6;
            --bilibili-pink: #FB7299;
            --card-orange: #FFF7ED;
            --card-red: #FEF2F2;
            --card-yellow: #FFFBEB;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Noto Sans SC', sans-serif;
            background: linear-gradient(135deg, #f0f9ff 0%, #e6f7ff 100%);
            min-height: 100vh;
            color: var(--dark);
            padding: 14px;
            font-size: 14px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 14px;
        }
        
        /* 头部样式 */
        .header {
            text-align: center;
            margin-bottom: 24px;
            position: relative;
        }
        
        .header h1 {
            font-size: 2.2rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 6px;
            letter-spacing: -1px;
        }
        
        .header p {
            font-size: 1rem;
            color: #4B5563;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .divider {
            height: 3px;
            width: 70px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 2px;
            margin: 12px auto;
        }
        
        /* 卡片样式 */
        .cards-container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
            margin-bottom: 24px;
        }
        
        @media (min-width: 768px) {
            .cards-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .card {
            background: white;
            border-radius: 14px;
            overflow: hidden;
            box-shadow: 0 6px 16px rgba(0, 0, 0, 0.05);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            z-index: 1;
        }
        
        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 24px rgba(59, 130, 246, 0.15);
        }
        
        .card-header {
            padding: 14px 16px;
            background: linear-gradient(90deg, rgba(59,130,246,0.1) 0%, rgba(59,130,246,0.05) 100%);
            border-bottom: 1px solid rgba(59, 130, 246, 0.1);
            display: flex;
            align-items: center;
        }
        
        .card-header i {
            font-size: 1.1rem;
            color: var(--primary);
            background: rgba(59, 130, 246, 0.15);
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
        }
        
        .card-header h2 {
            font-size: 1.15rem;
            font-weight: 600;
            color: var(--dark);
        }
        
        .card-body {
            padding: 10px;
        }
        
        .info-item {
            display: flex;
            margin-bottom: 14px;
        }
        
        .info-number {
            min-width: 24px;
            height: 24px;
            background: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            font-size: 0.8rem;
            margin-right: 10px;
        }
        
        .info-content h3 {
            font-weight: 600;
            margin-bottom: 3px;
            color: var(--dark);
            font-size: 0.9rem;
        }
        
        .info-content p {
            color: #4B5563;
            line-height: 1.5;
            font-size: 0.85rem;
        }
        
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
        }
        
        @media (min-width: 480px) {
            .contact-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            padding: 10px;
            background: #F9FAFB;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        
        .contact-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.05);
        }
        
        .contact-icon {
            width: 34px;
            height: 34px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            margin-right: 10px;
        }
        
        .contact-info h3 {
            font-size: 0.85rem;
            font-weight: 500;
            color: #6B7280;
        }
        
        .contact-info p {
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--dark);
        }
        
        /* 联系方式卡片字体调整 */
        .contact-card .contact-icon {
            font-size: 1.1rem;
        }
        
        .contact-card .contact-info h3 {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 2px;
        }
        
        .contact-card .contact-info p {
            font-size: 0.85rem;
            font-weight: 500;
            color: #4B5563;
        }
        
        .friend-link-box h3 {
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 5px;
            font-size: 0.9rem;
        }
        
        .friend-link-box p {
            color: #4B5563;
            font-size: 0.8rem;
        }
        
        /* B站账号区域 */
        .accounts-section {
            margin-bottom: 24px;
        }
        
        .section-title {
            font-size: 1.4rem;
            font-weight: 600;
            text-align: center;
            margin-bottom: 20px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 2px;
        }
        
        .accounts-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 14px;
        }
        
        @media (min-width: 640px) {
            .accounts-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .account-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            display: flex;
            padding: 14px;
            text-decoration: none;
            color: inherit;
            position: relative;
        }
        
        .account-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 16px rgba(251, 114, 153, 0.3);
        }
        
        .bilibili-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--bilibili-pink);
            color: white;
            font-size: 0.7rem;
            padding: 3px 8px;
            border-radius: 14px;
            font-weight: 500;
        }
        
        .account-avatar {
            width: 54px;
            height: 54px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--bilibili-pink);
            margin-right: 12px;
            flex-shrink: 0;
            transition: transform 0.3s ease;
        }
        
        .account-card:hover .account-avatar {
            transform: scale(1.05);
        }
        
        .account-name {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 3px;
            color: var(--dark);
        }
        
        .account-desc {
            color: #6B7280;
            font-size: 0.8rem;
            margin-bottom: 6px;
        }
        
        .account-content {
            flex: 1;
        }
        
        .account-stats {
            display: flex;
            gap: 15px;
            margin-top: 5px;
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-number {
            font-weight: 700;
            color: var(--bilibili-pink);
            font-size: 0.9rem;
        }
        
        .stat-label {
            font-size: 0.7rem;
            color: #9CA3AF;
        }
        
        /* 社交图标区域 */
        .social-icons {
            margin-top: 16px;
        }
        
        .social-icons h3 {
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--dark);
            font-size: 0.9rem;
        }
        
        .social-links {
            display: flex;
            gap: 10px;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 38px;
            height: 38px;
            border-radius: 8px;
            background: rgba(31,41,55,0.05);
            color: var(--dark);
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .social-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }
        
        .social-link.github:hover {
            background: #333;
            color: white;
        }
        
        .social-link.bilibili:hover {
            background: var(--bilibili-pink);
            color: white;
        }
        
        .social-link.weibo:hover {
            background: #e6162d;
            color: white;
        }
        
        .social-link.instagram:hover {
            background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
            color: white;
        }
        
        /* 页脚 */
        .footer {
            text-align: center;
            padding: 20px 0;
            color: #6B7280;
            border-top: 1px solid rgba(0, 0, 0, 0.05);
            font-size: 0.85rem;
        }
        
        .footer p {
            margin: 3px 0;
        }
        
        /* 动画效果 */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .animate-card {
            animation: fadeIn 0.5s ease-out forwards;
        }
        
        .card:nth-child(1) { animation-delay: 0.1s; }
        .card:nth-child(2) { animation-delay: 0.2s; }
        .account-card:nth-child(1) { animation-delay: 0.3s; }
        .account-card:nth-child(2) { animation-delay: 0.4s; }
        
        /* 装饰元素 */
        .decoration {
            position: fixed;
            border-radius: 50%;
            opacity: 0.05;
            filter: blur(30px);
            z-index: -1;
        }
        
        .decoration-1 {
            width: 220px;
            height: 220px;
            background: var(--primary);
            top: 10%;
            left: 5%;
        }
        
        .decoration-2 {
            width: 160px;
            height: 160px;
            background: var(--accent);
            bottom: 10%;
            right: 5%;
        }
        
        .decoration-3 {
            width: 100px;
            height: 100px;
            background: var(--secondary);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .bilibili-icon {
            color: var(--bilibili-pink);
            font-size: 1.5rem;
        }
        
        /* 新添加的三个卡片区域 */
        .three-cards-section {
            margin-bottom: 24px;
        }
        
        .three-cards-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
        }
        
        @media (min-width: 768px) {
            .three-cards-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .custom-card {
            background: white;
            border-radius: 14px;
            overflow: hidden;
            box-shadow: 0 6px 16px rgba(0, 0, 0, 0.05);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            z-index: 1;
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .custom-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 24px rgba(59, 130, 246, 0.15);
        }
        
        .card-top {
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .card-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 1.5rem;
        }
        
        .card-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--dark);
        }
        
        .card-subtitle {
            font-size: 0.9rem;
            color: #6B7280;
        }
        
        .card-content {
            padding: 15px 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .card-features {
            margin-bottom: 15px;
            flex-grow: 1;
        }
        
        .feature-item {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            font-size: 0.9rem;
        }
        
        .feature-item i {
            color: var(--primary);
            margin-right: 8px;
            font-size: 0.8rem;
        }
        
        .card-actions {
            margin-top: auto;
            text-align: center;
            padding: 10px 0;
        }
        
        .card-btn {
            display: inline-block;
            padding: 8px 20px;
            background: var(--primary);
            color: white;
            border-radius: 20px;
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .card-btn:hover {
            background: #032060ff;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(37, 99, 235, 0.2);
        }
        
        /* 卡片颜色变体 */
        .card-orange .card-top {
            background: linear-gradient(135deg, rgba(249, 115, 22, 0.1) 0%, rgba(253, 186, 116, 0.1) 100%);
        }
        
        .card-orange .card-icon {
            background: rgba(249, 115, 22, 0.15);
            color: #F97316;
        }
        
        .card-red .card-top {
            background: linear-gradient(135deg, rgba(239, 68, 68, 0.1) 0%, rgba(252, 165, 165, 0.1) 100%);
        }
        
        .card-red .card-icon {
            background: rgba(239, 68, 68, 0.15);
            color: #EF4444;
        }
        
        .card-blue .card-top {
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.1) 0%, rgba(147, 197, 253, 0.1) 100%);
        }
        
        .card-blue .card-icon {
            background: rgba(59, 130, 246, 0.15);
            color: #3B82F6;
        }
    </style>
</head>
<body>
    <!-- 装饰元素 -->
    <div class="decoration decoration-1"></div>
    <div class="decoration decoration-2"></div>
    <div class="decoration decoration-3"></div>
    
    <div class="container">
        <!-- 头部 -->
        <div class="header">
            <h1>ZUTOMATO</h1>
            <p>简单的介绍喵</p>
            <div class="divider"></div>
        </div>
        
        <!-- 卡片区域 -->
        <div class="cards-container">
            <!-- 个人信息卡片 -->
            <div class="card animate-card">
                <div class="card-header">
                    <i class="fas fa-user"></i>
                    <h2>个人信息</h2>
                </div>
                <div class="card-body">
                    <div class="info-item">
                        <div class="info-number">1</div>
                        <div class="info-content">
                            <h3>专业</h3>
                            <p>浙江大学数学科学学院 <br> 23级统计学本科</p>
                        </div>
                    </div>
                    
                    <div class="info-item">
                        <div class="info-number">2</div>
                        <div class="info-content">
                            <h3>原专业</h3>
                            <p>原专业化学，现微辅修<br>也会在这里聊聊一些化学课的体验</p>
                        </div>
                    </div>
                    
                    <div class="info-item">
                        <div class="info-number">3</div>
                        <div class="info-content">
                            <h3>我是TZM</h3>
                            <p>欢迎找我约🏓</p>
                        </div>
                    </div>
                    
                    <div class="info-item">
                        <div class="info-number">4</div>
                        <div class="info-content">
                            <h3>音乐</h3>
                            <p>极端真夜厨<br>乐队键盘手</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- 联系方式卡片 -->
            <div class="card contact-card animate-card">
                <div class="card-header">
                    <i class="fas fa-phone-alt"></i>
                    <h2>我的联系方式</h2>
                </div>
                <div class="card-body">
                    <div class="contact-grid">
                        <div class="contact-item">
                            <div class="contact-icon" style="background: rgba(18, 183, 245, 0.1);">
                                <i class="fab fa-qq" style="color:#12B7F5;"></i>
                            </div>
                            <div class="contact-info">
                                <h3>QQ</h3>
                                <p>2044581717</p>
                            </div>
                        </div><br>
                        
                        <div class="contact-item">
                            <div class="contact-icon" style="background: rgba(7, 193, 96, 0.1);">
                                <i class="fab fa-weixin" style="color:#07C160;"></i>
                            </div>
                            <div class="contact-info">
                                <h3>微信</h3>
                                <p>q2044581717</p>
                            </div>
                        </div><br>
                        
                        <div class="contact-item">
                            <div class="contact-icon" style="background: rgba(59, 130, 246, 0.1);">
                                <i class="fas fa-phone" style="color:#3B82F6;"></i>
                            </div>
                            <div class="contact-info">
                                <h3>电话</h3>
                                <p>19883101612</p>
                            </div>
                        </div><br>
                        
                        <div class="contact-item">
                            <div class="contact-icon" style="background: rgba(235, 64, 52, 0.1);">
                                <i class="fas fa-envelope" style="color:#EB4034;"></i>
                            </div>
                            <div class="contact-info">
                                <h3>邮箱</h3>
                                <p>2044581717@qq.com</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- B站账号区域 -->
        <div class="accounts-section">
            <h2 class="section-title">
<svg t="1753006079260" class="icon" viewBox="0 0 2241 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4787" width="100" height="100"><path d="M626.875127 734.992893c-32.227411-24.430457-68.613198-41.583756-106.038579-56.657868-76.410152-30.148223-156.458883-41.063959-238.067005-38.984772-19.232487 0-38.464975 1.559391-58.217259 2.598985 0-1.559391-1.559391-3.638579-1.559391-6.237563-5.19797-58.217259-11.435533-116.434518-15.593909-173.612183-3.638579-47.82132-5.19797-95.64264-6.237563-143.463959-1.559391-92.004061-1.559391-183.488325-1.559391-275.492386 0-21.831472-1.559391-19.232487-18.192893-11.95533-51.459898 20.791878-102.4 41.063959-153.859898 60.816244C25.989848 93.563452 23.390863 98.761421 24.430457 101.360406c15.593909 58.217259 27.029442 117.993909 34.826396 177.250761 7.796954 51.459898 14.554315 101.360406 21.831472 151.780711 6.237563 44.182741 10.395939 88.365482 15.593909 133.06802 5.19797 45.222335 11.435533 90.44467 16.633503 136.186802 5.19797 43.662944 10.395939 85.766497 15.593909 129.429442 3.638579 31.187817 6.75736 61.855838 9.356345 93.043655 1.559391 24.430457 3.638579 48.860914 4.158376 72.251777 0 5.19797 1.559391 7.796954 6.75736 7.796954 11.435533 0 21.831472 1.559391 32.747208 0 53.019289-5.19797 106.038579-8.836548 158.018274-16.633503 40.024365-6.237563 79.009137-15.593909 117.474112-28.588832 54.57868-18.192893 101.360406-49.380711 146.582741-85.246701 19.232487-14.554315 34.826396-32.227411 41.583756-54.57868C660.142132 780.215228 653.904569 755.264975 626.875127 734.992893L626.875127 734.992893zM327.472081 908.085279c-7.796954-58.217259-15.593909-114.875127-23.390863-171.013198 30.148223 6.75736 156.97868 57.177665 163.216244 64.974619C421.035533 836.873096 375.293401 872.219289 327.472081 908.085279L327.472081 908.085279zM932.515736 763.061929c-2.598985-30.148223-5.19797-61.855838-8.836548-92.004061-3.638579-41.583756-7.796954-83.167513-11.435533-125.271066-3.638579-38.464975-5.19797-76.410152-7.796954-114.875127-3.638579-53.019289-7.796954-106.038579-11.435533-159.057868l-7.796954-117.474112c-1.039594-14.554315-6.75736-18.192893-21.831472-17.153299-18.192893 1.559391-35.86599 2.598985-54.058883 3.638579-15.593909 1.559391-31.187817 3.638579-46.261929 5.19797 46.781726 248.462944 67.573604 497.445685 92.004061 744.349239 28.588832 2.598985 54.57868 4.158376 81.608122 6.75736 5.19797 1.039594 7.796954 0 7.796954-5.19797l-2.598985-28.588832C939.792893 829.076142 936.154315 795.809137 932.515736 763.061929L932.515736 763.061929zM790.091371 794.249746c-3.638579-31.187817-6.75736-61.855838-10.395939-93.043655-3.638579-35.346193-6.75736-71.212183-11.435533-106.558376-2.598985-21.831472-6.237563-42.62335-9.356345-63.415228-1.039594-7.796954-6.237563-11.435533-14.554315-10.395939-14.554315 1.559391-30.148223 1.559391-45.222335 3.638579-20.791878 2.598985-41.583756 6.237563-63.415228 8.836548 25.989848 135.667005 51.979695 268.215228 79.009137 402.84264 31.187817-4.158376 60.816244-7.796954 90.964467-11.435533-1.039594-10.395939-2.598985-20.791878-3.638579-30.148223C797.888325 860.263959 793.729949 826.996954 790.091371 794.249746L790.091371 794.249746zM1100.929949 933.035533c-1.039594-51.459898-2.598985-101.360406-3.638579-152.820305-1.039594-63.415228 0-127.870051 0-191.285279 0-14.034518-1.039594-27.029442-1.559391-41.063959 0-6.237563-3.638579-11.435533-10.395939-11.435533-27.029442-1.039594-54.57868-1.559391-81.608122-1.559391-10.395939 0-19.752284 1.559391-30.148223 3.638579 1.039594 3.638579 1.039594 6.237563 1.039594 8.836548 3.638579 43.662944 7.796954 86.806091 11.435533 129.429442 3.638579 41.583756 7.796954 84.207107 11.435533 125.790863 4.158376 45.222335 7.796954 90.44467 11.95533 135.667005 0 2.598985 4.158376 6.75736 6.75736 6.75736 27.549239 1.039594 56.657868 0 85.766497 0C1100.929949 939.273096 1100.929949 935.634518 1100.929949 933.035533L1100.929949 933.035533zM750.067005 470.936041c-5.19797-49.380711-9.356345-96.162437-14.034518-143.983756-1.039594-6.237563-3.638579-9.356345-8.836548-9.356345-16.633503 0-33.786802 0-51.459898 1.039594 6.75736 53.019289 12.994924 103.959391 19.752284 156.458883C714.720812 473.535025 731.874112 473.015228 750.067005 470.936041L750.067005 470.936041zM1093.132995 478.732995 1093.132995 346.704569c0-9.356345-3.638579-11.95533-11.435533-11.95533l-45.222335 0 0 151.780711c19.752284 1.039594 38.464975 1.559391 56.657868 2.598985L1093.132995 478.732995 1093.132995 478.732995zM673.656853 477.173604l0-10.395939c-2.598985-27.029442-6.237563-53.019289-8.836548-80.048731-1.559391-17.153299-3.638579-33.786802-5.19797-51.459898-1.039594-4.158376 1.039594-10.395939-6.237563-9.356345-16.633503 1.559391-32.747208 5.19797-49.380711 6.75736 9.356345 51.459898 18.192893 101.360406 27.549239 151.780711L673.656853 477.173604 673.656853 477.173604zM1017.762437 486.010152 1017.762437 407.001015c0-20.791878-1.039594-42.62335 0-63.415228 0-7.796954-2.598985-9.356345-9.356345-9.356345l-46.261929 0c4.158376 54.058883 7.796954 104.998985 11.95533 155.419289C988.13401 488.609137 1002.168528 487.569543 1017.762437 486.010152L1017.762437 486.010152zM1017.762437 486.010152" fill="#FB7299" p-id="4788"></path><path d="M1728.84467 734.992893c-32.227411-24.430457-68.613198-41.583756-106.038579-56.657868-76.410152-30.148223-156.458883-41.063959-238.067005-38.984772-19.232487 0-38.464975 1.559391-58.217259 2.598985 0-1.559391-1.559391-3.638579-1.559391-6.237563-5.19797-58.217259-11.435533-116.434518-15.593909-173.612183-3.638579-47.82132-5.19797-95.64264-6.237563-143.463959-1.559391-92.004061-1.559391-183.488325-1.559391-275.492386 0-21.831472-1.559391-19.232487-18.192893-11.95533-51.459898 20.791878-102.4 41.063959-153.859898 60.816244-1.559391 1.039594-4.158376 6.237563-3.638579 8.836548 15.593909 58.217259 27.029442 117.993909 34.826396 177.250761 7.796954 51.459898 14.554315 101.360406 21.831472 151.780711 6.237563 44.182741 10.395939 88.365482 15.593909 133.06802 5.19797 45.222335 11.435533 90.44467 16.633503 136.186802 5.19797 43.662944 10.395939 85.766497 15.593909 129.429442 3.638579 31.187817 6.75736 61.855838 9.356345 93.043655 1.559391 24.430457 3.638579 48.860914 4.158376 72.251777 0 5.19797 1.559391 7.796954 6.75736 7.796954 11.435533 0 21.831472 1.559391 32.747208 0 53.019289-5.19797 106.038579-8.836548 158.018274-16.633503 40.024365-6.237563 79.009137-15.593909 117.474112-28.588832 54.57868-18.192893 101.360406-49.380711 146.582741-85.246701 19.232487-14.554315 34.826396-32.227411 41.583756-54.57868C1762.111675 780.215228 1755.874112 755.264975 1728.84467 734.992893L1728.84467 734.992893zM1429.441624 908.085279c-7.796954-58.217259-15.593909-114.875127-23.390863-171.013198 30.148223 6.75736 156.97868 57.177665 163.216244 64.974619C1523.005076 836.873096 1477.262944 872.219289 1429.441624 908.085279L1429.441624 908.085279zM2034.485279 763.061929c-2.598985-30.148223-5.19797-61.855838-8.836548-92.004061-3.638579-41.583756-7.796954-83.167513-11.435533-125.271066-3.638579-38.464975-5.19797-76.410152-7.796954-114.875127-3.638579-53.019289-7.796954-106.038579-11.435533-159.057868l-7.796954-117.474112c-1.039594-14.554315-6.75736-18.192893-21.831472-17.153299-18.192893 1.559391-35.86599 2.598985-54.058883 3.638579-15.593909 1.559391-31.187817 3.638579-46.261929 5.19797 46.781726 248.462944 67.573604 497.445685 92.004061 744.349239 28.588832 2.598985 54.57868 4.158376 81.608122 6.75736 5.19797 1.039594 7.796954 0 7.796954-5.19797l-2.598985-28.588832C2041.762437 829.076142 2038.123858 795.809137 2034.485279 763.061929L2034.485279 763.061929zM1892.060914 794.249746c-3.638579-31.187817-6.75736-61.855838-10.395939-93.043655-3.638579-35.346193-6.75736-71.212183-11.435533-106.558376-2.598985-21.831472-6.237563-42.62335-9.356345-63.415228-1.039594-7.796954-6.237563-11.435533-14.554315-10.395939-14.554315 1.559391-30.148223 1.559391-45.222335 3.638579-20.791878 2.598985-41.583756 6.237563-63.415228 8.836548 25.989848 135.667005 51.979695 268.215228 79.009137 402.84264 31.187817-4.158376 60.816244-7.796954 90.964467-11.435533-1.039594-10.395939-2.598985-20.791878-3.638579-30.148223C1899.857868 860.263959 1895.699492 826.996954 1892.060914 794.249746L1892.060914 794.249746zM2202.899492 933.035533c-1.039594-51.459898-2.598985-101.360406-3.638579-152.820305-1.039594-63.415228 0-127.870051 0-191.285279 0-14.034518-1.039594-27.029442-1.559391-41.063959 0-6.237563-3.638579-11.435533-10.395939-11.435533-27.029442-1.039594-54.57868-1.559391-81.608122-1.559391-10.395939 0-19.752284 1.559391-30.148223 3.638579 1.039594 3.638579 1.039594 6.237563 1.039594 8.836548 3.638579 43.662944 7.796954 86.806091 11.435533 129.429442 3.638579 41.583756 7.796954 84.207107 11.435533 125.790863 4.158376 45.222335 7.796954 90.44467 11.95533 135.667005 0 2.598985 4.158376 6.75736 6.75736 6.75736 27.549239 1.039594 56.657868 0 85.766497 0C2202.899492 939.273096 2202.899492 935.634518 2202.899492 933.035533L2202.899492 933.035533zM1852.036548 470.936041c-5.19797-49.380711-9.356345-96.162437-14.034518-143.983756-1.039594-6.237563-3.638579-9.356345-8.836548-9.356345-16.633503 0-33.786802 0-51.459898 1.039594 6.75736 53.019289 12.994924 103.959391 19.752284 156.458883C1816.690355 473.535025 1833.843655 473.015228 1852.036548 470.936041L1852.036548 470.936041zM2195.102538 478.732995 2195.102538 346.704569c0-9.356345-3.638579-11.95533-11.435533-11.95533l-45.222335 0 0 151.780711c19.752284 1.039594 38.464975 1.559391 56.657868 2.598985L2195.102538 478.732995 2195.102538 478.732995zM1775.626396 477.173604l0-10.395939c-2.598985-27.029442-6.237563-53.019289-8.836548-80.048731-1.559391-17.153299-3.638579-33.786802-5.19797-51.459898-1.039594-4.158376 1.039594-10.395939-6.237563-9.356345-16.633503 1.559391-32.747208 5.19797-49.380711 6.75736 9.356345 51.459898 18.192893 101.360406 27.549239 151.780711L1775.626396 477.173604 1775.626396 477.173604zM2119.73198 486.010152 2119.73198 407.001015c0-20.791878-1.039594-42.62335 0-63.415228 0-7.796954-2.598985-9.356345-9.356345-9.356345l-46.261929 0c4.158376 54.058883 7.796954 104.998985 11.95533 155.419289C2090.103553 488.609137 2104.138071 487.569543 2119.73198 486.010152L2119.73198 486.010152zM2119.73198 486.010152" fill="#FB7299" p-id="4789"></path></svg>
            </h2>
            
            <div class="accounts-grid">
                <a href="https://space.bilibili.com/567372658?spm_id_from=333.337.0.0" target="_blank" class="account-card animate-card">
                    <div class="bilibili-badge">个人账号</div>
                    <img src="https://s21.ax1x.com/2025/07/19/pV3XuZ9.png" 
                         alt="ZUTOMATO" class="account-avatar">
                    <div class="account-content">
                        <div class="account-name">ZUTOMATO</div>
                        <div class="account-desc">我的个人B站账号</div>
                    </div>
                </a>
                
                <a href="https://space.bilibili.com/3537124613687768" target="_blank" class="account-card animate-card">
                    <div class="bilibili-badge">乐队账号</div>
                    <img src="https://s21.ax1x.com/2025/07/20/pV8Mg8P.png" 
                         alt="LilyPuffer" class="account-avatar">
                    <div class="account-content">
                        <div class="account-name">LilyPuffer</div>
                        <div class="account-desc">我的乐队B站账号</div>
                    </div>
                </a>
            </div>
        </div>
        
        <!-- 新添加的三个卡片区域 -->
        <div class="three-cards-section">
            <h2 class="section-title">
            <div class="logo">
                <img src="https://s21.ax1x.com/2025/07/20/pV8lhkj.png" alt="米哈游" width="120">
            </div>
            </h2>
            
            <div class="three-cards-grid">
                <!-- 音乐卡片 -->
                <div class="custom-card animate-card card-orange">
                    <div class="card-top">
                        <div class="card-icon">
                        <div class="logo">
                            <img src="https://s21.ax1x.com/2025/07/20/pV8lqnU.png" width="120">
                        </div>
                        </div>
                        <h3 class="card-title">○神</h3>
                    </div>
                    <div class="card-content">
                        <div class="card-features">
                            <div class="feature-item">
                                ID：Ginger_Strings<br>
                                UID：230727409
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 学习卡片 -->
                <div class="custom-card animate-card card-red">
                    <div class="card-top">
                        <div class="card-icon">
                            <div class="logo">
                            <img src="https://s21.ax1x.com/2025/07/20/pV8lT10.png" width="120">
                        </div>
                        </div>
                        <h3 class="card-title">崩铁</h3>
                    </div>
                    <div class="card-content">
                        <div class="card-features">
                            <div class="feature-item">
                                ID：ZUTOMATO<br>
                                UID：112136529
                            </div>
                        </div>
                    </div>
                </div>
            </div>        
        <!-- ✅ 独立的新红色卡片 -->
                <div class="three-cards-section">
            <h2 class="section-title">
            <div class="logo">
                <img src="https://s21.ax1x.com/2025/07/20/pV83CPs.png"  width="120">
            </div>
            </h2>
        <div style="max-width: 320px; margin: 24px auto;">
            <div class="custom-card card-blue">
                <div class="card-top">
                    <div class="card-icon">
                            <div class="logo">
                                <img src="https://s21.ax1x.com/2025/07/19/pV3XuZ9.png" width="120">
                            </div>
                        </div>
            <h3 class="card-title">zutomato</h3>
            <p class="card-subtitle">CC98</p>
                    </div>
                    <div class="card-content">
                        <div class="card-actions">
                <a href="http://www-cc98-org-s.webvpn.zju.edu.cn:8001/usercenter" class="card-btn" target="_blank">CC98主页</a>
                        </div>
                </div>
            </div>
        </div>
        <!-- 页脚 -->
        <div class="footer">
            <p>© ZUTOMATO 2025</p>
        </div>

    
    <script>
        // 添加简单的悬停效果
        document.querySelectorAll('.card, .account-card, .custom-card').forEach(card => {
            card.addEventListener('mouseenter', () => {
                card.style.zIndex = '10';
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.zIndex = '1';
            });
        });
        
        // 为B站卡片添加点击效果
        document.querySelectorAll('.account-card').forEach(card => {
            card.addEventListener('click', function(e) {
                if (this.tagName === 'A') {
                    // 如果是链接，正常跳转
                    return true;
                }
                // 否则阻止默认行为
                e.preventDefault();
            });
        });
        
        // 为普通卡片按钮添加点击效果
        document.querySelectorAll('.card-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.preventDefault();
                alert('功能开发中，敬请期待！');
            });
        });
    </script>
</body>
</html>