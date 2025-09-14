# OpenGram
.
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenGram - Межплатформенная соцсеть</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #fafafa;
            color: #262626;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #dbdbdb;
            background-color: white;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #405DE6;
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }
        
        .search-container {
            display: flex;
            align-items: center;
            background: #efefef;
            border-radius: 8px;
            padding: 10px 16px;
            width: 300px;
        }
        
        .search-container input {
            border: none;
            background: transparent;
            margin-left: 10px;
            width: 100%;
            outline: none;
            font-size: 14px;
        }
        
        .nav-icons {
            display: flex;
            gap: 20px;
        }
        
        .icon {
            font-size: 22px;
            cursor: pointer;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #262626;
        }
        
        .icon:hover {
            color: #405DE6;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 350px;
            gap: 30px;
            margin-top: 30px;
        }
        
        .posts {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .post {
            background: white;
            border: 1px solid #dbdbdb;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
        }
        
        .post-header {
            display: flex;
            align-items: center;
            padding: 14px;
            gap: 12px;
            border-bottom: 1px solid #efefef;
        }
        
        .avatar {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: #405DE6;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 16px;
        }
        
        .post-content {
            width: 100%;
        }
        
        .post-image {
            width: 100%;
            height: auto;
            display: block;
        }
        
        .post-actions {
            padding: 14px;
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #efefef;
        }
        
        .action-buttons {
            display: flex;
            gap: 16px;
        }
        
        .post-likes {
            padding: 0 14px;
            font-weight: bold;
            margin: 8px 0;
            font-size: 14px;
        }
        
        .post-caption {
            padding: 0 14px 14px;
            font-size: 14px;
        }
        
        .post-comments {
            padding: 14px;
            border-top: 1px solid #efefef;
            background: #fafafa;
        }
        
        .comment {
            display: flex;
            margin-bottom: 12px;
            align-items: flex-start;
        }
        
        .comment-avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background: #3897f0;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            flex-shrink: 0;
            font-size: 13px;
        }
        
        .comment-content {
            flex-grow: 1;
        }
        
        .comment-author {
            font-weight: bold;
            font-size: 13px;
            margin-right: 5px;
        }
        
        .add-comment {
            display: flex;
            margin-top: 14px;
        }
        
        .add-comment input {
            flex-grow: 1;
            border: 1px solid #dbdbdb;
            border-radius: 20px;
            padding: 10px 16px;
            outline: none;
            font-size: 14px;
        }
        
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .profile-card {
            background: white;
            border: 1px solid #dbdbdb;
            border-radius: 12px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .profile-avatar {
            width: 85px;
            height: 85px;
            border-radius: 50%;
            background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .profile-info {
            text-align: center;
            margin-bottom: 15px;
        }
        
        .profile-name {
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 5px;
        }
        
        .profile-bio {
            color: #8e8e8e;
            font-size: 14px;
            max-width: 250px;
        }
        
        .profile-stats {
            display: flex;
            gap: 20px;
            margin: 15px 0;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-weight: bold;
            font-size: 16px;
        }
        
        .stat-label {
            font-size: 13px;
            color: #8e8e8e;
        }
        
        .edit-profile-btn {
            padding: 8px 20px;
            border: 1px solid #dbdbdb;
            border-radius: 8px;
            background: transparent;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
            width: 100%;
        }
        
        .edit-profile-btn:hover {
            background: #fafafa;
        }
        
        .suggestions {
            background: white;
            border: 1px solid #dbdbdb;
            border-radius: 12px;
            padding: 20px;
        }
        
        .suggestion-title {
            font-weight: bold;
            margin-bottom: 15px;
            font-size: 16px;
        }
        
        .suggestion-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .suggestion-user {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .follow-btn {
            color: #0095f6;
            font-weight: bold;
            cursor: pointer;
            font-size: 13px;
        }
        
        .follow-btn:hover {
            color: #0056b3;
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #4CAF50;
            color: white;
            padding: 15px 20px;
            border-radius: 8px;
            display: none;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .notification.error {
            background: #f44336;
        }
        
        .active-like {
            color: #ed4956;
        }
        
        .stories {
            display: flex;
            gap: 18px;
            overflow-x: auto;
            padding: 20px 0;
            margin-bottom: 20px;
            scrollbar-width: none;
        }
        
        .stories::-webkit-scrollbar {
            display: none;
        }
        
        .story {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            flex-shrink: 0;
        }
        
        .story-avatar {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-bottom: 8px;
            padding: 3px;
        }
        
        .story-avatar-inner {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #262626;
            font-size: 26px;
        }
        
        .story-username {
            font-size: 13px;
            max-width: 70px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }
        
        .create-post {
            background: white;
            border: 1px solid #dbdbdb;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 25px;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }
        
        .create-post textarea {
            width: 100%;
            padding: 14px;
            border: 1px solid #dbdbdb;
            border-radius: 8px;
            resize: none;
            height: 100px;
            font-size: 14px;
        }
        
        .post-options {
            display: flex;
            gap: 15px;
        }
        
        .post-option {
            display: flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
            padding: 10px 16px;
            border-radius: 20px;
            background: #f0f0f0;
            font-size: 14px;
        }
        
        .post-option:hover {
            background: #e0e0e0;
        }
        
        .publish-btn {
            align-self: flex-end;
            padding: 10px 20px;
            background: #405DE6;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
        }
        
        .publish-btn:hover {
            background: #304ac1;
        }
        
        .post-id {
            font-size: 12px;
            color: #8e8e8e;
            margin-top: 12px;
            padding: 8px 0;
            border-top: 1px solid #efefef;
        }
        
        .search-results {
            margin-top: 20px;
            background: white;
            border-radius: 12px;
            border: 1px solid #dbdbdb;
            padding: 20px;
        }
        
        .search-results h3 {
            margin-bottom: 15px;
            font-size: 18px;
        }
        
        .search-help {
            font-size: 14px;
            color: #8e8e8e;
            margin-top: 10px;
        }
        
        .hidden {
            display: none;
        }
        
        .auth-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .auth-container {
            background: white;
            padding: 30px;
            border-radius: 12px;
            width: 400px;
            text-align: center;
        }
        
        .auth-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #dbdbdb;
        }
        
        .auth-tab {
            flex: 1;
            padding: 12px;
            cursor: pointer;
            border-bottom: 2px solid transparent;
        }
        
        .auth-tab.active {
            border-bottom: 2px solid #405DE6;
            font-weight: bold;
        }
        
        .auth-form input {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border: 1px solid #dbdbdb;
            border-radius: 5px;
            font-size: 14px;
        }
        
        .auth-form button {
            width: 100%;
            padding: 12px;
            background: #405DE6;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
        }
        
        .auth-form button:hover {
            background: #304ac1;
        }
        
        .sms-notice {
            font-size: 14px;
            color: #8e8e8e;
            margin-top: 15px;
        }
        
        .no-posts {
            text-align: center;
            padding: 40px;
            background: white;
            border-radius: 12px;
            border: 1px solid #dbdbdb;
        }
        
        .no-posts i {
            font-size: 40px;
            color: #dbdbdb;
            margin-bottom: 15px;
        }
        
        .no-posts p {
            color: #8e8e8e;
            margin-bottom: 20px;
        }
        
        .device-section {
            background: white;
            border-radius: 12px;
            border: 1px solid #dbdbdb;
            padding: 20px;
            margin-bottom: 25px;
        }
        
        .device-title {
            font-weight: bold;
            margin-bottom: 15px;
            font-size: 18px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .device-buttons {
            display: flex;
            gap: 15px;
        }
        
        .device-btn {
            padding: 10px 20px;
            border: 1px solid #dbdbdb;
            border-radius: 8px;
            background: #fafafa;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
            flex: 1;
            text-align: center;
        }
        
        .device-btn.active {
            background: #405DE6;
            color: white;
            border-color: #405DE6;
        }
        
        .device-info {
            margin-top: 15px;
            padding: 15px;
            background: #f9f9f9;
            border-radius: 8px;
            font-size: 14px;
        }
        
        .sync-info {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
            color: #0095f6;
        }
    </style>
</head>
<body>
    <!-- Уведомление -->
    <div class="notification" id="notification"></div>

    <!-- Модальное окно авторизации -->
    <div class="auth-modal" id="authModal">
        <div class="auth-container">
            <div class="auth-tabs">
                <div class="auth-tab active" id="loginTab">Вход</div>
                <div class="auth-tab" id="registerTab">Регистрация</div>
            </div>
            <div class="auth-form">
                <input type="tel" id="phoneInput" placeholder="Номер телефона">
                <div id="smsCodeContainer" style="display: none;">
                    <input type="text" id="smsCodeInput" placeholder="Код из SMS">
                </div>
                <button id="authButton">Продолжить</button>
                <div class="sms-notice" id="smsNotice">Мы отправим SMS с кодом подтверждения на ваш номер</div>
            </div>
        </div>
    </div>

    <div class="container">
        <header>
            <div class="logo" id="homeButton">
                <i class="fas fa-camera"></i>
                <span>OpenGram</span>
            </div>
            <div class="search-container">
                <i class="fas fa-search"></i>
                <input type="text" id="searchInput" placeholder="Поиск по ID поста (например: #OPG-829375)">
            </div>
            <div class="nav-icons">
                <div class="icon" id="homeNavButton"><i class="fas fa-home"></i></div>
                <div class="icon" id="messageButton"><i class="fas fa-paper-plane"></i></div>
                <div class="icon" id="createButton"><i class="fas fa-plus-square"></i></div>
                <div class="icon" id="notificationsButton"><i class="fas fa-heart"></i></div>
                <div class="icon" id="profileButton"><i class="fas fa-user"></i></div>
            </div>
        </header>

        <div class="device-section">
            <div class="device-title">
                <i class="fas fa-mobile-alt"></i>
                <span>Эмуляция работы с разных устройств</span>
            </div>
            <div class="device-buttons">
                <div class="device-btn active" id="thisDeviceBtn">Это устройство</div>
                <div class="device-btn" id="otherDeviceBtn">Другое устройство</div>
            </div>
            <div class="device-info">
                <p>В реальном приложении посты сохраняются на сервере и доступны с любого устройства.</p>
                <p>Здесь вы можете эмулировать работу с другого устройства:</p>
                <div class="sync-info">
                    <i class="fas fa-sync-alt"></i>
                    <span id="syncStatus">Синхронизировано с сервером</span>
                </div>
            </div>
        </div>

        <div class="stories">
            <div class="story">
                <div class="story-avatar">
                    <div class="story-avatar-inner">М</div>
                </div>
                <div class="story-username">Мария</div>
            </div>
            <div class="story">
                <div class="story-avatar">
                    <div class="story-avatar-inner">П</div>
                </div>
                <div class="story-username">Павел</div>
            </div>
            <div class="story">
                <div class="story-avatar">
                    <div class="story-avatar-inner">А</div>
                </div>
                <div class="story-username">Андрей</div>
            </div>
            <div class="story">
                <div class="story-avatar">
                    <div class="story-avatar-inner">К</div>
                </div>
                <div class="story-username">Карина</div>
            </div>
            <div class="story">
                <div class="story-avatar">
                    <div class="story-avatar-inner">Д</div>
                </div>
                <div class="story-username">Дмитрий</div>
            </div>
        </div>

        <div class="main-content">
            <div class="posts-section">
                <div class="create-post">
                    <textarea placeholder="Что у вас нового?" id="postTextarea"></textarea>
                    <div class="post-options">
                        <div class="post-option" id="addPhotoOption"><i class="fas fa-image"></i> Фото</div>
                        <div class="post-option" id="addVideoOption"><i class="fas fa-video"></i> Видео</div>
                        <div class="post-option" id="addShortsOption"><i class="fas fa-film"></i> Shorts</div>
                    </div>
                    <button class="publish-btn" id="publishButton">Опубликовать</button>
                    <div class="post-id">ID поста: #OPG-<span id="generatedId">829375</span> (скопируйте этот ID для поиска)</div>
                </div>

                <div class="posts" id="postsContainer">
                    <!-- Посты будут добавляться здесь -->
                </div>

                <div class="search-results hidden" id="searchResults">
                    <h3>Результаты поиска</h3>
                    <div id="searchResultsContainer"></div>
                    <div class="search-help">Используйте формат #ID (например: #OPG-829375) для поиска постов</div>
                </div>
            </div>

            <div class="sidebar">
                <div class="profile-card">
                    <div class="profile-avatar">В</div>
                    <div class="profile-info">
                        <div class="profile-name">Ваше имя</div>
                        <div class="profile-bio">Добро пожаловать в OpenGram! Здесь вы можете делиться моментами своей жизни.</div>
                    </div>
                    <div class="profile-stats">
                        <div class="stat">
                            <div class="stat-value" id="postsCount">7</div>
                            <div class="stat-label">публикаций</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">347</div>
                            <div class="stat-label">подписчиков</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">189</div>
                            <div class="stat-label">подписок</div>
                        </div>
                    </div>
                    <button class="edit-profile-btn">Редактировать профиль</button>
                </div>

                <div class="suggestions">
                    <div class="suggestion-title">Предложения для вас</div>
                    <div class="suggestion-item">
                        <div class="suggestion-user">
                            <div class="avatar">А</div>
                            <div>
                                <div style="font-weight: bold;">Андрей</div>
                                <div style="font-size: 12px; color: #8e8e8e;">В друзьях у Марии</div>
                            </div>
                        </div>
                        <div class="follow-btn">Подписаться</div>
                    </div>
                    <div class="suggestion-item">
                        <div class="suggestion-user">
                            <div class="avatar">К</div>
                            <div>
                                <div style="font-weight: bold;">Карина</div>
                                <div style="font-size: 12px; color: #8e8e8e;">Популярный блогер</div>
                            </div>
                        </div>
                        <div class="follow-btn">Подписаться</div>
                    </div>
                    <div class="suggestion-item">
                        <div class="suggestion-user">
                            <div class="avatar">Д</div>
                            <div>
                                <div style="font-weight: bold;">Дмитрий</div>
                                <div style="font-size: 12px; color: #8e8e8e;">В друзьях у Павла</div>
                            </div>
                        </div>
                        <div class="follow-btn">Подписаться</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Эмуляция базы данных на сервере (localStorage)
        function getServerDatabase() {
            const serverData = localStorage.getItem('openGramServer');
            return serverData ? JSON.parse(serverData) : {
                posts: [
                    {
                        id: "OPG-829375",
                        username: "Мария",
                        avatar: "М",
                        content: "photo",
                        image: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=600&q=80",
                        likes: 245,
                        caption: "Отличный день на пляже! ☀️ #отдых #море",
                        comments: [
                            {user: "Андрей", text: "Отлично выглядишь!"},
                            {user: "Карина", text: "Классное фото!"}
                        ]
                    },
                    {
                        id: "OPG-472196",
                        username: "Павел",
                        avatar: "П",
                        content: "photo",
                        image: "https://images.unsplash.com/photo-1470229722913-7c0e2dbbafd3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=600&q=80",
                        likes: 189,
                        caption: "Новый трек в студии! 🎸 #музыка #живаямузыка",
                        comments: [
                            {user: "Дмитрий", text: "Было круто!"},
                            {user: "Мария", text: "Жду следующего концерта!"}
                        ]
                    },
                    {
                        id: "OPG-135790",
                        username: "Андрей",
                        avatar: "А",
                        content: "photo",
                        image: "https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=600&q=80",
                        likes: 312,
                        caption: "Восхождение на вершину! 🏔️ #горы #природа",
                        comments: [
                            {user: "Павел", text: "Крутой вид!"},
                            {user: "Дмитрий", text: "Как там наверху?"}
                        ]
                    }
                ],
                users: []
            };
        }

        function saveToServer(data) {
            localStorage.setItem('openGramServer', JSON.stringify(data));
        }

        // Логика для модального окна авторизации
        document.addEventListener('DOMContentLoaded', function() {
            const authModal = document.getElementById('authModal');
            const profileIcon = document.getElementById('profileButton');
            const loginTab = document.getElementById('loginTab');
            const registerTab = document.getElementById('registerTab');
            const smsCodeContainer = document.getElementById('smsCodeContainer');
            const smsNotice = document.getElementById('smsNotice');
            const authButton = document.getElementById('authButton');
            const phoneInput = document.getElementById('phoneInput');
            const searchInput = document.getElementById('searchInput');
            const postsContainer = document.getElementById('postsContainer');
            const searchResults = document.getElementById('searchResults');
            const searchResultsContainer = document.getElementById('searchResultsContainer');
            const notification = document.getElementById('notification');
            const publishButton = document.getElementById('publishButton');
            const homeButton = document.getElementById('homeButton');
            const homeNavButton = document.getElementById('homeNavButton');
            const messageButton = document.getElementById('messageButton');
            const notificationsButton = document.getElementById('notificationsButton');
            const postTextarea = document.getElementById('postTextarea');
            const thisDeviceBtn = document.getElementById('thisDeviceBtn');
            const otherDeviceBtn = document.getElementById('otherDeviceBtn');
            const syncStatus = document.getElementById('syncStatus');
            const postsCount = document.getElementById('postsCount');
            const generatedId = document.getElementById('generatedId');
            
            let currentView = 'thisDevice';
            let serverData = getServerDatabase();
            
            // Показываем модальное окно при загрузке (эмуляция неавторизованного пользователя)
            authModal.style.display = 'flex';
            
            // Заполняем ленту постами
            renderPosts(serverData.posts);
            updatePostsCount();
            
            // Генерируем случайный ID для нового поста
            generatedId.textContent = Math.floor(100000 + Math.random() * 900000);
            
            profileIcon.addEventListener('click', function() {
                authModal.style.display = 'flex';
            });
            
            loginTab.addEventListener('click', function() {
                loginTab.classList.add('active');
                registerTab.classList.remove('active');
                smsNotice.textContent = 'Мы отправим SMS с кодом подтверждения на ваш номер';
            });
            
            registerTab.addEventListener('click', function() {
                registerTab.classList.add('active');
                loginTab.classList.remove('active');
                smsNotice.textContent = 'Мы отправим SMS с кодом подтверждения для регистрации';
            });
            
            authButton.addEventListener('click', function() {
                if (!smsCodeContainer.style.display || smsCodeContainer.style.display === 'none') {
                    // Эмулируем отправку SMS кода
                    const phone = phoneInput.value;
                    if (phone) {
                        smsCodeContainer.style.display = 'block';
                        authButton.textContent = 'Подтвердить';
                        smsNotice.textContent = 'Код отправлен на номер ' + phone;
                    } else {
                        showNotification('Введите номер телефона', 'error');
                    }
                } else {
                    // Эмулируем проверку кода и вход
                    const smsCode = document.getElementById('smsCodeInput').value;
                    if (smsCode === '1234') { // Простой код для демонстрации
                        showNotification('Вход выполнен успешно!');
                        authModal.style.display = 'none';
                    } else {
                        showNotification('Неверный код подтверждения', 'error');
                    }
                }
            });
            
            // Переключение между устройствами
            thisDeviceBtn.addEventListener('click', function() {
                thisDeviceBtn.classList.add('active');
                otherDeviceBtn.classList.remove('active');
                currentView = 'thisDevice';
                syncStatus.textContent = 'Синхронизировано с сервером';
                renderPosts(serverData.posts);
                showNotification('Режим: это устройство');
            });
            
            otherDeviceBtn.addEventListener('click', function() {
                otherDeviceBtn.classList.add('active');
                thisDeviceBtn.classList.remove('active');
                currentView = 'otherDevice';
                syncStatus.textContent = 'Загрузка постов с сервера...';
                
                // Эмуляция загрузки данных с сервера
                setTimeout(() => {
                    syncStatus.textContent = 'Синхронизировано с сервером';
                    renderPosts(serverData.posts);
                    showNotification('Режим: другое устройство. Посты загружены с сервера.');
                }, 1000);
            });
            
            // Поиск по ID
            searchInput.addEventListener('keyup', function(e) {
                if (e.key === 'Enter') {
                    const searchTerm = searchInput.value.trim();
                    
                    if (searchTerm.startsWith('#')) {
                        // Поиск по ID поста
                        const postId = searchTerm.substring(1);
                        const foundPost = serverData.posts.find(post => post.id === postId);
                        
                        if (foundPost) {
                            postsContainer.classList.add('hidden');
                            searchResults.classList.remove('hidden');
                            searchResultsContainer.innerHTML = '';
                            
                            const postElement = createPostElement(foundPost);
                            searchResultsContainer.appendChild(postElement);
                            
                            showNotification('Пост найден!');
                        } else {
                            showNotification('Пост с таким ID не найден', 'error');
                            searchResultsContainer.innerHTML = `
                                <div class="no-posts">
                                    <i class="fas fa-search"></i>
                                    <p>Пост с ID ${searchTerm} не найден</p>
                                    <p>Попробуйте один из этих ID:</p>
                                    <p>#OPG-829375, #OPG-472196, #OPG-135790</p>
                                </div>
                            `;
                        }
                    } else if (searchTerm !== '') {
                        // Поиск по имени пользователя
                        const userPosts = serverData.posts.filter(post => 
                            post.username.toLowerCase().includes(searchTerm.toLowerCase())
                        );
                        
                        if (userPosts.length > 0) {
                            postsContainer.classList.add('hidden');
                            searchResults.classList.remove('hidden');
                            searchResultsContainer.innerHTML = '<h4>Посты пользователя ' + searchTerm + '</h4>';
                            
                            userPosts.forEach(post => {
                                const postElement = createPostElement(post);
                                searchResultsContainer.appendChild(postElement);
                            });
                            
                            showNotification('Найдено ' + userPosts.length + ' постов');
                        } else {
                            showNotification('Пользователь не найден', 'error');
                            searchResultsContainer.innerHTML = `
                                <div class="no-posts">
                                    <i class="fas fa-search"></i>
                                    <p>Пользователь "${searchTerm}" не найден</p>
                                    <p>Попробуйте найти по ID поста, используя #</p>
                                </div>
                            `;
                        }
                    } else {
                        postsContainer.classList.remove('hidden');
                        searchResults.classList.add('hidden');
                    }
                }
            });
            
            // Создание поста
            publishButton.addEventListener('click', function() {
                if (postTextarea.value.trim() === '') {
                    showNotification('Добавьте текст к публикации', 'error');
                    return;
                }
                
                // Создаем новый пост
                const newPost = {
                    id: "OPG-" + generatedId.textContent,
                    username: "Ваше имя",
                    avatar: "В",
                    content: "photo",
                    image: "https://images.unsplash.com/photo-1518791841217-8f162f1e1131?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=600&q=80",
                    likes: 0,
                    caption: postTextarea.value,
                    comments: []
                };
                
                // Добавляем пост в базу данных на "сервере"
                serverData.posts.unshift(newPost);
                saveToServer(serverData);
                
                // Обновляем ленту
                renderPosts(serverData.posts);
                updatePostsCount();
                
                // Генерируем новый ID для следующего поста
                generatedId.textContent = Math.floor(100000 + Math.random() * 900000);
                
                showNotification('Публикация успешно создана! ID: ' + newPost.id);
                postTextarea.value = '';
            });
            
            // Навигация
            homeButton.addEventListener('click', function() {
                postsContainer.classList.remove('hidden');
                searchResults.classList.add('hidden');
                searchInput.value = '';
                showNotification('Главная страница');
            });
            
            homeNavButton.addEventListener('click', function() {
                postsContainer.classList.remove('hidden');
                searchResults.classList.add('hidden');
                searchInput.value = '';
                showNotification('Главная страница');
            });
            
            messageButton.addEventListener('click', function() {
                showNotification('Раздел сообщений');
            });
            
            notificationsButton.addEventListener('click', function() {
                showNotification('Уведомления');
            });
            
            // Функция отображения уведомлений
            function showNotification(message, type = 'success') {
                notification.textContent = message;
                notification.className = type === 'success' ? 'notification' : 'notification error';
                notification.style.display = 'block';
                
                setTimeout(() => {
                    notification.style.display = 'none';
                }, 3000);
            }
            
            // Функция обновления счетчика постов
            function updatePostsCount() {
                postsCount.textContent = serverData.posts.filter(post => post.username === "Ваше имя").length;
            }
            
            // Функция отрисовки постов
            function renderPosts(posts) {
                postsContainer.innerHTML = '';
                
                if (posts.length === 0) {
                    postsContainer.innerHTML = `
                        <div class="no-posts">
                            <i class="fas fa-camera"></i>
                            <p>Пока нет публикаций</p>
                            <p>Создайте первую публикацию!</p>
                        </div>
                    `;
                    return;
                }
                
                posts.forEach(post => {
                    const postElement = createPostElement(post);
                    postsContainer.appendChild(postElement);
                });
            }
            
            // Функция создания элемента поста
            function createPostElement(post) {
                const postElement = document.createElement('div');
                postElement.className = 'post';
                postElement.dataset.id = post.id;
                
                let contentHTML = '';
                if (post.content === 'photo') {
                    contentHTML = `<img src="${post.image}" alt="Post image" class="post-image">`;
                }
                
                postElement.innerHTML = `
                    <div class="post-header">
                        <div class="avatar">${post.avatar}</div>
                        <div>${post.username}</div>
                    </div>
                    <div class="post-content">
                        ${contentHTML}
                    </div>
                    <div class="post-actions">
                        <div class="action-buttons">
                            <span class="icon like-button"><i class="far fa-heart"></i></span>
                            <span class="icon comment-button"><i class="far fa-comment"></i></span>
                            <span class="icon share-button"><i class="far fa-paper-plane"></i></span>
                        </div>
                        <div class="icon save-button"><i class="far fa-bookmark"></i></div>
                    </div>
                    <div class="post-likes">Нравится: <span class="likes-count">${post.likes}</span></div>
                    <div class="post-caption">
                        <strong>${post.username}</strong> ${post.caption}
                    </div>
                    <div class="post-comments">
                        ${post.comments.map(comment => `
                            <div class="comment">
                                <div class="comment-avatar">${comment.user.charAt(0)}</div>
                                <div class="comment-content">
                                    <span class="comment-author">${comment.user}</span> ${comment.text}
                                </div>
                            </div>
                        `).join('')}
                        <div class="add-comment">
                            <input type="text" placeholder="Добавьте комментарий...">
                        </div>
                    </div>
                    <div class="post-id">ID поста: ${post.id}</div>
                `;
                
                // Добавляем обработчик лайков
                const likeButton = postElement.querySelector('.like-button');
                const likesCount = postElement.querySelector('.likes-count');
                
                likeButton.addEventListener('click', function() {
                    const icon = likeButton.querySelector('i');
                    
                    if (icon.classList.contains('far')) {
                        icon.classList.remove('far');
                        icon.classList.add('fas', 'active-like');
                        likesCount.textContent = parseInt(likesCount.textContent) + 1;
                        showNotification('Лайк добавлен!');
                    } else {
                        icon.classList.remove('fas', 'active-like');
                        icon.classList.add('far');
                        likesCount.textContent = parseInt(likesCount.textContent) - 1;
                        showNotification('Лайк удален');
                    }
                });
                
                // Обработчики для других кнопок
                const commentButton = postElement.querySelector('.comment-button');
                const shareButton = postElement.querySelector('.share-button');
                const saveButton = postElement.querySelector('.save-button');
                const commentInput = postElement.querySelector('.add-comment input');
                
                commentButton.addEventListener('click', function() {
                    commentInput.focus();
                    showNotification('Оставьте комментарий');
                });
                
                shareButton.addEventListener('click', function() {
                    showNotification('Поделиться постом: ' + post.id);
                });
                
                saveButton.addEventListener('click', function() {
                    const icon = saveButton.querySelector('i');
                    
                    if (icon.classList.contains('far')) {
                        icon.classList.remove('far');
                        icon.classList.add('fas');
                        showNotification('Пост сохранен');
                    } else {
                        icon.classList.remove('fas');
                        icon.classList.add('far');
                        showNotification('Пост удален из сохраненных');
                    }
                });
                
                commentInput.addEventListener('keyup', function(e) {
                    if (e.key === 'Enter') {
                        if (commentInput.value.trim() !== '') {
                            showNotification('Комментарий добавлен');
                            commentInput.value = '';
                        }
                    }
                });
                
                return postElement;
            }
            
            // Обработчики для кнопок "Подписаться"
            const followButtons = document.querySelectorAll('.follow-btn');
            followButtons.forEach(button => {
                button.addEventListener('click', function() {
                    if (button.textContent === 'Подписаться') {
                        button.textContent = 'Отписаться';
                        showNotification('Вы подписались на пользователя');
                    } else {
                        button.textContent = 'Подписаться';
                        showNotification('Вы отписались от пользователя');
                    }
                });
            });
            
            // Обработчики для сторис
            const stories = document.querySelectorAll('.story');
            stories.forEach(story => {
                story.addEventListener('click', function() {
                    const username = story.querySelector('.story-username').textContent;
                    showNotification(`Просмотр сторис от ${username}`);
                });
            });
        });
    </script>
</body>
</html>
