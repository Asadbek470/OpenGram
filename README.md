# OpenGram
.
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FaceXI - Социальная сеть с синхронизацией</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #1877f2;
            --secondary: #42b72a;
            --bg-color: #f0f2f5;
            --card-bg: #ffffff;
            --text-primary: #050505;
            --text-secondary: #65676b;
            --border: #dddfe2;
        }
        
        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background-color: var(--card-bg);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 24px;
            font-weight: bold;
            color: var(--primary);
            cursor: pointer;
        }
        
        .logo i {
            margin-right: 8px;
        }
        
        .search-bar {
            flex: 0 1 680px;
            margin: 0 20px;
        }
        
        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border-radius: 20px;
            border: 1px solid var(--border);
            background-color: var(--bg-color);
            font-size: 15px;
        }
        
        .nav-icons {
            display: flex;
            gap: 15px;
        }
        
        .nav-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: var(--bg-color);
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .nav-icon.active {
            background-color: var(--primary);
            color: white;
        }
        
        .nav-icon:hover {
            background-color: var(--border);
        }
        
        .nav-icon.active:hover {
            background-color: var(--primary);
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            cursor: pointer;
            background-size: cover;
            background-position: center;
        }
        
        /* Main Content */
        .main-content {
            display: flex;
            margin-top: 20px;
            gap: 20px;
        }
        
        /* Left Sidebar */
        .left-sidebar {
            flex: 0 0 280px;
        }
        
        .sidebar-card {
            background-color: var(--card-bg);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .user-info .avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            background-size: cover;
            background-position: center;
        }
        
        .sidebar-menu {
            list-style: none;
        }
        
        .sidebar-menu li {
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            margin-bottom: 5px;
        }
        
        .sidebar-menu li:hover {
            background-color: var(--bg-color);
        }
        
        .sidebar-menu li.active {
            background-color: var(--bg-color);
            font-weight: bold;
        }
        
        .sidebar-menu li i {
            margin-right: 10px;
            width: 24px;
            text-align: center;
            color: var(--primary);
        }
        
        .shortcuts {
            margin-top: 20px;
        }
        
        .shortcuts h3 {
            font-size: 17px;
            margin-bottom: 10px;
            color: var(--text-secondary);
        }
        
        /* Feed */
        .feed {
            flex: 1;
        }
        
        .create-post {
            background-color: var(--card-bg);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
        }
        
        .post-input {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .post-input .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--secondary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            background-size: cover;
            background-position: center;
        }
        
        .post-input input {
            flex: 1;
            padding: 12px 15px;
            border-radius: 20px;
            border: none;
            background-color: var(--bg-color);
            font-size: 17px;
            cursor: pointer;
        }
        
        .post-actions {
            display: flex;
            justify-content: space-between;
            padding-top: 10px;
            border-top: 1px solid var(--border);
        }
        
        .post-action {
            display: flex;
            align-items: center;
            padding: 8px 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .post-action:hover {
            background-color: var(--bg-color);
        }
        
        .post-action i {
            margin-right: 8px;
            font-size: 20px;
        }
        
        .photo-video i { color: #45bd62; }
        .feeling i { color: #f7b928; }
        
        /* Stories */
        .stories {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            overflow-x: auto;
            padding: 10px 0;
        }
        
        .story {
            flex: 0 0 120px;
            height: 200px;
            border-radius: 10px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
            cursor: pointer;
        }
        
        .story-bg {
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            transition: transform 0.3s;
        }
        
        .story:hover .story-bg {
            transform: scale(1.05);
        }
        
        .story-user {
            position: absolute;
            top: 10px;
            left: 10px;
            color: white;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
        }
        
        .create-story {
            background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.6));
        }
        
        .create-story .plus {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
            border: 4px solid var(--card-bg);
        }
        
        .create-story .text {
            position: absolute;
            bottom: 10px;
            left: 0;
            width: 100%;
            text-align: center;
            color: white;
            font-weight: bold;
        }
        
        /* Posts */
        .post {
            background-color: var(--card-bg);
            border-radius: 8px;
            margin-bottom: 20px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
        }
        
        .post-header {
            display: flex;
            align-items: center;
            padding: 15px;
        }
        
        .post-header .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            background-size: cover;
            background-position: center;
        }
        
        .post-user {
            flex: 1;
        }
        
        .post-user .name {
            font-weight: 600;
        }
        
        .post-user .time {
            font-size: 13px;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
        }
        
        .post-user .time i {
            margin-left: 5px;
        }
        
        .post-content {
            padding: 0 15px 15px;
        }
        
        .post-text {
            margin-bottom: 10px;
        }
        
        .post-image {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 10px;
            max-height: 500px;
            object-fit: cover;
        }
        
        .post-stats {
            display: flex;
            justify-content: space-between;
            padding: 10px 15px;
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
            color: var(--text-secondary);
            font-size: 14px;
        }
        
        .post-actions-row {
            display: flex;
            justify-content: space-around;
            padding: 5px 15px;
        }
        
        .post-action-btn {
            display: flex;
            align-items: center;
            padding: 8px 5px;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
            flex: 1;
            justify-content: center;
        }
        
        .post-action-btn:hover {
            background-color: var(--bg-color);
        }
        
        .post-action-btn i {
            margin-right: 8px;
            font-size: 18px;
        }
        
        .post-action-btn.active {
            color: var(--primary);
        }
        
        .comments {
            padding: 10px 15px;
        }
        
        .comment {
            display: flex;
            margin-bottom: 10px;
        }
        
        .comment .avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background-color: var(--secondary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            flex-shrink: 0;
            background-size: cover;
            background-position: center;
        }
        
        .comment-content {
            background-color: var(--bg-color);
            padding: 8px 12px;
            border-radius: 18px;
            flex: 1;
        }
        
        .comment .name {
            font-weight: 600;
            font-size: 13px;
        }
        
        .comment .text {
            font-size: 14px;
        }
        
        .comment-actions {
            display: flex;
            font-size: 12px;
            color: var(--text-secondary);
            margin-top: 5px;
        }
        
        .comment-action {
            margin-right: 15px;
            cursor: pointer;
        }
        
        .add-comment {
            display: flex;
            margin-top: 10px;
        }
        
        .add-comment input {
            flex: 1;
            padding: 10px 15px;
            border-radius: 20px;
            border: none;
            background-color: var(--bg-color);
            font-size: 14px;
        }
        
        /* Right Sidebar */
        .right-sidebar {
            flex: 0 0 280px;
        }
        
        .contacts h3 {
            font-size: 17px;
            margin-bottom: 10px;
            color: var(--text-secondary);
        }
        
        .contact {
            display: flex;
            align-items: center;
            padding: 8px;
            border-radius: 8px;
            cursor: pointer;
        }
        
        .contact:hover {
            background-color: var(--bg-color);
        }
        
        .contact .avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            background-size: cover;
            background-position: center;
        }
        
        /* Auth Modal */
        .auth-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .auth-content {
            background-color: white;
            border-radius: 8px;
            width: 400px;
            max-width: 90%;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .auth-header {
            padding: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .auth-header h2 {
            font-size: 20px;
        }
        
        .close-auth {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-secondary);
        }
        
        .auth-body {
            padding: 20px;
        }
        
        .auth-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid var(--border);
        }
        
        .auth-tab {
            flex: 1;
            text-align: center;
            padding: 10px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
        }
        
        .auth-tab.active {
            border-bottom: 3px solid var(--primary);
            font-weight: bold;
        }
        
        .auth-form {
            display: none;
        }
        
        .auth-form.active {
            display: block;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }
        
        .form-group input, .form-group select {
            width: 100%;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid var(--border);
            font-size: 15px;
        }
        
        .auth-button {
            width: 100%;
            padding: 12px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
        }
        
        .auth-button:hover {
            background-color: #166fe5;
        }
        
        /* Profile Modal */
        .profile-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .profile-content {
            background-color: white;
            border-radius: 8px;
            width: 500px;
            max-width: 90%;
            max-height: 90%;
            overflow-y: auto;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .profile-header {
            padding: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .profile-header h2 {
            font-size: 20px;
        }
        
        .close-profile {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-secondary);
        }
        
        .profile-body {
            padding: 20px;
        }
        
        .profile-avatar {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .profile-avatar .avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 40px;
            margin-bottom: 10px;
            background-size: cover;
            background-position: center;
        }
        
        .change-avatar {
            color: var(--primary);
            cursor: pointer;
            font-weight: 500;
        }
        
        /* Create Story Modal */
        .story-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .story-content {
            background-color: white;
            border-radius: 8px;
            width: 500px;
            max-width: 90%;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .story-header {
            padding: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .story-header h2 {
            font-size: 20px;
        }
        
        .close-story {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-secondary);
        }
        
        .story-body {
            padding: 20px;
        }
        
        .story-preview {
            width: 100%;
            height: 300px;
            background-color: var(--bg-color);
            border-radius: 8px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            background-size: cover;
            background-position: center;
        }
        
        .story-preview-text {
            color: var(--text-secondary);
        }
        
        .story-actions {
            display: flex;
            gap: 10px;
        }
        
        .story-button {
            flex: 1;
            padding: 10px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }
        
        /* Create Post Modal */
        .post-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .post-content {
            background-color: white;
            border-radius: 8px;
            width: 500px;
            max-width: 90%;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .post-modal-header {
            padding: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .post-modal-header h2 {
            font-size: 20px;
        }
        
        .close-post {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-secondary);
        }
        
        .post-modal-body {
            padding: 20px;
        }
        
        .post-modal-text {
            width: 100%;
            min-height: 100px;
            border: none;
            resize: none;
            font-size: 16px;
            margin-bottom: 15px;
        }
        
        .post-modal-text:focus {
            outline: none;
        }
        
        .post-modal-preview {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 15px;
            display: none;
        }
        
        .post-modal-actions {
            display: flex;
            gap: 10px;
        }
        
        .post-modal-button {
            flex: 1;
            padding: 10px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }
        
        /* Status Message */
        .status-message {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            display: none;
            z-index: 1001;
        }
        
        /* Responsive */
        @media (max-width: 1100px) {
            .left-sidebar {
                flex: 0 0 240px;
            }
            
            .right-sidebar {
                flex: 0 0 240px;
            }
        }
        
        @media (max-width: 900px) {
            .left-sidebar {
                display: none;
            }
            
            .right-sidebar {
                display: none;
            }
            
            .search-bar {
                flex: 0 1 400px;
            }
        }
        
        @media (max-width: 600px) {
            .search-bar {
                display: none;
            }
            
            .nav-icons {
                gap: 10px;
            }
        }
        
        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>
    <!-- Status Message -->
    <div class="status-message" id="statusMessage"></div>
    
    <!-- Auth Modal -->
    <div class="auth-modal" id="authModal">
        <div class="auth-content">
            <div class="auth-header">
                <h2>FaceXI</h2>
                <div class="close-auth" id="closeAuth">&times;</div>
            </div>
            <div class="auth-body">
                <div class="auth-tabs">
                    <div class="auth-tab active" data-tab="login">Вход</div>
                    <div class="auth-tab" data-tab="register">Регистрация</div>
                </div>
                
                <form class="auth-form active" id="loginForm">
                    <div class="form-group">
                        <label for="loginEmail">Email</label>
                        <input type="email" id="loginEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="loginPassword">Пароль</label>
                        <input type="password" id="loginPassword" required>
                    </div>
                    <button type="submit" class="auth-button">Войти</button>
                </form>
                
                <form class="auth-form" id="registerForm">
                    <div class="form-group">
                        <label for="registerName">Имя и фамилия</label>
                        <input type="text" id="registerName" required>
                    </div>
                    <div class="form-group">
                        <label for="registerEmail">Email</label>
                        <input type="email" id="registerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="registerPassword">Пароль</label>
                        <input type="password" id="registerPassword" required>
                    </div>
                    <div class="form-group">
                        <label for="registerBirthday">Дата рождения</label>
                        <input type="date" id="registerBirthday" required>
                    </div>
                    <div class="form-group">
                        <label for="registerGender">Пол</label>
                        <select id="registerGender" required>
                            <option value="">Выберите пол</option>
                            <option value="male">Мужской</option>
                            <option value="female">Женский</option>
                        </select>
                    </div>
                    <button type="submit" class="auth-button">Зарегистрироваться</button>
                </form>
            </div>
        </div>
    </div>
    
    <!-- Profile Modal -->
    <div class="profile-modal" id="profileModal">
        <div class="profile-content">
            <div class="profile-header">
                <h2>Редактирование профиля</h2>
                <div class="close-profile" id="closeProfile">&times;</div>
            </div>
            <div class="profile-body">
                <div class="profile-avatar">
                    <div class="avatar" id="profileAvatarPreview"></div>
                    <div class="change-avatar" id="changeAvatar">Изменить фото профиля</div>
                    <input type="file" id="avatarUpload" accept="image/*" class="hidden">
                </div>
                
                <div class="form-group">
                    <label for="profileName">Имя и фамилия</label>
                    <input type="text" id="profileName">
                </div>
                <div class="form-group">
                    <label for="profileBio">О себе</label>
                    <input type="text" id="profileBio" placeholder="Расскажите о себе">
                </div>
                <div class="form-group">
                    <label for="profileLocation">Местоположение</label>
                    <input type="text" id="profileLocation" placeholder="Где вы живете?">
                </div>
                <button class="auth-button" id="saveProfile">Сохранить изменения</button>
            </div>
        </div>
    </div>
    
    <!-- Create Story Modal -->
    <div class="story-modal" id="storyModal">
        <div class="story-content">
            <div class="story-header">
                <h2>Создать историю</h2>
                <div class="close-story" id="closeStory">&times;</div>
            </div>
            <div class="story-body">
                <div class="story-preview" id="storyPreview">
                    <div class="story-preview-text">Ваша история будет здесь</div>
                </div>
                <input type="file" id="storyUpload" accept="image/*" class="hidden">
                <div class="story-actions">
                    <button class="story-button" id="uploadStoryBtn">Загрузить фото</button>
                    <button class="story-button" id="publishStoryBtn">Опубликовать</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Create Post Modal -->
    <div class="post-modal" id="postModal">
        <div class="post-content">
            <div class="post-modal-header">
                <h2>Создать пост</h2>
                <div class="close-post" id="closePost">&times;</div>
            </div>
            <div class="post-modal-body">
                <textarea class="post-modal-text" id="postText" placeholder="Что у вас нового?"></textarea>
                <img class="post-modal-preview" id="postPreview">
                <input type="file" id="postUpload" accept="image/*" class="hidden">
                <div class="post-modal-actions">
                    <button class="post-modal-button" id="uploadPostImageBtn">Добавить фото</button>
                    <button class="post-modal-button" id="publishPostBtn">Опубликовать</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Header -->
    <header id="mainHeader" class="hidden">
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-globe-americas"></i>
                    <span>FaceXI</span>
                </div>
                
                <div class="search-bar">
                    <input type="text" placeholder="Поиск в FaceXI">
                </div>
                
                <div class="nav-icons">
                    <div class="nav-icon active" data-page="home">
                        <i class="fas fa-home"></i>
                    </div>
                    <div class="nav-icon" data-page="friends">
                        <i class="fas fa-user-friends"></i>
                    </div>
                    <div class="nav-icon" data-page="watch">
                        <i class="fas fa-tv"></i>
                    </div>
                    <div class="nav-icon" data-page="groups">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="nav-icon" data-page="notifications">
                        <i class="fas fa-bell"></i>
                    </div>
                    <div class="user-avatar" id="headerAvatar"></div>
                </div>
            </div>
        </div>
    </header>
    
    <!-- Main Content -->
    <div class="container">
        <div class="main-content" id="mainContent" class="hidden">
            <!-- Left Sidebar -->
            <div class="left-sidebar">
                <div class="sidebar-card">
                    <div class="user-info">
                        <div class="avatar" id="sidebarAvatar"></div>
                        <div class="name" id="sidebarName">Иван Иванов</div>
                    </div>
                    
                    <ul class="sidebar-menu">
                        <li class="active" data-page="home">
                            <i class="fas fa-user-friends"></i>
                            <span>Новости</span>
                        </li>
                        <li data-page="friends">
                            <i class="fas fa-user-friends"></i>
                            <span>Друзья</span>
                        </li>
                        <li data-page="watch">
                            <i class="fas fa-play-circle"></i>
                            <span>Watch</span>
                        </li>
                        <li data-page="groups">
                            <i class="fas fa-users"></i>
                            <span>Группы</span>
                        </li>
                        <li data-page="events">
                            <i class="fas fa-calendar-alt"></i>
                            <span>События</span>
                        </li>
                        <li data-page="memories">
                            <i class="fas fa-history"></i>
                            <span>Воспоминания</span>
                        </li>
                        <li data-page="saved">
                            <i class="fas fa-bookmark"></i>
                            <span>Сохраненное</span>
                        </li>
                        <li id="editProfileBtn">
                            <i class="fas fa-edit"></i>
                            <span>Редактировать профиль</span>
                        </li>
                    </ul>
                </div>
                
                <div class="sidebar-card shortcuts">
                    <h3>Ваши ярлыки</h3>
                    <ul class="sidebar-menu">
                        <li>
                            <i class="fas fa-code" style="color: #1877f2;"></i>
                            <span>Разработчики FaceXI</span>
                        </li>
                        <li>
                            <i class="fas fa-graduation-cap" style="color: #f02849;"></i>
                            <span>Учебная группа</span>
                        </li>
                        <li>
                            <i class="fas fa-gamepad" style="color: #45bd62;"></i>
                            <span>Игровые новости</span>
                        </li>
                    </ul>
                </div>
            </div>
            
            <!-- Feed -->
            <div class="feed">
                <!-- Create Post -->
                <div class="create-post">
                    <div class="post-input">
                        <div class="avatar" id="postInputAvatar"></div>
                        <input type="text" placeholder="Что у вас нового?" id="openPostModal">
                    </div>
                    
                    <div class="post-actions">
                        <div class="post-action photo-video" id="openPostModal2">
                            <i class="fas fa-photo-video"></i>
                            <span>Фото/Видео</span>
                        </div>
                        <div class="post-action feeling" id="openFeelingModal">
                            <i class="fas fa-laugh-beam"></i>
                            <span>Чувства/действия</span>
                        </div>
                    </div>
                </div>
                
                <!-- Stories -->
                <div class="stories" id="storiesContainer">
                    <div class="story" id="createStoryBtn">
                        <div class="story-bg" style="background-color: #f0f2f5;"></div>
                        <div class="create-story">
                            <div class="plus">
                                <i class="fas fa-plus"></i>
                            </div>
                            <div class="text">Создать историю</div>
                        </div>
                    </div>
                    
                    <!-- Stories will be loaded here -->
                </div>
                
                <!-- Posts -->
                <div id="postsContainer">
                    <!-- Posts will be loaded here -->
                </div>
            </div>
            
            <!-- Right Sidebar -->
            <div class="right-sidebar">
                <div class="sidebar-card contacts">
                    <h3>Контакты</h3>
                    
                    <div class="contact">
                        <div class="avatar" style="background-image: url('https://images.unsplash.com/photo-1494790108755-2616b612b786?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60');"></div>
                        <div class="name">Мария Семенова</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-image: url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60');"></div>
                        <div class="name">Андрей Петров</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-image: url('https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60');"></div>
                        <div class="name">Ольга Козлова</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-image: url('https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60');"></div>
                        <div class="name">Дмитрий Иванов</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-image: url('https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60');"></div>
                        <div class="name">Елена Смирнова</div>
                    </div>
                </div>
                
                <div class="sidebar-card">
                    <h3>Группы FaceXI</h3>
                    
                    <div class="contact">
                        <div class="avatar" style="background-color: #f7b928;">Т</div>
                        <div class="name">Путешествия по миру</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-color: #45bd62;">Ф</div>
                        <div class="name">Фотография</div>
                    </div>
                    
                    <div class="contact">
                        <div class="avatar" style="background-color: #1877f2;">П</div>
                        <div class="name">Программирование</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Имитация облачного хранилища
        class CloudStorage {
            constructor() {
                this.storageKey = 'facexi_cloud_data';
                this.init();
            }
            
            init() {
                // Инициализируем облачное хранилище в localStorage
                if (!localStorage.getItem(this.storageKey)) {
                    const initialData = {
                        users: [],
                        posts: [],
                        stories: [],
                        lastUpdate: new Date().toISOString()
                    };
                    localStorage.setItem(this.storageKey, JSON.stringify(initialData));
                }
            }
            
            // Получить все данные
            getAllData() {
                const data = localStorage.getItem(this.storageKey);
                return data ? JSON.parse(data) : null;
            }
            
            // Сохранить все данные
            saveAllData(data) {
                data.lastUpdate = new Date().toISOString();
                localStorage.setItem(this.storageKey, JSON.stringify(data));
                
                // Имитируем синхронизацию с "облаком"
                this.simulateSync();
            }
            
            // Имитация синхронизации между устройствами
            simulateSync() {
                // В реальном приложении здесь был бы запрос к серверу
                console.log('Данные синхронизированы с облаком');
                
                // Показываем сообщение о синхронизации
                this.showStatus('Данные синхронизированы с облаком');
            }
            
            // Показать статус
            showStatus(message) {
                const statusElement = document.getElementById('statusMessage');
                statusElement.textContent = message;
                statusElement.style.display = 'block';
                
                setTimeout(() => {
                    statusElement.style.display = 'none';
                }, 3000);
            }
            
            // Получить пользователей
            getUsers() {
                const data = this.getAllData();
                return data ? data.users : [];
            }
            
            // Сохранить пользователей
            saveUsers(users) {
                const data = this.getAllData();
                data.users = users;
                this.saveAllData(data);
            }
            
            // Получить посты
            getPosts() {
                const data = this.getAllData();
                return data ? data.posts : [];
            }
            
            // Сохранить посты
            savePosts(posts) {
                const data = this.getAllData();
                data.posts = posts;
                this.saveAllData(data);
            }
            
            // Получить истории
            getStories() {
                const data = this.getAllData();
                return data ? data.stories : [];
            }
            
            // Сохранить истории
            saveStories(stories) {
                const data = this.getAllData();
                data.stories = stories;
                this.saveAllData(data);
            }
            
            // Найти пользователя по email
            findUserByEmail(email) {
                const users = this.getUsers();
                return users.find(user => user.email === email);
            }
            
            // Найти пользователя по ID
            findUserById(id) {
                const users = this.getUsers();
                return users.find(user => user.id === id);
            }
            
            // Добавить пользователя
            addUser(user) {
                const users = this.getUsers();
                users.push(user);
                this.saveUsers(users);
                return user;
            }
            
            // Обновить пользователя
            updateUser(updatedUser) {
                const users = this.getUsers();
                const index = users.findIndex(user => user.id === updatedUser.id);
                if (index !== -1) {
                    users[index] = updatedUser;
                    this.saveUsers(users);
                    return true;
                }
                return false;
            }
            
            // Добавить пост
            addPost(post) {
                const posts = this.getPosts();
                posts.unshift(post);
                this.savePosts(posts);
                return post;
            }
            
            // Обновить пост
            updatePost(updatedPost) {
                const posts = this.getPosts();
                const index = posts.findIndex(post => post.id === updatedPost.id);
                if (index !== -1) {
                    posts[index] = updatedPost;
                    this.savePosts(posts);
                    return true;
                }
                return false;
            }
            
            // Добавить историю
            addStory(story) {
                const stories = this.getStories();
                stories.unshift(story);
                this.saveStories(stories);
                return story;
            }
        }
        
        // Данные приложения
        const cloudStorage = new CloudStorage();
        let currentUser = null;
        
        // DOM элементы
        const authModal = document.getElementById('authModal');
        const profileModal = document.getElementById('profileModal');
        const storyModal = document.getElementById('storyModal');
        const postModal = document.getElementById('postModal');
        const mainHeader = document.getElementById('mainHeader');
        const mainContent = document.getElementById('mainContent');
        const postsContainer = document.getElementById('postsContainer');
        const storiesContainer = document.getElementById('storiesContainer');
        
        // Инициализация приложения
        document.addEventListener('DOMContentLoaded', function() {
            // Проверяем, есть ли активный пользователь
            const savedUser = localStorage.getItem('facexi_current_user');
            if (savedUser) {
                const userData = JSON.parse(savedUser);
                // Ищем пользователя в облачном хранилище
                const user = cloudStorage.findUserById(userData.id);
                if (user) {
                    currentUser = user;
                    showMainApp();
                } else {
                    showAuthModal();
                }
            } else {
                showAuthModal();
            }
            
            // Инициализация обработчиков событий
            initEventListeners();
            loadPosts();
            loadStories();
        });
        
        // Показать модальное окно авторизации
        function showAuthModal() {
            authModal.style.display = 'flex';
            mainHeader.classList.add('hidden');
            mainContent.classList.add('hidden');
        }
        
        // Показать основное приложение
        function showMainApp() {
            authModal.style.display = 'none';
            mainHeader.classList.remove('hidden');
            mainContent.classList.remove('hidden');
            updateUserInterface();
        }
        
        // Обновление интерфейса пользователя
        function updateUserInterface() {
            if (!currentUser) return;
            
            // Обновление аватаров
            const avatars = document.querySelectorAll('.avatar, .user-avatar');
            avatars.forEach(avatar => {
                if (currentUser.avatar) {
                    avatar.style.backgroundImage = `url(${currentUser.avatar})`;
                    avatar.textContent = '';
                } else {
                    avatar.style.backgroundImage = '';
                    avatar.textContent = currentUser.name.split(' ').map(n => n[0]).join('');
                }
            });
            
            // Обновление имени
            const nameElements = document.querySelectorAll('.name, #sidebarName');
            nameElements.forEach(element => {
                element.textContent = currentUser.name;
            });
        }
        
        // Инициализация обработчиков событий
        function initEventListeners() {
            // Авторизация
            document.getElementById('closeAuth').addEventListener('click', () => {
                if (!currentUser) return;
                authModal.style.display = 'none';
            });
            
            // Переключение между вкладками авторизации
            document.querySelectorAll('.auth-tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
                    document.querySelectorAll('.auth-form').forEach(f => f.classList.remove('active'));
                    
                    this.classList.add('active');
                    document.getElementById(this.dataset.tab + 'Form').classList.add('active');
                });
            });
            
            // Форма входа
            document.getElementById('loginForm').addEventListener('submit', function(e) {
                e.preventDefault();
                const email = document.getElementById('loginEmail').value;
                const password = document.getElementById('loginPassword').value;
                
                const user = cloudStorage.findUserByEmail(email);
                if (user && user.password === password) {
                    currentUser = user;
                    localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                    showMainApp();
                } else {
                    alert('Неверный email или пароль');
                }
            });
            
            // Форма регистрации
            document.getElementById('registerForm').addEventListener('submit', function(e) {
                e.preventDefault();
                const name = document.getElementById('registerName').value;
                const email = document.getElementById('registerEmail').value;
                const password = document.getElementById('registerPassword').value;
                const birthday = document.getElementById('registerBirthday').value;
                const gender = document.getElementById('registerGender').value;
                
                // Проверяем, есть ли уже пользователь с таким email
                if (cloudStorage.findUserByEmail(email)) {
                    alert('Пользователь с таким email уже существует');
                    return;
                }
                
                const newUser = {
                    id: Date.now(),
                    name,
                    email,
                    password,
                    birthday,
                    gender,
                    avatar: null,
                    bio: '',
                    location: ''
                };
                
                cloudStorage.addUser(newUser);
                
                currentUser = newUser;
                localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                
                showMainApp();
            });
            
            // Профиль
            document.getElementById('editProfileBtn').addEventListener('click', () => {
                document.getElementById('profileName').value = currentUser.name;
                document.getElementById('profileBio').value = currentUser.bio || '';
                document.getElementById('profileLocation').value = currentUser.location || '';
                
                const avatarPreview = document.getElementById('profileAvatarPreview');
                if (currentUser.avatar) {
                    avatarPreview.style.backgroundImage = `url(${currentUser.avatar})`;
                    avatarPreview.textContent = '';
                } else {
                    avatarPreview.style.backgroundImage = '';
                    avatarPreview.textContent = currentUser.name.split(' ').map(n => n[0]).join('');
                }
                
                profileModal.style.display = 'flex';
            });
            
            document.getElementById('closeProfile').addEventListener('click', () => {
                profileModal.style.display = 'none';
            });
            
            document.getElementById('changeAvatar').addEventListener('click', () => {
                document.getElementById('avatarUpload').click();
            });
            
            document.getElementById('avatarUpload').addEventListener('change', function(e) {
                if (e.target.files && e.target.files[0]) {
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        currentUser.avatar = event.target.result;
                        document.getElementById('profileAvatarPreview').style.backgroundImage = `url(${event.target.result})`;
                        document.getElementById('profileAvatarPreview').textContent = '';
                        updateUserInterface();
                    };
                    reader.readAsDataURL(e.target.files[0]);
                }
            });
            
            document.getElementById('saveProfile').addEventListener('click', () => {
                currentUser.name = document.getElementById('profileName').value;
                currentUser.bio = document.getElementById('profileBio').value;
                currentUser.location = document.getElementById('profileLocation').value;
                
                // Обновляем пользователя в облачном хранилище
                cloudStorage.updateUser(currentUser);
                localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                updateUserInterface();
                profileModal.style.display = 'none';
                
                cloudStorage.showStatus('Профиль обновлен и синхронизирован');
            });
            
            // Создание истории
            document.getElementById('createStoryBtn').addEventListener('click', () => {
                storyModal.style.display = 'flex';
            });
            
            document.getElementById('closeStory').addEventListener('click', () => {
                storyModal.style.display = 'none';
            });
            
            document.getElementById('uploadStoryBtn').addEventListener('click', () => {
                document.getElementById('storyUpload').click();
            });
            
            document.getElementById('storyUpload').addEventListener('change', function(e) {
                if (e.target.files && e.target.files[0]) {
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        document.getElementById('storyPreview').style.backgroundImage = `url(${event.target.result})`;
                        document.getElementById('storyPreview').textContent = '';
                    };
                    reader.readAsDataURL(e.target.files[0]);
                }
            });
            
            document.getElementById('publishStoryBtn').addEventListener('click', () => {
                const storyPreview = document.getElementById('storyPreview');
                const backgroundImage = storyPreview.style.backgroundImage;
                
                if (backgroundImage && backgroundImage !== 'none') {
                    const newStory = {
                        id: Date.now(),
                        userId: currentUser.id,
                        userName: currentUser.name,
                        userAvatar: currentUser.avatar,
                        image: backgroundImage.slice(5, -2), // Извлекаем URL из backgroundImage
                        timestamp: new Date().toISOString()
                    };
                    
                    cloudStorage.addStory(newStory);
                    loadStories();
                    storyModal.style.display = 'none';
                    
                    // Сброс превью
                    storyPreview.style.backgroundImage = 'none';
                    storyPreview.textContent = 'Ваша история будет здесь';
                    
                    cloudStorage.showStatus('История опубликована и синхронизирована');
                } else {
                    alert('Пожалуйста, загрузите изображение для истории');
                }
            });
            
            // Создание поста
            document.getElementById('openPostModal').addEventListener('click', () => {
                postModal.style.display = 'flex';
            });
            
            document.getElementById('openPostModal2').addEventListener('click', () => {
                postModal.style.display = 'flex';
            });
            
            document.getElementById('closePost').addEventListener('click', () => {
                postModal.style.display = 'none';
            });
            
            document.getElementById('uploadPostImageBtn').addEventListener('click', () => {
                document.getElementById('postUpload').click();
            });
            
            document.getElementById('postUpload').addEventListener('change', function(e) {
                if (e.target.files && e.target.files[0]) {
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        document.getElementById('postPreview').src = event.target.result;
                        document.getElementById('postPreview').style.display = 'block';
                    };
                    reader.readAsDataURL(e.target.files[0]);
                }
            });
            
            document.getElementById('publishPostBtn').addEventListener('click', () => {
                const postText = document.getElementById('postText').value;
                const postImage = document.getElementById('postPreview').src;
                
                if (postText.trim() === '' && postImage === '') {
                    alert('Пожалуйста, добавьте текст или изображение к посту');
                    return;
                }
                
                const newPost = {
                    id: Date.now(),
                    userId: currentUser.id,
                    userName: currentUser.name,
                    userAvatar: currentUser.avatar,
                    text: postText,
                    image: postImage !== '' ? postImage : null,
                    likes: [],
                    comments: [],
                    timestamp: new Date().toISOString()
                };
                
                cloudStorage.addPost(newPost);
                loadPosts();
                postModal.style.display = 'none';
                
                // Сброс формы
                document.getElementById('postText').value = '';
                document.getElementById('postPreview').src = '';
                document.getElementById('postPreview').style.display = 'none';
                
                cloudStorage.showStatus('Пост опубликован и синхронизирован');
            });
            
            // Навигация
            document.querySelectorAll('.nav-icon, .sidebar-menu li').forEach(element => {
                if (element.dataset.page) {
                    element.addEventListener('click', function() {
                        // Убираем активный класс у всех элементов
                        document.querySelectorAll('.nav-icon').forEach(icon => icon.classList.remove('active'));
                        document.querySelectorAll('.sidebar-menu li').forEach(li => li.classList.remove('active'));
                        
                        // Добавляем активный класс к текущему элементу
                        this.classList.add('active');
                        
                        // Здесь можно добавить логику для переключения страниц
                        // В этом примере мы просто показываем уведомление
                        if (this.dataset.page !== 'home') {
                            alert(`Раздел "${this.dataset.page}" находится в разработке`);
                        }
                    });
                }
            });
        }
        
        // Загрузка постов
        function loadPosts() {
            const posts = cloudStorage.getPosts();
            postsContainer.innerHTML = '';
            
            if (posts.length === 0) {
                postsContainer.innerHTML = '<div class="post"><div class="post-content"><p>Пока нет постов. Будьте первым, кто поделится чем-то интересным!</p></div></div>';
                return;
            }
            
            posts.forEach(post => {
                const postElement = document.createElement('div');
                postElement.className = 'post';
                postElement.innerHTML = `
                    <div class="post-header">
                        <div class="avatar" style="${post.userAvatar ? `background-image: url(${post.userAvatar})` : ''}">${!post.userAvatar ? post.userName.split(' ').map(n => n[0]).join('') : ''}</div>
                        <div class="post-user">
                            <div class="name">${post.userName}</div>
                            <div class="time">
                                ${formatTime(post.timestamp)} <i class="fas fa-globe-americas"></i>
                            </div>
                        </div>
                        <div class="nav-icon">
                            <i class="fas fa-ellipsis-h"></i>
                        </div>
                    </div>
                    
                    <div class="post-content">
                        <div class="post-text">${post.text}</div>
                        ${post.image ? `<img src="${post.image}" alt="Post image" class="post-image">` : ''}
                    </div>
                    
                    <div class="post-stats">
                        <div class="likes">
                            <i class="fas fa-thumbs-up"></i> ${post.likes.length}
                        </div>
                        <div class="comments-share">
                            ${post.comments.length} комментария
                        </div>
                    </div>
                    
                    <div class="post-actions-row">
                        <div class="post-action-btn ${post.likes.includes(currentUser.id) ? 'active' : ''}" data-post-id="${post.id}">
                            <i class="${post.likes.includes(currentUser.id) ? 'fas' : 'far'} fa-thumbs-up"></i>
                            <span>Нравится</span>
                        </div>
                        <div class="post-action-btn" data-post-id="${post.id}">
                            <i class="far fa-comment"></i>
                            <span>Комментировать</span>
                        </div>
                        <div class="post-action-btn" data-post-id="${post.id}">
                            <i class="far fa-share-square"></i>
                            <span>Поделиться</span>
                        </div>
                    </div>
                    
                    <div class="comments">
                        ${post.comments.map(comment => `
                            <div class="comment">
                                <div class="avatar" style="${comment.userAvatar ? `background-image: url(${comment.userAvatar})` : ''}">${!comment.userAvatar ? comment.userName.split(' ').map(n => n[0]).join('') : ''}</div>
                                <div class="comment-content">
                                    <div class="name">${comment.userName}</div>
                                    <div class="text">${comment.text}</div>
                                    <div class="comment-actions">
                                        <span class="comment-action">Нравится</span>
                                        <span class="comment-action">Ответить</span>
                                        <span class="comment-action">${formatTime(comment.timestamp)}</span>
                                    </div>
                                </div>
                            </div>
                        `).join('')}
                        
                        <div class="add-comment">
                            <div class="avatar" style="${currentUser.avatar ? `background-image: url(${currentUser.avatar})` : ''}">${!currentUser.avatar ? currentUser.name.split(' ').map(n => n[0]).join('') : ''}</div>
                            <input type="text" placeholder="Напишите комментарий..." data-post-id="${post.id}">
                        </div>
                    </div>
                `;
                
                postsContainer.appendChild(postElement);
            });
            
            // Добавляем обработчики событий для лайков и комментариев
            document.querySelectorAll('.post-action-btn[data-post-id]').forEach(button => {
                if (button.querySelector('.fa-thumbs-up')) {
                    button.addEventListener('click', function() {
                        const postId = parseInt(this.dataset.postId);
                        const posts = cloudStorage.getPosts();
                        const post = posts.find(p => p.id === postId);
                        
                        if (post.likes.includes(currentUser.id)) {
                            post.likes = post.likes.filter(id => id !== currentUser.id);
                        } else {
                            post.likes.push(currentUser.id);
                        }
                        
                        cloudStorage.updatePost(post);
                        loadPosts();
                    });
                }
            });
            
            document.querySelectorAll('.add-comment input').forEach(input => {
                input.addEventListener('keypress', function(e) {
                    if (e.key === 'Enter' && this.value.trim() !== '') {
                        const postId = parseInt(this.dataset.postId);
                        const posts = cloudStorage.getPosts();
                        const post = posts.find(p => p.id === postId);
                        
                        const newComment = {
                            id: Date.now(),
                            userId: currentUser.id,
                            userName: currentUser.name,
                            userAvatar: currentUser.avatar,
                            text: this.value.trim(),
                            timestamp: new Date().toISOString()
                        };
                        
                        post.comments.push(newComment);
                        cloudStorage.updatePost(post);
                        loadPosts();
                    }
                });
            });
        }
        
        // Загрузка историй
        function loadStories() {
            const stories = cloudStorage.getStories();
            
            // Оставляем только первую историю (кнопку создания)
            const createStoryBtn = document.getElementById('createStoryBtn');
            storiesContainer.innerHTML = '';
            storiesContainer.appendChild(createStoryBtn);
            
            if (stories.length === 0) return;
            
            stories.slice(0, 5).forEach(story => {
                const storyElement = document.createElement('div');
                storyElement.className = 'story';
                storyElement.innerHTML = `
                    <div class="story-bg" style="background-image: url(${story.image})"></div>
                    <div class="story-user">${story.userName}</div>
                `;
                
                storiesContainer.appendChild(storyElement);
            });
        }
        
        // Форматирование времени
        function formatTime(timestamp) {
            const now = new Date();
            const postTime = new Date(timestamp);
            const diffMs = now - postTime;
            const diffMins = Math.floor(diffMs / 60000);
            const diffHours = Math.floor(diffMs / 3600000);
            const diffDays = Math.floor(diffMs / 86400000);
            
            if (diffMins < 1) return 'только что';
            if (diffMins < 60) return `${diffMins} мин.`;
            if (diffHours < 24) return `${diffHours} ч.`;
            if (diffDays < 7) return `${diffDays} дн.`;
            
            return postTime.toLocaleDateString('ru-RU');
        }
    </script>
</body>
</html>
