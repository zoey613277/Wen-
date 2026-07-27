<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="theme-color" content="#ffffff">
    <title>WorkStation - 个人工作台</title>
    <link rel="stylesheet" href="css/style.css?v=2.1">
    <link rel="stylesheet" href="css/sidebar.css?v=2.1">
    <link rel="stylesheet" href="css/modules.css?v=2.1">
    <link rel="stylesheet" href="css/responsive.css?v=2.1">
    <link rel="manifest" href="manifest.json">
</head>
<body>
    <!-- 侧边栏 -->
    <nav class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <div class="logo">
                <svg width="32" height="32" viewBox="0 0 32 32">
                    <rect width="32" height="32" rx="8" fill="url(#logo-grad)"/>
                    <text x="16" y="22" text-anchor="middle" fill="white" font-size="18" font-weight="bold">W</text>
                    <defs>
                        <linearGradient id="logo-grad" x1="0" y1="0" x2="32" y2="32">
                            <stop offset="0%" stop-color="#667eea"/>
                            <stop offset="100%" stop-color="#764ba2"/>
                        </linearGradient>
                    </defs>
                </svg>
                <span>WorkStation</span>
            </div>
            <button class="sidebar-toggle" id="sidebarToggle" onclick="toggleSidebar()">
                <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="2">
                    <line x1="3" y1="6" x2="17" y2="6"/><line x1="3" y1="10" x2="17" y2="10"/><line x1="3" y1="14" x2="17" y2="14"/>
                </svg>
            </button>
        </div>
        
        <div class="sidebar-nav" id="sidebarNav">
            <!-- 导航项由JS动态生成 -->
        </div>
        
        <div class="sidebar-footer">
            <button class="add-nav-btn" onclick="showAddNavDialog()">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2">
                    <line x1="8" y1="2" x2="8" y2="14"/><line x1="2" y1="8" x2="14" y2="8"/>
                </svg>
                添加导航
            </button>
        </div>
    </nav>

    <!-- 主内容区 -->
    <main class="main-content" id="mainContent">
        <div class="content-header">
            <h1 id="pageTitle">工作台</h1>
            <div class="header-actions">
                <span class="current-time" id="currentTime"></span>
                <span class="current-date" id="currentDate"></span>
            </div>
        </div>
        <div class="content-body" id="contentBody">
            <!-- 动态内容区域 -->
        </div>
    </main>

    <!-- 添加导航对话框 -->
    <div class="modal-overlay" id="addNavModal" style="display:none;">
        <div class="modal-dialog">
            <h3>添加��航项</h3>
            <input type="text" id="newNavTitle" placeholder="导航名称" class="modal-input">
            <input type="text" id="newNavIcon" placeholder="图标(emoji)" class="modal-input" maxlength="2">
            <div class="modal-actions">
                <button onclick="hideAddNavDialog()" class="btn-secondary">取消</button>
                <button onclick="addNavItem()" class="btn-primary">添加</button>
            </div>
        </div>
    </div>

    <!-- 自定义导航上下文菜单 -->
    <div class="context-menu" id="contextMenu" style="display:none;">
        <div class="context-item" onclick="renameNavItem()">重命名</div>
        <div class="context-item danger" onclick="deleteNavItem()">删除</div>
    </div>

    <script src="js/config.js?v=2.1"></script>
    <script src="js/russian_exam.js?v=2.1"></script>
    <script src="js/sidebar.js?v=2.1"></script>
    <script src="js/modules.js?v=2.1"></script>
    <script src="js/app.js?v=2.1"></script>
</body>
</html>
