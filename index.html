<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>照片上传工具</title>
    <!-- 引入Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入Font Awesome -->
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <!-- 配置Tailwind自定义颜色和字体 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#3B82F6',
                        secondary: '#10B981',
                        neutral: '#64748B',
                    },
                    fontFamily: {
                        inter: ['Inter', 'system-ui', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <!-- 自定义工具类 -->
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .upload-shadow {
                box-shadow: 0 10px 25px -5px rgba(59, 130, 246, 0.1), 0 8px 10px -6px rgba(59, 130, 246, 0.1);
            }
            .upload-hover {
                transition: all 0.3s ease;
            }
            .upload-hover:hover {
                transform: translateY(-5px);
                box-shadow: 0 20px 25px -5px rgba(59, 130, 246, 0.1), 0 10px 10px -5px rgba(59, 130, 246, 0.04);
            }
        }
    </style>
</head>
<body class="bg-gray-50 font-inter min-h-screen">
    <!-- 页面容器 -->
    <div class="container mx-auto px-4 py-12 max-w-5xl">
        <!-- 页面标题 -->
        <header class="text-center mb-12">
            <h1 class="text-[clamp(2rem,5vw,3rem)] font-bold text-gray-800 mb-4">
                <i class="fa fa-upload text-primary mr-3"></i>照片上传工具
            </h1>
            <p class="text-neutral text-lg max-w-2xl mx-auto">
                上传你的照片，支持拖放或点击选择文件。上传后可以预览图片并查看文件信息。
            </p>
        </header>
        <!-- 主要内容区 -->
        <main>
            <!-- 上传区域 -->
            <div id="upload-container" class="bg-white rounded-2xl p-8 mb-10 upload-shadow upload-hover">
                <!-- 拖放区域 -->
                <div id="drop-area" class="border-2 border-dashed border-gray-300 rounded-xl p-10 text-center cursor-pointer transition-all duration-300 hover:border-primary">
                    <div class="upload-icon mb-4 text-6xl text-primary">
                        <i class="fa fa-cloud-upload"></i>
                    </div>
                    <h2 class="text-xl font-semibold text-gray-800 mb-2">拖放照片到这里</h2>
                    <p class="text-neutral mb-6">或者点击选择文件上传</p>
                    <!-- 隐藏的文件输入 -->
                    <input type="file" id="file-input" accept="image/*" class="hidden" multiple>
                    <!-- 上传按钮 -->
                    <button id="upload-btn" class="bg-primary hover:bg-primary/90 text-white font-medium py-3 px-8 rounded-lg transition-all duration-300 focus:outline-none focus:ring-2 focus:ring-primary/50">
                        <i class="fa fa-picture-o mr-2"></i>选择照片
                    </button>
                </div>
                <!-- 上传进度条 (默认隐藏) -->
                <div id="progress-container" class="mt-6 hidden">
                    <div class="flex justify-between text-sm mb-1">
                        <span id="progress-filename" class="text-gray-700"></span>
                        <span id="progress-percent" class="text-primary font-medium">0%</span>
                    </div>
                    <div class="w-full bg-gray-200 rounded-full h-2.5">
                        <div id="progress-bar" class="bg-primary h-2.5 rounded-full transition-all duration-300" style="width: 0%"></div>
                    </div>
                </div>
            </div>
            <!-- 预览区域 (默认隐藏) -->
            <div id="preview-container" class="hidden">
                <h2 class="text-2xl font-bold text-gray-800 mb-6 flex items-center">
                    <i class="fa fa-images text-primary mr-2"></i>照片预览
                </h2>
                <!-- 预览网格 -->
                <div id="preview-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- 预览内容将通过JavaScript动态添加 -->
                </div>
            </div>
            <!-- 没有照片时的提示 (默认隐藏) -->
            <div id="no-photos" class="hidden text-center py-16">
                <div class="text-neutral text-5xl mb-4">
                    <i class="fa fa-camera"></i>
                </div>
                <p class="text-neutral text-lg">还没有上传任何照片</p>
            </div>
        </main>
        <!-- 页脚 -->
        <footer class="mt-16 text-center text-neutral text-sm">
            <p>照片上传工具 &copy; 2023 | 仅在浏览器中处理，不会上传到服务器</p>
        </footer>
    </div>
    <!-- JavaScript 功能实现 -->
    <script>
        // 获取DOM元素
        const dropArea = document.getElementById('drop-area');
        const fileInput = document.getElementById('file-input');
        const uploadBtn = document.getElementById('upload-btn');
        const progressContainer = document.getElementById('progress-container');
        const progressBar = document.getElementById('progress-bar');
        const progressFilename = document.getElementById('progress-filename');
        const progressPercent = document.getElementById('progress-percent');
        const previewContainer = document.getElementById('preview-container');
        const previewGrid = document.getElementById('preview-grid');
        const noPhotos = document.getElementById('no-photos');
        // 点击上传按钮触发文件选择
        uploadBtn.addEventListener('click', () => {
            fileInput.click();
        });
        // 处理文件选择
        fileInput.addEventListener('change', (e) => {
            handleFiles(e.target.files);
        });
        // 拖放功能
        ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
            dropArea.addEventListener(eventName, preventDefaults, false);
        });
        function preventDefaults(e) {
            e.preventDefault();
            e.stopPropagation();
        }
        ['dragenter', 'dragover'].forEach(eventName => {
            dropArea.addEventListener(eventName, highlight, false);
        });
        ['dragleave', 'drop'].forEach(eventName => {
            dropArea.addEventListener(eventName, unhighlight, false);
        });
        function highlight() {
            dropArea.classList.add('border-primary');
            dropArea.classList.add('bg-blue-50');
        }
        function unhighlight() {
            dropArea.classList.remove('border-primary');
            dropArea.classList.remove('bg-blue-50');
        }
        // 处理拖放的文件
        dropArea.addEventListener('drop', (e) => {
            const dt = e.dataTransfer;
            const files = dt.files;
            handleFiles(files);
        });
        // 处理上传的文件
        function handleFiles(files) {
            // 过滤非图片文件
            const imageFiles = Array.from(files).filter(file => file.type.startsWith('image/'));
            if (imageFiles.length === 0) {
                alert('请选择图片文件（JPG、PNG等格式）');
                return;
            }
            // 显示预览区域，隐藏无照片提示
            previewContainer.classList.remove('hidden');
            noPhotos.classList.add('hidden');
            // 处理每个图片文件
            imageFiles.forEach((file, index) => {
                // 模拟上传进度
                simulateUploadProgress(file, index, imageFiles.length);
                // 读取文件并显示预览
                const reader = new FileReader();
                reader.onload = function(e) {
                    // 创建预览元素
                    const previewItem = document.createElement('div');
                    previewItem.className = 'bg-white rounded-xl overflow-hidden shadow-md transition-all duration-300 hover:shadow-lg';
                    // 获取图片尺寸信息
                    const img = new Image();
                    img.src = e.target.result;
                    img.onload = function() {
                        // 创建预览内容
                        previewItem.innerHTML = `
                            <div class="relative pb-[75%]">
                                <img src="${e.target.result}" alt="预览图" class="absolute inset-0 w-full h-full object-cover">
                                <button class="delete-btn absolute top-2 right-2 bg-red-500 text-white rounded-full p-1.5 opacity-0 hover:opacity-100 transition-opacity">
                                    <i class="fa fa-times"></i>
                                </button>
                            </div>
                            <div class="p-4">
                                <h3 class="font-medium text-gray-800 truncate mb-1">${file.name}</h3>
                                <div class="flex justify-between text-sm text-neutral">
                                    <span>${img.width} × ${img.height}</span>
                                    <span>${formatFileSize(file.size)}</span>
                                </div>
                            </div>
                        `;
                        // 添加到预览网格
                        previewGrid.appendChild(previewItem);
                        // 删除按钮功能
                        const deleteBtn = previewItem.querySelector('.delete-btn');
                        deleteBtn.addEventListener('click', () => {
                            previewItem.classList.add('scale-95', 'opacity-0');
                            setTimeout(() => {
                                previewItem.remove();
                                // 检查是否还有预览项
                                if (previewGrid.children.length === 0) {
                                    previewContainer.classList.add('hidden');
                                    noPhotos.classList.remove('hidden');
                                }
                            }, 300);
                        });
                    };
                }; 
                // 读取文件为DataURL
                reader.readAsDataURL(file);
            });
        }
        // 模拟上传进度
        function simulateUploadProgress(file, index, total) {
            // 每个文件延迟处理，避免进度条冲突
            setTimeout(() => {
                let progress = 0;
                progressContainer.classList.remove('hidden');
                progressFilename.textContent = file.name;
                const interval = setInterval(() => {
                    progress += Math.random() * 10;
                    if (progress >= 100) {
                        progress = 100;
                        clearInterval(interval);
                        // 如果是最后一个文件，延迟隐藏进度条
                        if (index === total - 1) {
                            setTimeout(() => {
                                progressContainer.classList.add('hidden');
                            }, 1000);
                        }
                    }
                    progressBar.style.width = `${progress}%`;
                    progressPercent.textContent = `${Math.round(progress)}%`;
                }, 100);
            }, index * 500);
        }
        // 格式化文件大小
        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB', 'GB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + ' ' + sizes[i];
        }
        // 初始化页面显示无照片提示
        window.addEventListener('load', () => {
            noPhotos.classList.remove('hidden');
        });
    </script>
</body>
</html>
