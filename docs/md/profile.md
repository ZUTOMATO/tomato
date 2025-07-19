<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZUTOMATO的介绍</title>
    <script src="https://cdn.tailwindcss.com "></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css ">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#3B82F6',
                        secondary: '#10B981',
                        dark: '#1F2937',
                        light: '#F9FAFB'
                    }
                }
            }
        }
    </script>
    <style>
        .card {
            transition: transform 0.3s ease, box-shadow 0.3s ease, background-color 0.3s ease;
            cursor: pointer;
            overflow: hidden;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .icon-wrapper {
            transition: all 0.3s ease;
        }
        .card:hover .icon-wrapper {
            transform: scale(1.1);
            background-color: rgba(59, 130, 246, 0.2);
        }
        .floating {
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        .pulse {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
        .content-hidden {
            max-height: 0;
            opacity: 0;
            overflow: hidden;
            transition: all 0.4s ease;
        }
        .content-visible {
            max-height: 500px;
            opacity: 1;
        }
    </style>
</head>
<body class="bg-gradient-to-br from-gray-50 to-gray-100 min-h-screen text-dark font-sans antialiased">
    <div class="max-w-6xl mx-auto px-4 py-12">
        <div class="text-center mb-16">
            <h1 class="text-4xl md:text-5xl font-bold bg-gradient-to-r from-primary to-secondary bg-clip-text text-transparent mb-4">
                我的介绍
            </h1>
            <!-- <p class="text-xl text-gray-600 max-w-2xl mx-auto">
               FROM 浙江大学数学科学学院 23 级统计系
            </p> -->
        </div>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

            <!-- 卡片2: 步骤摘要型 -->
            <div class="card bg-gradient-to-br from-white to-blue-50 rounded-xl shadow-lg overflow-hidden border border-blue-100">
                <div class="p-6">
                    <div class="flex items-center mb-4">
                        <h2>ZUTOMATO</h2>
                    </div>
                    <div class="space-y-4 mb-4">
                        <div class="flex items-start">
                            <div class="bg-blue-500 text-white rounded-full w-6 h-6 flex items-center justify-center flex-shrink-0 mr-3 mt-1">
                                <span class="text-xs font-bold">1</span>
                            </div>
                            <p class="text-gray-700">浙江大学数学科学学院</p>
                        </div>
                        <div class="flex items-start">
                            <div class="bg-blue-500 text-white rounded-full w-6 h-6 flex items-center justify-center flex-shrink-0 mr-3 mt-1">
                                <span class="text-xs font-bold">2</span>
                            </div>
                            <p class="text-gray-700">23级统计学</p>
                        </div>
                        <div class="flex items-start">
                            <div class="bg-blue-500 text-white rounded-full w-6 h-6 flex items-center justify-center flex-shrink-0 mr-3 mt-1">
                                <span class="text-xs font-bold">3</span>
                            </div>
                            <p class="text-gray-700">原专业化学，现微辅修</p>
                        </div>

                </div>
            </div>
            
            <!-- 卡片3: 可扩展型 -->
            <div class="card bg-white rounded-xl shadow-lg overflow-hidden">
                <div class="p-6">
                    <div class="flex items-center mb-4">
                        <div class="icon-wrapper bg-green-100 p-3 rounded-full mr-3">
                            <span style="font-size:30px;">☎</span>
                        </div>
                        <h2 class="text-xl font-bold">我的联系方式</h2>
                    </div>
                    <button onclick="toggleContent()" class="w-full bg-green-500 hover:bg-green-600 text-white py-2 px-4 rounded-lg transition-colors duration-300 flex items-center justify-center">
                        <span>显示详细信息</span>
                        <i class="fas fa-chevron-down ml-2 transition-transform duration-300" id="expandIcon"></i>
                    </button>
                </div>
                
                <div class="content-hidden" id="extraContent">
                    <div class="border-t border-gray-200 p-6 bg-gray-50">
                        <h3 class="font-semibold text-lg mb-3">联系方式</h3>
                        <ul class="space-y-2 text-gray-700">
                            <li class="flex items-start">
                                <i class="fas fa-check-circle text-green-500 mt-1 mr-2"></i>
                                <i class="fab fa-qq" style="font-size:25px; color:#12B7F5;"></i>
                                <span>&nbsp2044581717</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fas fa-check-circle text-green-500 mt-1 mr-2"></i>
                                <i class="fab fa-weixin" style="font-size:25px; color:#07C160;"></i>
                                <span>&nbspq2044581717</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fas fa-check-circle text-green-500 mt-1 mr-2"></i>
                                <i class="fas fa-phone" style="font-size:25px; color:#333;"></i>
                                <span>&nbsp19883101612</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    <script>
        function toggleContent() {
            const content = document.getElementById('extraContent');
            const icon = document.getElementById('expandIcon');
            
            content.classList.toggle('content-hidden');
            content.classList.toggle('content-visible');
            
            if (content.classList.contains('content-visible')) {
                icon.classList.remove('fa-chevron-down');
                icon.classList.add('fa-chevron-up');
            } else {
                icon.classList.remove('fa-chevron-up');
                icon.classList.add('fa-chevron-down');
            }
        }
        
        document.querySelectorAll('.card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.zIndex = '10';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.zIndex = '1';
            });
        });
    </script>
</body>
</html>