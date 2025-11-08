# FaceXi
.
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FaceXI - Социальная сеть с уникальными функциями</title>
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
            --family: #ff6b6b;
            --bg-color: #f0f2f5;
            --card-bg: #ffffff;
            --text-primary: #050505;
            --text-secondary: #65676b;
            --border: #dddfe2;
            --shadow: 0 2px 4px rgba(0, 0, 0, 0.1), 0 8px 16px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s cubic-bezier(0.08, 0.52, 0.52, 1);
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
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            transition: var(--transition);
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
            transition: var(--transition);
        }
        
        .logo:hover {
            transform: scale(1.05);
        }
        
        .logo i {
            margin-right: 8px;
        }
        
        .search-bar {
            flex: 0 1 680px;
            margin: 0 20px;
            position: relative;
        }
        
        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border-radius: 20px;
            border: 1px solid var(--border);
            background-color: var(--bg-color);
            font-size: 15px;
            transition: var(--transition);
        }
        
        .search-bar input:focus {
            background-color: white;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2);
        }
        
        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: white;
            border-radius: 8px;
            box-shadow: var(--shadow);
            max-height: 300px;
            overflow-y: auto;
            z-index: 1000;
            display: none;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .search-result-item {
            padding: 10px 15px;
            border-bottom: 1px solid var(--border);
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
        }
        
        .search-result-item:hover {
            background-color: var(--bg-color);
        }
        
        .search-result-avatar {
            width: 32px;
            height: 32px;
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
            transition: var(--transition);
            position: relative;
        }
        
        .nav-icon.active {
            background-color: var(--primary);
            color: white;
        }
        
        .nav-icon:hover {
            background-color: var(--border);
            transform: scale(1.1);
        }
        
        .nav-icon.active:hover {
            background-color: var(--primary);
        }
        
        .nav-icon .notification-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background-color: #ff375f;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
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
            transition: var(--transition);
            border: 2px solid transparent;
        }
        
        .user-avatar:hover {
            border-color: var(--primary);
            transform: scale(1.05);
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
            position: sticky;
            top: 70px;
            height: calc(100vh - 90px);
            overflow-y: auto;
        }
        
        .sidebar-card {
            background-color: var(--card-bg);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .sidebar-card:hover {
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border);
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
            transition: var(--transition);
        }
        
        .user-info .avatar:hover {
            transform: scale(1.1);
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
            transition: var(--transition);
        }
        
        .sidebar-menu li:hover {
            background-color: var(--bg-color);
            transform: translateX(5px);
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
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .create-post:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
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
            transition: var(--transition);
        }
        
        .post-input .avatar:hover {
            transform: scale(1.1);
        }
        
        .post-input input {
            flex: 1;
            padding: 12px 15px;
            border-radius: 20px;
            border: none;
            background-color: var(--bg-color);
            font-size: 17px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .post-input input:hover {
            background-color: #e4e6e9;
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
            transition: var(--transition);
            flex: 1;
            justify-content: center;
        }
        
        .post-action:hover {
            background-color: var(--bg-color);
            transform: translateY(-2px);
        }
        
        .post-action i {
            margin-right: 8px;
            font-size: 20px;
        }
        
        .photo-video i { color: #45bd62; }
        .feeling i { color: #f7b928; }
        .live i { color: #f5533d; }
        
        /* Post Options */
        .post-options {
            padding: 10px 0;
            border-top: 1px solid var(--border);
            display: none;
        }
        
        .post-option {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .post-option input {
            margin-right: 10px;
        }
        
        /* Family Section */
        .family-section {
            background: var(--card-bg);
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .family-section:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }
        
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .section-title {
            font-size: 20px;
            font-weight: bold;
        }
        
        .add-family-btn {
            color: var(--primary);
            cursor: pointer;
            font-weight: 500;
            padding: 8px 12px;
            border-radius: 6px;
            transition: var(--transition);
        }
        
        .add-family-btn:hover {
            background-color: var(--bg-color);
        }
        
        .family-members {
            display: flex;
            gap: 15px;
            overflow-x: auto;
            padding: 10px 0;
        }
        
        .family-member {
            text-align: center;
            flex: 0 0 100px;
            transition: var(--transition);
            cursor: pointer;
        }
        
        .family-member:hover {
            transform: translateY(-5px);
        }
        
        .family-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--family);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin: 0 auto 10px;
            font-size: 20px;
            transition: var(--transition);
            background-size: cover;
            background-position: center;
        }
        
        .family-avatar:hover {
            transform: scale(1.1);
        }
        
        .add-family {
            border: 2px dashed var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .add-family:hover {
            border-color: var(--primary);
            background-color: rgba(24, 119, 242, 0.05);
        }
        
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
            box-shadow: var(--shadow);
            cursor: pointer;
            transition: var(--transition);
        }
        
        .story:hover {
            transform: scale(1.03);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
        }
        
        .story-bg {
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            transition: transform 0.5s;
        }
        
        .story:hover .story-bg {
            transform: scale(1.1);
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
            transition: var(--transition);
        }
        
        .create-story:hover .plus {
            background-color: #166fe5;
            transform: translateX(-50%) scale(1.1);
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
            box-shadow: var(--shadow);
            transition: var(--transition);
            overflow: hidden;
        }
        
        .post:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
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
            transition: var(--transition);
            cursor: pointer;
        }
        
        .post-header .avatar:hover {
            transform: scale(1.1);
        }
        
        .post-user {
            flex: 1;
        }
        
        .post-user .name {
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .post-user .name:hover {
            color: var(--primary);
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
        
        .post-badge {
            background: var(--secondary);
            color: white;
            padding: 2px 8px;
            border-radius: 10px;
            font-size: 12px;
            margin-left: 5px;
        }
        
        .post-content {
            padding: 0 15px 15px;
        }
        
        .post-text {
            margin-bottom: 10px;
            line-height: 1.4;
        }
        
        .post-image {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 10px;
            max-height: 500px;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .post-image:hover {
            opacity: 0.95;
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
            transition: var(--transition);
            flex: 1;
            justify-content: center;
        }
        
        .post-action-btn:hover {
            background-color: var(--bg-color);
            transform: translateY(-2px);
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
            max-height: 300px;
            overflow-y: auto;
        }
        
        .comment {
            display: flex;
            margin-bottom: 10px;
            animation: fadeIn 0.3s ease;
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
            transition: var(--transition);
            cursor: pointer;
        }
        
        .comment .avatar:hover {
            transform: scale(1.1);
        }
        
        .comment-content {
            background-color: var(--bg-color);
            padding: 8px 12px;
            border-radius: 18px;
            flex: 1;
            transition: var(--transition);
        }
        
        .comment-content:hover {
            background-color: #e4e6e9;
        }
        
        .comment .name {
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .comment .name:hover {
            color: var(--primary);
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
            transition: var(--transition);
        }
        
        .comment-action:hover {
            color: var(--primary);
            text-decoration: underline;
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
            transition: var(--transition);
        }
        
        .add-comment input:focus {
            background-color: white;
            box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2);
        }
        
        /* Right Sidebar */
        .right-sidebar {
            flex: 0 0 280px;
            position: sticky;
            top: 70px;
            height: calc(100vh - 90px);
            overflow-y: auto;
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
            transition: var(--transition);
        }
        
        .contact:hover {
            background-color: var(--bg-color);
            transform: translateX(5px);
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
            transition: var(--transition);
        }
        
        .contact .avatar:hover {
            transform: scale(1.1);
        }
        
        /* Modals */
        .modal-overlay {
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
            animation: fadeIn 0.3s ease;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 8px;
            width: 500px;
            max-width: 90%;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            transform: scale(0.9);
            animation: modalAppear 0.3s ease forwards;
        }
        
        @keyframes modalAppear {
            to { transform: scale(1); }
        }
        
        .modal-header {
            padding: 15px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-header h2 {
            font-size: 20px;
        }
        
        .close-modal {
            font-size: 24px;
            cursor: pointer;
            color: var(--text-secondary);
            transition: var(--transition);
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .close-modal:hover {
            background-color: var(--bg-color);
            color: var(--text-primary);
        }
        
        .modal-body {
            padding: 20px;
        }
        
        /* Auth Modal */
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
            transition: var(--transition);
        }
        
        .auth-tab.active {
            border-bottom: 3px solid var(--primary);
            font-weight: bold;
        }
        
        .auth-tab:hover {
            background-color: var(--bg-color);
        }
        
        .auth-form {
            display: none;
        }
        
        .auth-form.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid var(--border);
            font-size: 15px;
            transition: var(--transition);
        }
        
        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2);
        }
        
        .checkbox-group {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .checkbox-group input {
            width: auto;
            margin-right: 10px;
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
            transition: var(--transition);
        }
        
        .auth-button:hover {
            background-color: #166fe5;
            transform: translateY(-2px);
        }
        
        /* Profile Modal */
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
            transition: var(--transition);
            border: 4px solid white;
            box-shadow: var(--shadow);
        }
        
        .profile-avatar .avatar:hover {
            transform: scale(1.05);
        }
        
        .change-avatar {
            color: var(--primary);
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition);
        }
        
        .change-avatar:hover {
            text-decoration: underline;
        }
        
        .unique-id {
            background: var(--bg-color);
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 15px;
            font-family: monospace;
        }
        
        /* Create Story Modal */
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
            transition: var(--transition);
        }
        
        .story-preview:hover {
            background-color: #e4e6e9;
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
            transition: var(--transition);
        }
        
        .story-button:hover {
            background-color: #166fe5;
            transform: translateY(-2px);
        }
        
        /* Create Post Modal */
        .post-modal-text {
            width: 100%;
            min-height: 100px;
            border: none;
            resize: none;
            font-size: 16px;
            margin-bottom: 15px;
            transition: var(--transition);
        }
        
        .post-modal-text:focus {
            outline: none;
        }
        
        .post-modal-preview {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 15px;
            display: none;
            transition: var(--transition);
        }
        
        .post-modal-preview:hover {
            opacity: 0.9;
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
            transition: var(--transition);
        }
        
        .post-modal-button:hover {
            background-color: #166fe5;
            transform: translateY(-2px);
        }
        
        .post-modal-button.secondary {
            background-color: var(--bg-color);
            color: var(--text-primary);
        }
        
        .post-modal-button.secondary:hover {
            background-color: #e4e6e9;
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
            box-shadow: var(--shadow);
            display: none;
            z-index: 1001;
            animation: slideIn 0.3s ease;
        }
        
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        
        /* Family Management Modal */
        .search-family-member {
            display: flex;
            margin-bottom: 20px;
        }
        
        .search-family-member input {
            flex: 1;
            padding: 10px 15px;
            border-radius: 5px 0 0 5px;
            border: 1px solid var(--border);
            border-right: none;
            transition: var(--transition);
        }
        
        .search-family-member input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(24, 119, 242, 0.2);
        }
        
        .search-family-member button {
            padding: 10px 15px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .search-family-member button:hover {
            background-color: #166fe5;
        }
        
        .current-family-members {
            margin-bottom: 20px;
        }
        
        .family-member-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px;
            border-bottom: 1px solid var(--border);
            transition: var(--transition);
        }
        
        .family-member-item:hover {
            background-color: var(--bg-color);
        }
        
        .family-member-info {
            display: flex;
            align-items: center;
        }
        
        .family-member-avatar {
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
            transition: var(--transition);
            cursor: pointer;
        }
        
        .family-member-avatar:hover {
            transform: scale(1.1);
        }
        
        .remove-family-member {
            color: var(--text-secondary);
            cursor: pointer;
            padding: 5px;
            transition: var(--transition);
        }
        
        .remove-family-member:hover {
            color: #ff6b6b;
            transform: scale(1.2);
        }
        
        /* Accounts Modal */
        .account-item {
            display: flex;
            align-items: center;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            margin-bottom: 10px;
            border: 1px solid var(--border);
            transition: var(--transition);
        }
        
        .account-item:hover {
            background-color: var(--bg-color);
            transform: translateX(5px);
        }
        
        .account-item.active {
            border-color: var(--primary);
            background-color: rgba(24, 119, 242, 0.05);
        }
        
        .account-avatar {
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
            transition: var(--transition);
        }
        
        .account-avatar:hover {
            transform: scale(1.1);
        }
        
        .account-info {
            flex: 1;
        }
        
        .account-name {
            font-weight: 600;
        }
        
        .account-id {
            font-size: 12px;
            color: var(--text-secondary);
        }
        
        .add-account-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 15px;
            border: 2px dashed var(--border);
            border-radius: 8px;
            cursor: pointer;
            margin-top: 10px;
            transition: var(--transition);
        }
        
        .add-account-btn:hover {
            background-color: var(--bg-color);
            border-color: var(--primary);
        }
        
        /* Switch Account Button */
        .switch-account-btn {
            display: flex;
            align-items: center;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            margin-left: 10px;
            background-color: var(--bg-color);
            transition: var(--transition);
        }
        
        .switch-account-btn:hover {
            background-color: var(--border);
            transform: scale(1.05);
        }
        
        /* User Profile Modal */
        .user-profile-modal {
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
            animation: fadeIn 0.3s ease;
        }
        
        .user-profile-content {
            background-color: white;
            border-radius: 8px;
            width: 800px;
            max-width: 95%;
            max-height: 95%;
            overflow-y: auto;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            transform: scale(0.9);
            animation: modalAppear 0.3s ease forwards;
        }
        
        .user-profile-header {
            padding: 20px;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: linear-gradient(135deg, var(--primary) 0%, #42b72a 100%);
            color: white;
            border-radius: 8px 8px 0 0;
        }
        
        .user-profile-header h2 {
            font-size: 24px;
            margin: 0;
        }
        
        .close-user-profile {
            font-size: 24px;
            cursor: pointer;
            color: white;
            transition: var(--transition);
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .close-user-profile:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }
        
        .user-profile-body {
            padding: 20px;
        }
        
        .user-profile-info {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border);
        }
        
        .user-profile-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 40px;
            margin-right: 20px;
            background-size: cover;
            background-position: center;
            border: 4px solid white;
            box-shadow: var(--shadow);
        }
        
        .user-profile-details {
            flex: 1;
        }
        
        .user-profile-name {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .user-profile-id {
            font-size: 16px;
            color: var(--text-secondary);
            margin-bottom: 10px;
            font-family: monospace;
        }
        
        .user-profile-bio {
            margin-bottom: 10px;
            line-height: 1.4;
        }
        
        .user-profile-location {
            display: flex;
            align-items: center;
            color: var(--text-secondary);
            margin-bottom: 10px;
        }
        
        .user-profile-location i {
            margin-right: 5px;
        }
        
        .user-profile-stats {
            display: flex;
            gap: 20px;
            margin-top: 15px;
        }
        
        .user-profile-stat {
            text-align: center;
        }
        
        .user-profile-stat-value {
            font-size: 18px;
            font-weight: bold;
            color: var(--primary);
        }
        
        .user-profile-stat-label {
            font-size: 12px;
            color: var(--text-secondary);
        }
        
        .user-profile-tabs {
            display: flex;
            border-bottom: 1px solid var(--border);
            margin-bottom: 20px;
        }
        
        .user-profile-tab {
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: var(--transition);
        }
        
        .user-profile-tab.active {
            border-bottom: 3px solid var(--primary);
            font-weight: bold;
        }
        
        .user-profile-tab:hover {
            background-color: var(--bg-color);
        }
        
        .user-profile-tab-content {
            display: none;
        }
        
        .user-profile-tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        .user-profile-posts {
            display: grid;
            gap: 15px;
        }
        
        .user-profile-stories {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding: 10px 0;
        }
        
        .user-profile-story {
            flex: 0 0 100px;
            height: 150px;
            border-radius: 10px;
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow);
            cursor: pointer;
            transition: var(--transition);
        }
        
        .user-profile-story:hover {
            transform: scale(1.05);
        }
        
        .user-profile-story-bg {
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
        }
        
        .user-profile-about {
            line-height: 1.6;
        }
        
        .user-profile-about-item {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .user-profile-about-item i {
            width: 20px;
            margin-right: 10px;
            color: var(--primary);
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
        
        /* Video player styles */
        .video-player {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 10px;
        }
        
        /* Feeling/Activity modal */
        .feeling-options {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .feeling-option {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .feeling-option:hover {
            background-color: var(--bg-color);
            transform: scale(1.05);
        }
        
        .feeling-option i {
            font-size: 24px;
            margin-bottom: 5px;
        }
        
        /* File upload area */
        .file-upload-area {
            border: 2px dashed var(--border);
            border-radius: 8px;
            padding: 30px;
            text-align: center;
            margin-bottom: 20px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .file-upload-area:hover {
            border-color: var(--primary);
            background-color: rgba(24, 119, 242, 0.05);
        }
        
        .file-upload-area i {
            font-size: 40px;
            color: var(--text-secondary);
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <!-- Status Message -->
    <div class="status-message" id="statusMessage"></div>
    
    <!-- Auth Modal -->
    <div class="modal-overlay" id="authModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>FaceXI</h2>
                <div class="close-modal" id="closeAuth">&times;</div>
            </div>
            <div class="modal-body">
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
                    <div class="checkbox-group">
                        <input type="checkbox" id="makePublic" checked>
                        <label for="makePublic">Сделать аккаунт общедоступным</label>
                    </div>
                    <button type="submit" class="auth-button">Зарегистрироваться</button>
                </form>
            </div>
        </div>
    </div>
    
    <!-- Profile Modal -->
    <div class="modal-overlay" id="profileModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Настройки профиля</h2>
                <div class="close-modal" id="closeProfile">&times;</div>
            </div>
            <div class="modal-body">
                <div class="profile-avatar">
                    <div class="avatar" id="profileAvatar">ИИ</div>
                    <div id="profileNameDisplay">Иван Иванов</div>
                </div>
                
                <button class="auth-button secondary" id="manageFamilyBtn" style="margin-bottom: 15px;">
                    <i class="fas fa-users"></i> Управление семьей
                </button>
                
                <div class="form-group">
                    <label>Ваш уникальный ID:</label>
                    <div class="unique-id" id="uniqueId">собачка-осадбек.канал</div>
                </div>
                
                <div class="checkbox-group">
                    <input type="checkbox" id="profilePublic" checked>
                    <label for="profilePublic">Сделать аккаунт общедоступным</label>
                </div>
                
                <div class="form-group">
                    <label for="customId">Настройте свой ID:</label>
                    <input type="text" id="customId" placeholder="введите ваш уникальный ID">
                </div>
                
                <div class="form-group">
                    <label for="profileName">Имя и фамилия</label>
                    <input type="text" id="profileName">
                </div>
                <div class="form-group">
                    <label for="profileBio">О себе</label>
                    <textarea id="profileBio" placeholder="Расскажите о себе" rows="3"></textarea>
                </div>
                <div class="form-group">
                    <label for="profileLocation">Местоположение</label>
                    <input type="text" id="profileLocation" placeholder="Где вы живете?">
                </div>
                <button class="auth-button" id="saveProfile">Сохранить изменения</button>
            </div>
        </div>
    </div>
    
    <!-- Family Management Modal -->
    <div class="modal-overlay" id="familyModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Управление семьей</h2>
                <div class="close-modal" id="closeFamily">&times;</div>
            </div>
            <div class="modal-body">
                <div class="search-family-member">
                    <input type="text" id="familySearchInput" placeholder="Поиск по уникальному ID...">
                    <button id="searchFamilyMemberBtn">Найти</button>
                </div>
                
                <div id="familySearchResults"></div>
                
                <div class="current-family-members">
                    <h3>Члены семьи</h3>
                    <div id="familyMembersList">
                        <!-- Список членов семьи будет здесь -->
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Accounts Modal -->
    <div class="modal-overlay" id="accountsModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Выберите аккаунт</h2>
                <div class="close-modal" id="closeAccounts">&times;</div>
            </div>
            <div class="modal-body">
                <div id="accountsList">
                    <!-- Список аккаунтов будет здесь -->
                </div>
                <div class="add-account-btn" id="addAccountBtn">
                    <i class="fas fa-plus"></i>
                    <span>Создать новый аккаунт</span>
                </div>
            </div>
        </div>
    </div>
    
    <!-- User Profile Modal -->
    <div class="user-profile-modal" id="userProfileModal">
        <div class="user-profile-content">
            <div class="user-profile-header">
                <h2 id="userProfileName">Профиль пользователя</h2>
                <div class="close-user-profile" id="closeUserProfile">&times;</div>
            </div>
            <div class="user-profile-body">
                <div class="user-profile-info">
                    <div class="user-profile-avatar" id="userProfileAvatar">ИИ</div>
                    <div class="user-profile-details">
                        <div class="user-profile-name" id="userProfileFullName">Иван Иванов</div>
                        <div class="user-profile-id" id="userProfileUniqueId">собачка-осадбек.канал</div>
                        <div class="user-profile-bio" id="userProfileBio">Описание пользователя будет здесь</div>
                        <div class="user-profile-location" id="userProfileLocation">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Местоположение</span>
                        </div>
                        <div class="user-profile-stats">
                            <div class="user-profile-stat">
                                <div class="user-profile-stat-value" id="userProfilePostsCount">0</div>
                                <div class="user-profile-stat-label">Постов</div>
                            </div>
                            <div class="user-profile-stat">
                                <div class="user-profile-stat-value" id="userProfileStoriesCount">0</div>
                                <div class="user-profile-stat-label">Историй</div>
                            </div>
                            <div class="user-profile-stat">
                                <div class="user-profile-stat-value" id="userProfileFamilyCount">0</div>
                                <div class="user-profile-stat-label">В семье</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="user-profile-tabs">
                    <div class="user-profile-tab active" data-tab="posts">Посты</div>
                    <div class="user-profile-tab" data-tab="stories">Истории</div>
                    <div class="user-profile-tab" data-tab="about">Информация</div>
                </div>
                
                <div class="user-profile-tab-content active" id="userProfilePostsTab">
                    <div class="user-profile-posts" id="userProfilePostsContainer">
                        <!-- Посты пользователя будут здесь -->
                    </div>
                </div>
                
                <div class="user-profile-tab-content" id="userProfileStoriesTab">
                    <div class="user-profile-stories" id="userProfileStoriesContainer">
                        <!-- Истории пользователя будут здесь -->
                    </div>
                </div>
                
                <div class="user-profile-tab-content" id="userProfileAboutTab">
                    <div class="user-profile-about">
                        <div class="user-profile-about-item">
                            <i class="fas fa-user"></i>
                            <div>
                                <strong>Имя:</strong> <span id="userProfileAboutName">Иван Иванов</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item">
                            <i class="fas fa-at"></i>
                            <div>
                                <strong>Уникальный ID:</strong> <span id="userProfileAboutId">собачка-осадбек.канал</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item">
                            <i class="fas fa-birthday-cake"></i>
                            <div>
                                <strong>Дата рождения:</strong> <span id="userProfileAboutBirthday">Не указана</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item">
                            <i class="fas fa-venus-mars"></i>
                            <div>
                                <strong>Пол:</strong> <span id="userProfileAboutGender">Не указан</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item">
                            <i class="fas fa-calendar-alt"></i>
                            <div>
                                <strong>В сети с:</strong> <span id="userProfileAboutRegDate">Не указана</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item" id="userProfileAboutBioItem">
                            <i class="fas fa-info-circle"></i>
                            <div>
                                <strong>О себе:</strong> <span id="userProfileAboutBio">Не указано</span>
                            </div>
                        </div>
                        <div class="user-profile-about-item" id="userProfileAboutLocationItem">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <strong>Местоположение:</strong> <span id="userProfileAboutLocation">Не указано</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Create Story Modal -->
    <div class="modal-overlay" id="storyModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Создать историю</h2>
                <div class="close-modal" id="closeStory">&times;</div>
            </div>
            <div class="modal-body">
                <div class="file-upload-area" id="storyUploadArea">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Перетащите сюда фото или видео для истории</p>
                    <p>или нажмите для выбора файла</p>
                </div>
                <div class="story-preview" id="storyPreview">
                    <div class="story-preview-text">Ваша история будет здесь</div>
                </div>
                <input type="file" id="storyUpload" accept="image/*,video/*" class="hidden">
                <div class="story-actions">
                    <button class="story-button secondary" id="uploadStoryBtn">Загрузить фото/видео</button>
                    <button class="story-button" id="publishStoryBtn">Опубликовать</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Create Post Modal -->
    <div class="modal-overlay" id="postModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Создать пост</h2>
                <div class="close-modal" id="closePost">&times;</div>
            </div>
            <div class="modal-body">
                <textarea class="post-modal-text" id="postText" placeholder="Что у вас нового?"></textarea>
                <img class="post-modal-preview" id="postPreview">
                <video class="post-modal-preview" id="postVideoPreview" controls style="display:none;"></video>
                <input type="file" id="postUpload" accept="image/*,video/*" class="hidden">
                
                <div class="file-upload-area" id="postUploadArea">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Перетащите сюда фото или видео</p>
                    <p>или нажмите для выбора файла</p>
                </div>
                
                <div class="post-options">
                    <div class="post-option">
                        <input type="checkbox" id="showToNewUsers">
                        <label for="showToNewUsers">Показать этот пост всем новым пользователям</label>
                    </div>
                    <div class="post-option">
                        <input type="checkbox" id="familyOnly">
                        <label for="familyOnly">Только для семьи</label>
                    </div>
                </div>
                <div class="post-modal-actions">
                    <button class="post-modal-button secondary" id="uploadPostImageBtn">Добавить фото/видео</button>
                    <button class="post-modal-button" id="publishPostBtn">Опубликовать</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Feeling/Activity Modal -->
    <div class="modal-overlay" id="feelingModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Добавить чувство или действие</h2>
                <div class="close-modal" id="closeFeeling">&times;</div>
            </div>
            <div class="modal-body">
                <div class="feeling-options">
                    <div class="feeling-option" data-feeling="happy">
                        <i class="fas fa-laugh-beam" style="color: #f7b928;"></i>
                        <span>Счастлив</span>
                    </div>
                    <div class="feeling-option" data-feeling="loved">
                        <i class="fas fa-heart" style="color: #f5533d;"></i>
                        <span>Влюблен</span>
                    </div>
                    <div class="feeling-option" data-feeling="sad">
                        <i class="fas fa-sad-tear" style="color: #1877f2;"></i>
                        <span>Грустный</span>
                    </div>
                    <div class="feeling-option" data-feeling="excited">
                        <i class="fas fa-grin-stars" style="color: #45bd62;"></i>
                        <span>Взволнован</span>
                    </div>
                    <div class="feeling-option" data-feeling="blessed">
                        <i class="fas fa-pray" style="color: #9360f7;"></i>
                        <span>Благословен</span>
                    </div>
                    <div class="feeling-option" data-feeling="grateful">
                        <i class="fas fa-hands" style="color: #f7b928;"></i>
                        <span>Благодарен</span>
                    </div>
                    <div class="feeling-option" data-feeling="confused">
                        <i class="fas fa-surprise" style="color: #1877f2;"></i>
                        <span>В замешательстве</span>
                    </div>
                    <div class="feeling-option" data-feeling="cool">
                        <i class="fas fa-cool" style="color: #45bd62;"></i>
                        <span>Крутой</span>
                    </div>
                </div>
                <button class="auth-button" id="addFeelingBtn">Добавить к посту</button>
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
                    <input type="text" placeholder="Поиск по уникальным ID..." id="searchInput">
                    <div class="search-results" id="searchResults"></div>
                </div>
                
                <div style="display: flex; align-items: center;">
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
                        <div class="nav-icon" data-page="marketplace">
                            <i class="fas fa-store"></i>
                        </div>
                        <div class="nav-icon" data-page="notifications">
                            <i class="fas fa-bell"></i>
                            <div class="notification-badge">3</div>
                        </div>
                        <div class="nav-icon" id="profileBtn">
                            <i class="fas fa-user"></i>
                        </div>
                    </div>
                    
                    <div class="switch-account-btn" id="switchAccountBtn">
                        <i class="fas fa-sync-alt"></i>
                        <span style="margin-left: 5px;">Сменить аккаунт</span>
                    </div>
                    
                    <div class="user-avatar" id="headerUserAvatar">ИИ</div>
                </div>
            </div>
        </div>
    </header>
    
    <!-- Main Content -->
    <div class="container">
        <div id="mainContent" class="hidden">
            <div class="main-content">
                <!-- Left Sidebar -->
                <div class="left-sidebar">
                    <div class="sidebar-card">
                        <div class="user-info">
                            <div class="avatar" id="sidebarAvatar">ИИ</div>
                            <div id="sidebarName">Иван Иванов</div>
                        </div>
                        <ul class="sidebar-menu">
                            <li class="active">
                                <i class="fas fa-user-friends"></i>
                                <span>Друзья</span>
                            </li>
                            <li>
                                <i class="fas fa-users"></i>
                                <span>Группы</span>
                            </li>
                            <li>
                                <i class="fas fa-store"></i>
                                <span>Маркетплейс</span>
                            </li>
                            <li>
                                <i class="fas fa-tv"></i>
                                <span>Watch</span>
                            </li>
                            <li>
                                <i class="fas fa-history"></i>
                                <span>Воспоминания</span>
                            </li>
                            <li>
                                <i class="fas fa-bookmark"></i>
                                <span>Сохраненное</span>
                            </li>
                            <li>
                                <i class="fas fa-flag"></i>
                                <span>Страницы</span>
                            </li>
                            <li>
                                <i class="fas fa-calendar-alt"></i>
                                <span>События</span>
                            </li>
                        </ul>
                    </div>
                    
                    <div class="sidebar-card">
                        <div class="shortcuts">
                            <h3>Ваши ярлыки</h3>
                            <ul class="sidebar-menu">
                                <li>
                                    <i class="fas fa-gamepad" style="color: #45bd62;"></i>
                                    <span>Игры</span>
                                </li>
                                <li>
                                    <i class="fas fa-film" style="color: #f7b928;"></i>
                                    <span>Фильмы</span>
                                </li>
                                <li>
                                    <i class="fas fa-music" style="color: #f5533d;"></i>
                                    <span>Музыка</span>
                                </li>
                                <li>
                                    <i class="fas fa-newspaper" style="color: #1877f2;"></i>
                                    <span>Новости</span>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                
                <!-- Feed -->
                <div class="feed">
                    <!-- Family Section -->
                    <div class="family-section">
                        <div class="section-header">
                            <div class="section-title">Моя семья</div>
                            <div class="add-family-btn" id="openFamilyModal">+ Добавить</div>
                        </div>
                        <div class="family-members" id="familyMembersContainer">
                            <!-- Члены семьи будут загружены здесь -->
                        </div>
                    </div>
                    
                    <!-- Create Post -->
                    <div class="create-post">
                        <div class="post-input">
                            <div class="avatar" id="postInputAvatar">ИИ</div>
                            <input type="text" placeholder="Что у вас нового?" id="openPostModalInput">
                        </div>
                        <div class="post-options" id="mainPostOptions">
                            <div class="post-option">
                                <input type="checkbox" id="showToNewUsersMain">
                                <label for="showToNewUsersMain">Показать этот пост всем новым пользователям</label>
                            </div>
                            <div class="post-option">
                                <input type="checkbox" id="familyOnlyMain">
                                <label for="familyOnlyMain">Только для семьи</label>
                            </div>
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
                            <div class="post-action live" id="openLiveModal">
                                <i class="fas fa-video"></i>
                                <span>Прямой эфир</span>
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
                    <div class="sidebar-card">
                        <h3>Контакты</h3>
                        <div class="contacts" id="contactsList">
                            <!-- Контакты будут загружены здесь -->
                        </div>
                    </div>
                    
                    <div class="sidebar-card">
                        <h3>Рекомендации</h3>
                        <div class="contacts">
                            <div class="contact">
                                <div class="avatar">АП</div>
                                <div>Андрей Петров</div>
                            </div>
                            <div class="contact">
                                <div class="avatar">МС</div>
                                <div>Мария Сидорова</div>
                            </div>
                            <div class="contact">
                                <div class="avatar">ДК</div>
                                <div>Дмитрий Козлов</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Класс облачного хранилища
        class CloudStorage {
            constructor() {
                this.storageKey = 'facexi_cloud_data';
                this.init();
            }
            
            init() {
                if (!localStorage.getItem(this.storageKey)) {
                    const initialData = {
                        users: [],
                        posts: [],
                        stories: [],
                        contacts: [],
                        lastUpdate: new Date().toISOString()
                    };
                    localStorage.setItem(this.storageKey, JSON.stringify(initialData));
                }
            }
            
            getAllData() {
                const data = localStorage.getItem(this.storageKey);
                return data ? JSON.parse(data) : null;
            }
            
            saveAllData(data) {
                data.lastUpdate = new Date().toISOString();
                localStorage.setItem(this.storageKey, JSON.stringify(data));
                this.simulateSync();
            }
            
            simulateSync() {
                console.log('Данные синхронизированы с облаком');
                this.showStatus('Данные синхронизированы с облаком');
            }
            
            showStatus(message) {
                const statusElement = document.getElementById('statusMessage');
                statusElement.textContent = message;
                statusElement.style.display = 'block';
                
                setTimeout(() => {
                    statusElement.style.display = 'none';
                }, 3000);
            }
            
            getUsers() {
                const data = this.getAllData();
                return data ? data.users : [];
            }
            
            saveUsers(users) {
                const data = this.getAllData();
                data.users = users;
                this.saveAllData(data);
            }
            
            getPosts() {
                const data = this.getAllData();
                return data ? data.posts : [];
            }
            
            savePosts(posts) {
                const data = this.getAllData();
                data.posts = posts;
                this.saveAllData(data);
            }
            
            getStories() {
                const data = this.getAllData();
                return data ? data.stories : [];
            }
            
            saveStories(stories) {
                const data = this.getAllData();
                data.stories = stories;
                this.saveAllData(data);
            }
            
            getContacts() {
                const data = this.getAllData();
                return data ? data.contacts : [];
            }
            
            saveContacts(contacts) {
                const data = this.getAllData();
                data.contacts = contacts;
                this.saveAllData(data);
            }
            
            findUserByEmail(email) {
                const users = this.getUsers();
                return users.find(user => user.email === email);
            }
            
            findUserById(id) {
                const users = this.getUsers();
                return users.find(user => user.id === id);
            }
            
            findUserByUniqueId(uniqueId) {
                const users = this.getUsers();
                return users.find(user => user.uniqueId === uniqueId);
            }
            
            addUser(user) {
                const users = this.getUsers();
                users.push(user);
                this.saveUsers(users);
                return user;
            }
            
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
            
            addPost(post) {
                const posts = this.getPosts();
                posts.unshift(post);
                this.savePosts(posts);
                return post;
            }
            
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
            
            addStory(story) {
                const stories = this.getStories();
                stories.unshift(story);
                this.saveStories(stories);
                return story;
            }
            
            searchUsers(query) {
                const users = this.getUsers();
                return users.filter(user => 
                    user.isPublic && 
                    (user.uniqueId.toLowerCase().includes(query.toLowerCase()) ||
                     user.name.toLowerCase().includes(query.toLowerCase()))
                );
            }
        }
        
        // Данные приложения
        const cloudStorage = new CloudStorage();
        let currentUser = null;
        let availableAccounts = [];
        let viewingUser = null;
        
        // DOM элементы
        const authModal = document.getElementById('authModal');
        const profileModal = document.getElementById('profileModal');
        const familyModal = document.getElementById('familyModal');
        const accountsModal = document.getElementById('accountsModal');
        const userProfileModal = document.getElementById('userProfileModal');
        const storyModal = document.getElementById('storyModal');
        const postModal = document.getElementById('postModal');
        const feelingModal = document.getElementById('feelingModal');
        const mainHeader = document.getElementById('mainHeader');
        const mainContent = document.getElementById('mainContent');
        const postsContainer = document.getElementById('postsContainer');
        const storiesContainer = document.getElementById('storiesContainer');
        const searchInput = document.getElementById('searchInput');
        const searchResults = document.getElementById('searchResults');
        
        // Инициализация приложения
        document.addEventListener('DOMContentLoaded', function() {
            // Загружаем доступные аккаунты
            loadAvailableAccounts();
            
            const savedUser = localStorage.getItem('facexi_current_user');
            if (savedUser) {
                const userData = JSON.parse(savedUser);
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
            
            initEventListeners();
            loadPosts();
            loadStories();
            loadFamilyMembers();
            loadContacts();
        });
        
        // Загрузка доступных аккаунтов
        function loadAvailableAccounts() {
            const savedAccounts = localStorage.getItem('facexi_available_accounts');
            if (savedAccounts) {
                availableAccounts = JSON.parse(savedAccounts);
            } else {
                availableAccounts = [];
            }
        }
        
        // Сохранение доступных аккаунтов
        function saveAvailableAccounts() {
            localStorage.setItem('facexi_available_accounts', JSON.stringify(availableAccounts));
        }
        
        // Добавление аккаунта в список доступных
        function addAccountToAvailable(user) {
            // Проверяем, нет ли уже этого аккаунта в списке
            const existingAccount = availableAccounts.find(acc => acc.id === user.id);
            if (!existingAccount) {
                availableAccounts.push({
                    id: user.id,
                    name: user.name,
                    uniqueId: user.uniqueId,
                    avatar: user.avatar
                });
                saveAvailableAccounts();
            }
        }
        
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
            
            // Обновляем аватар в хедере
            const headerAvatar = document.getElementById('headerUserAvatar');
            if (currentUser.avatar) {
                headerAvatar.style.backgroundImage = `url(${currentUser.avatar})`;
                headerAvatar.textContent = '';
            } else {
                headerAvatar.style.backgroundImage = '';
                headerAvatar.textContent = currentUser.name.split(' ').map(n => n[0]).join('');
            }
            
            // Обновляем аватар в сайдбаре
            const sidebarAvatar = document.getElementById('sidebarAvatar');
            if (currentUser.avatar) {
                sidebarAvatar.style.backgroundImage = `url(${currentUser.avatar})`;
                sidebarAvatar.textContent = '';
            } else {
                sidebarAvatar.style.backgroundImage = '';
                sidebarAvatar.textContent = currentUser.name.split(' ').map(n => n[0]).join('');
            }
            
            // Обновляем имя в сайдбаре
            document.getElementById('sidebarName').textContent = currentUser.name;
            
            // Обновляем аватар в создании поста
            const postInputAvatar = document.getElementById('postInputAvatar');
            if (currentUser.avatar) {
                postInputAvatar.style.backgroundImage = `url(${currentUser.avatar})`;
                postInputAvatar.textContent = '';
            } else {
                postInputAvatar.style.backgroundImage = '';
                postInputAvatar.textContent = currentUser.name.split(' ').map(n => n[0]).join('');
            }
            
            // Обновляем профиль
            document.getElementById('profileAvatar').textContent = currentUser.name.split(' ').map(n => n[0]).join('');
            if (currentUser.avatar) {
                document.getElementById('profileAvatar').style.backgroundImage = `url(${currentUser.avatar})`;
                document.getElementById('profileAvatar').textContent = '';
            }
            
            document.getElementById('profileNameDisplay').textContent = currentUser.name;
            document.getElementById('uniqueId').textContent = currentUser.uniqueId;
            document.getElementById('customId').value = currentUser.uniqueId;
            document.getElementById('profilePublic').checked = currentUser.isPublic;
            document.getElementById('profileName').value = currentUser.name;
            document.getElementById('profileBio').value = currentUser.bio || '';
            document.getElementById('profileLocation').value = currentUser.location || '';
        }
        
        // Генерация уникального ID
        function generateUniqueId(name) {
            const translit = {
                'а': 'a', 'б': 'b', 'в': 'v', 'г': 'g', 'д': 'd',
                'е': 'e', 'ё': 'yo', 'ж': 'zh', 'з': 'z', 'и': 'i',
                'й': 'y', 'к': 'k', 'л': 'l', 'м': 'm', 'н': 'n',
                'о': 'o', 'п': 'p', 'р': 'r', 'с': 's', 'т': 't',
                'у': 'u', 'ф': 'f', 'х': 'h', 'ц': 'ts', 'ч': 'ch',
                'ш': 'sh', 'щ': 'sch', 'ъ': '', 'ы': 'y', 'ь': '',
                'э': 'e', 'ю': 'yu', 'я': 'ya'
            };
            
            let result = '';
            for (let char of name.toLowerCase()) {
                result += translit[char] || char;
            }
            
            const randomSuffix = Math.random().toString(36).substring(2, 6);
            return result + '-' + randomSuffix + '.канал';
        }
        
        // Инициализация обработчиков событий
        function initEventListeners() {
            // Авторизация
            document.getElementById('closeAuth').addEventListener('click', () => {
                if (!currentUser) return;
                authModal.style.display = 'none';
            });
            
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
                    addAccountToAvailable(user);
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
                const isPublic = document.getElementById('makePublic').checked;
                
                if (cloudStorage.findUserByEmail(email)) {
                    alert('Пользователь с таким email уже существует');
                    return;
                }
                
                const uniqueId = generateUniqueId(name);
                
                const newUser = {
                    id: Date.now(),
                    name,
                    email,
                    password,
                    uniqueId,
                    isPublic,
                    birthday,
                    gender,
                    avatar: null,
                    bio: '',
                    location: '',
                    registrationDate: new Date().toISOString(),
                    family: []
                };
                
                cloudStorage.addUser(newUser);
                
                currentUser = newUser;
                localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                addAccountToAvailable(newUser);
                
                showMainApp();
            });
            
            // Профиль
            document.getElementById('profileBtn').addEventListener('click', () => {
                profileModal.style.display = 'flex';
            });
            
            document.getElementById('closeProfile').addEventListener('click', () => {
                profileModal.style.display = 'none';
            });
            
            document.getElementById('saveProfile').addEventListener('click', () => {
                const customId = document.getElementById('customId').value;
                const isPublic = document.getElementById('profilePublic').checked;
                const name = document.getElementById('profileName').value;
                const bio = document.getElementById('profileBio').value;
                const location = document.getElementById('profileLocation').value;
                
                if (customId && customId !== currentUser.uniqueId) {
                    if (cloudStorage.findUserByUniqueId(customId)) {
                        alert('Этот ID уже занят');
                        return;
                    }
                    
                    currentUser.uniqueId = customId;
                }
                
                currentUser.isPublic = isPublic;
                currentUser.name = name;
                currentUser.bio = bio;
                currentUser.location = location;
                
                cloudStorage.updateUser(currentUser);
                localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                updateUserInterface();
                profileModal.style.display = 'none';
                
                cloudStorage.showStatus('Профиль обновлен!');
            });
            
            // Управление семьей
            document.getElementById('manageFamilyBtn').addEventListener('click', () => {
                familyModal.style.display = 'flex';
                updateFamilyMembersList();
            });
            
            document.getElementById('openFamilyModal').addEventListener('click', () => {
                familyModal.style.display = 'flex';
                updateFamilyMembersList();
            });
            
            document.getElementById('closeFamily').addEventListener('click', () => {
                familyModal.style.display = 'none';
            });
            
            document.getElementById('searchFamilyMemberBtn').addEventListener('click', searchFamilyMember);
            
            document.getElementById('familySearchInput').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    searchFamilyMember();
                }
            });
            
            // Переключение аккаунтов
            document.getElementById('switchAccountBtn').addEventListener('click', showAccountsModal);
            
            document.getElementById('closeAccounts').addEventListener('click', () => {
                accountsModal.style.display = 'none';
            });
            
            document.getElementById('addAccountBtn').addEventListener('click', () => {
                accountsModal.style.display = 'none';
                showAuthModal();
            });
            
            // Создание поста
            document.getElementById('openPostModalInput').addEventListener('click', () => {
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
            
            document.getElementById('postUploadArea').addEventListener('click', () => {
                document.getElementById('postUpload').click();
            });
            
            document.getElementById('postUpload').addEventListener('change', function(e) {
                if (e.target.files && e.target.files[0]) {
                    const file = e.target.files[0];
                    const reader = new FileReader();
                    
                    reader.onload = function(event) {
                        if (file.type.startsWith('image/')) {
                            document.getElementById('postPreview').src = event.target.result;
                            document.getElementById('postPreview').style.display = 'block';
                            document.getElementById('postVideoPreview').style.display = 'none';
                        } else if (file.type.startsWith('video/')) {
                            document.getElementById('postVideoPreview').src = event.target.result;
                            document.getElementById('postVideoPreview').style.display = 'block';
                            document.getElementById('postPreview').style.display = 'none';
                        }
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            document.getElementById('publishPostBtn').addEventListener('click', () => {
                const postText = document.getElementById('postText').value;
                const postImage = document.getElementById('postPreview').style.display !== 'none' ? 
                    document.getElementById('postPreview').src : null;
                const postVideo = document.getElementById('postVideoPreview').style.display !== 'none' ? 
                    document.getElementById('postVideoPreview').src : null;
                const showToNewUsers = document.getElementById('showToNewUsers').checked;
                const familyOnly = document.getElementById('familyOnly').checked;
                
                if (postText.trim() === '' && !postImage && !postVideo) {
                    alert('Пожалуйста, добавьте текст, изображение или видео к посту');
                    return;
                }
                
                const newPost = {
                    id: Date.now(),
                    userId: currentUser.id,
                    userName: currentUser.name,
                    userAvatar: currentUser.avatar,
                    text: postText,
                    image: postImage,
                    video: postVideo,
                    showToNewUsers: showToNewUsers,
                    familyOnly: familyOnly,
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
                document.getElementById('postVideoPreview').src = '';
                document.getElementById('postVideoPreview').style.display = 'none';
                document.getElementById('showToNewUsers').checked = false;
                document.getElementById('familyOnly').checked = false;
                
                cloudStorage.showStatus('Пост опубликован и синхронизирован');
            });
            
            // Создание поста из главной страницы
            document.getElementById('openPostModalInput').addEventListener('keypress', function(e) {
                if (e.key === 'Enter' && this.value.trim() !== '') {
                    const postText = this.value;
                    const showToNewUsers = document.getElementById('showToNewUsersMain').checked;
                    const familyOnly = document.getElementById('familyOnlyMain').checked;
                    
                    const newPost = {
                        id: Date.now(),
                        userId: currentUser.id,
                        userName: currentUser.name,
                        userAvatar: currentUser.avatar,
                        text: postText,
                        image: null,
                        video: null,
                        showToNewUsers: showToNewUsers,
                        familyOnly: familyOnly,
                        likes: [],
                        comments: [],
                        timestamp: new Date().toISOString()
                    };
                    
                    cloudStorage.addPost(newPost);
                    loadPosts();
                    
                    this.value = '';
                    document.getElementById('showToNewUsersMain').checked = false;
                    document.getElementById('familyOnlyMain').checked = false;
                    
                    cloudStorage.showStatus('Пост опубликован и синхронизирован');
                }
            });
            
            // Чувства/действия
            document.getElementById('openFeelingModal').addEventListener('click', () => {
                feelingModal.style.display = 'flex';
            });
            
            document.getElementById('closeFeeling').addEventListener('click', () => {
                feelingModal.style.display = 'none';
            });
            
            document.querySelectorAll('.feeling-option').forEach(option => {
                option.addEventListener('click', function() {
                    const feeling = this.dataset.feeling;
                    const feelingText = this.querySelector('span').textContent;
                    
                    document.getElementById('postText').value = `Чувствую себя ${feelingText.toLowerCase()} ${document.getElementById('postText').value}`;
                    feelingModal.style.display = 'none';
                    postModal.style.display = 'flex';
                });
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
            
            document.getElementById('storyUploadArea').addEventListener('click', () => {
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
                        image: backgroundImage.slice(5, -2),
                        timestamp: new Date().toISOString()
                    };
                    
                    cloudStorage.addStory(newStory);
                    loadStories();
                    storyModal.style.display = 'none';
                    
                    storyPreview.style.backgroundImage = 'none';
                    storyPreview.textContent = 'Ваша история будет здесь';
                    
                    cloudStorage.showStatus('История опубликована и синхронизирована');
                } else {
                    alert('Пожалуйста, загрузите изображение для истории');
                }
            });
            
            // Навигация
            document.querySelectorAll('.nav-icon').forEach(element => {
                if (element.dataset.page) {
                    element.addEventListener('click', function() {
                        document.querySelectorAll('.nav-icon').forEach(icon => icon.classList.remove('active'));
                        this.classList.add('active');
                        
                        if (this.dataset.page !== 'home') {
                            cloudStorage.showStatus(`Раздел "${this.dataset.page}" находится в разработке`);
                        }
                    });
                }
            });
            
            // Поиск
            searchInput.addEventListener('input', function() {
                const query = this.value.trim();
                if (query.length > 0) {
                    const results = cloudStorage.searchUsers(query);
                    displaySearchResults(results);
                } else {
                    searchResults.style.display = 'none';
                }
            });
            
            document.addEventListener('click', function(e) {
                if (!searchInput.contains(e.target) && !searchResults.contains(e.target)) {
                    searchResults.style.display = 'none';
                }
            });
            
            // User Profile Modal
            document.getElementById('closeUserProfile').addEventListener('click', () => {
                userProfileModal.style.display = 'none';
            });
            
            // User Profile Tabs
            document.querySelectorAll('.user-profile-tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    switchUserProfileTab(this.dataset.tab);
                });
            });
            
            // Клики по элементам для открытия профиля пользователя
            document.addEventListener('click', function(e) {
                // Клик по результату поиска
                if (e.target.closest('.search-result-item')) {
                    const userItem = e.target.closest('.search-result-item');
                    const userId = parseInt(userItem.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по члену семьи
                if (e.target.closest('.family-member') && !e.target.closest('.family-member').classList.contains('add-family')) {
                    const familyMember = e.target.closest('.family-member');
                    const userId = parseInt(familyMember.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по контакту
                if (e.target.closest('.contact')) {
                    const contact = e.target.closest('.contact');
                    const userId = parseInt(contact.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по имени пользователя в посте
                if (e.target.closest('.post-user .name')) {
                    const postHeader = e.target.closest('.post-header');
                    const avatar = postHeader.querySelector('.avatar');
                    const userId = parseInt(avatar.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по имени пользователя в комментарии
                if (e.target.closest('.comment .name')) {
                    const comment = e.target.closest('.comment');
                    const avatar = comment.querySelector('.avatar');
                    const userId = parseInt(avatar.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по аватару в посте
                if (e.target.closest('.post-header .avatar')) {
                    const avatar = e.target.closest('.post-header .avatar');
                    const userId = parseInt(avatar.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
                
                // Клик по аватару в комментарии
                if (e.target.closest('.comment .avatar')) {
                    const avatar = e.target.closest('.comment .avatar');
                    const userId = parseInt(avatar.dataset.userId);
                    if (userId) {
                        openUserProfile(userId);
                    }
                }
            });
        }
        
        // Отображение результатов поиска
        function displaySearchResults(results) {
            searchResults.innerHTML = '';
            
            if (results.length === 0) {
                searchResults.innerHTML = '<div class="search-result-item">Пользователи не найдены</div>';
            } else {
                results.forEach(user => {
                    const item = document.createElement('div');
                    item.className = 'search-result-item';
                    item.dataset.userId = user.id;
                    item.innerHTML = `
                        <div class="search-result-avatar" style="${user.avatar ? `background-image: url(${user.avatar})` : ''}">
                            ${!user.avatar ? user.name.split(' ').map(n => n[0]).join('') : ''}
                        </div>
                        <div>
                            <div><strong>${user.name}</strong></div>
                            <small>${user.uniqueId}</small>
                        </div>
                    `;
                    searchResults.appendChild(item);
                });
            }
            
            searchResults.style.display = 'block';
        }
        
        // Переключение на другой аккаунт
        function switchAccount(accountId) {
            const user = cloudStorage.findUserById(accountId);
            if (user) {
                currentUser = user;
                localStorage.setItem('facexi_current_user', JSON.stringify(currentUser));
                updateUserInterface();
                loadPosts();
                loadStories();
                loadFamilyMembers();
                accountsModal.style.display = 'none';
                cloudStorage.showStatus(`Переключено на аккаунт: ${user.name}`);
            }
        }
        
        // Показать модальное окно переключения аккаунтов
        function showAccountsModal() {
            const accountsList = document.getElementById('accountsList');
            accountsList.innerHTML = '';
            
            // Добавляем текущий аккаунт
            if (currentUser) {
                const currentAccountElement = document.createElement('div');
                currentAccountElement.className = 'account-item active';
                currentAccountElement.innerHTML = `
                    <div class="account-avatar" style="${currentUser.avatar ? `background-image: url(${currentUser.avatar})` : ''}">
                        ${!currentUser.avatar ? currentUser.name.split(' ').map(n => n[0]).join('') : ''}
                    </div>
                    <div class="account-info">
                        <div class="account-name">${currentUser.name}</div>
                        <div class="account-id">${currentUser.uniqueId}</div>
                    </div>
                    <div style="color: var(--primary);">
                        <i class="fas fa-check"></i>
                    </div>
                `;
                accountsList.appendChild(currentAccountElement);
            }
            
            // Добавляем другие доступные аккаунты
            availableAccounts.forEach(account => {
                if (account.id !== currentUser.id) {
                    const accountElement = document.createElement('div');
                    accountElement.className = 'account-item';
                    accountElement.innerHTML = `
                        <div class="account-avatar" style="${account.avatar ? `background-image: url(${account.avatar})` : ''}">
                            ${!account.avatar ? account.name.split(' ').map(n => n[0]).join('') : ''}
                        </div>
                        <div class="account-info">
                            <div class="account-name">${account.name}</div>
                            <div class="account-id">${account.uniqueId}</div>
                        </div>
                    `;
                    accountElement.addEventListener('click', () => {
                        switchAccount(account.id);
                    });
                    accountsList.appendChild(accountElement);
                }
            });
            
            accountsModal.style.display = 'flex';
        }
        
        // Загрузка членов семьи
        function loadFamilyMembers() {
            const familyContainer = document.getElementById('familyMembersContainer');
            familyContainer.innerHTML = '';
            
            if (!currentUser.family || currentUser.family.length === 0) {
                familyContainer.innerHTML = '<div style="text-align: center; padding: 20px; color: var(--text-secondary);">Добавьте членов семьи</div>';
                
                // Добавляем кнопку добавления
                const addButton = document.createElement('div');
                addButton.className = 'family-member add-family';
                addButton.innerHTML = `<i class="fas fa-plus"></i>`;
                addButton.addEventListener('click', () => {
                    familyModal.style.display = 'flex';
                    updateFamilyMembersList();
                });
                familyContainer.appendChild(addButton);
                
                return;
            }
            
            currentUser.family.forEach(memberId => {
                const member = cloudStorage.findUserById(memberId);
                if (member) {
                    const memberElement = document.createElement('div');
                    memberElement.className = 'family-member';
                    memberElement.dataset.userId = member.id;
                    memberElement.innerHTML = `
                        <div class="family-avatar" style="${member.avatar ? `background-image: url(${member.avatar})` : ''}">
                            ${!member.avatar ? member.name.split(' ').map(n => n[0]).join('') : ''}
                        </div>
                        <div>${member.name}</div>
                    `;
                    familyContainer.appendChild(memberElement);
                }
            });
            
            // Добавляем кнопку добавления
            const addButton = document.createElement('div');
            addButton.className = 'family-member add-family';
            addButton.innerHTML = `<i class="fas fa-plus"></i>`;
            addButton.addEventListener('click', () => {
                familyModal.style.display = 'flex';
                updateFamilyMembersList();
            });
            familyContainer.appendChild(addButton);
        }
        
        // Поиск пользователя для добавления в семью
        function searchFamilyMember() {
            const searchInput = document.getElementById('familySearchInput');
            const query = searchInput.value.trim();
            
            if (query.length === 0) {
                document.getElementById('familySearchResults').innerHTML = '';
                return;
            }
            
            const users = cloudStorage.searchUsers(query);
            const resultsContainer = document.getElementById('familySearchResults');
            resultsContainer.innerHTML = '';
            
            if (users.length === 0) {
                resultsContainer.innerHTML = '<div style="padding: 10px; text-align: center; color: var(--text-secondary);">Пользователи не найдены</div>';
                return;
            }
            
            users.forEach(user => {
                // Пропускаем текущего пользователя и уже добавленных в семью
                if (user.id === currentUser.id || 
                    (currentUser.family && currentUser.family.includes(user.id))) {
                    return;
                }
                
                const userElement = document.createElement('div');
                userElement.className = 'family-member-item';
                userElement.innerHTML = `
                    <div class="family-member-info">
                        <div class="family-member-avatar" style="${user.avatar ? `background-image: url(${user.avatar})` : ''}">
                            ${!user.avatar ? user.name.split(' ').map(n => n[0]).join('') : ''}
                        </div>
                        <div>
                            <div>${user.name}</div>
                            <div style="font-size: 12px; color: var(--text-secondary);">${user.uniqueId}</div>
                        </div>
                    </div>
                    <div class="add-family-member" data-user-id="${user.id}">
                        <i class="fas fa-plus"></i> Добавить
                    </div>
                `;
                resultsContainer.appendChild(userElement);
            });
            
            // Добавляем обработчики событий для кнопок добавления
            document.querySelectorAll('.add-family-member').forEach(button => {
                button.addEventListener('click', function() {
                    const userId = parseInt(this.dataset.userId);
                    addFamilyMember(userId);
                });
            });
        }
        
        // Добавление члена семьи
        function addFamilyMember(userId) {
            if (!currentUser.family) {
                currentUser.family = [];
            }
            
            // Проверяем, не добавлен ли уже этот пользователь
            if (currentUser.family.includes(userId)) {
                alert('Этот пользователь уже в вашей семье');
                return;
            }
            
            currentUser.family.push(userId);
            cloudStorage.updateUser(currentUser);
            loadFamilyMembers();
            document.getElementById('familySearchInput').value = '';
            document.getElementById('familySearchResults').innerHTML = '';
            
            // Обновляем список членов семьи в модальном окне
            updateFamilyMembersList();
            
            cloudStorage.showStatus('Пользователь добавлен в семью');
        }
        
        // Удаление члена семьи
        function removeFamilyMember(userId) {
            if (!currentUser.family) return;
            
            currentUser.family = currentUser.family.filter(id => id !== userId);
            cloudStorage.updateUser(currentUser);
            loadFamilyMembers();
            updateFamilyMembersList();
            
            cloudStorage.showStatus('Пользователь удален из семьи');
        }
        
        // Обновление списка членов семьи в модальном окне
        function updateFamilyMembersList() {
            const membersList = document.getElementById('familyMembersList');
            membersList.innerHTML = '';
            
            if (!currentUser.family || currentUser.family.length === 0) {
                membersList.innerHTML = '<div style="padding: 10px; text-align: center; color: var(--text-secondary);">Нет членов семьи</div>';
                return;
            }
            
            currentUser.family.forEach(memberId => {
                const member = cloudStorage.findUserById(memberId);
                if (member) {
                    const memberElement = document.createElement('div');
                    memberElement.className = 'family-member-item';
                    memberElement.innerHTML = `
                        <div class="family-member-info">
                            <div class="family-member-avatar" style="${member.avatar ? `background-image: url(${member.avatar})` : ''}">
                                ${!member.avatar ? member.name.split(' ').map(n => n[0]).join('') : ''}
                            </div>
                            <div>
                                <div>${member.name}</div>
                                <div style="font-size: 12px; color: var(--text-secondary);">${member.uniqueId}</div>
                            </div>
                        </div>
                        <div class="remove-family-member" data-user-id="${member.id}">
                            <i class="fas fa-times"></i>
                        </div>
                    `;
                    membersList.appendChild(memberElement);
                }
            });
            
            // Добавляем обработчики событий для кнопок удаления
            document.querySelectorAll('.remove-family-member').forEach(button => {
                button.addEventListener('click', function() {
                    const userId = parseInt(this.dataset.userId);
                    removeFamilyMember(userId);
                });
            });
        }
        
        // Открытие профиля пользователя
        function openUserProfile(userId) {
            const user = cloudStorage.findUserById(userId);
            if (!user) {
                alert('Пользователь не найден');
                return;
            }
            
            viewingUser = user;
            
            // Заполняем информацию о пользователе
            document.getElementById('userProfileName').textContent = user.name;
            document.getElementById('userProfileFullName').textContent = user.name;
            document.getElementById('userProfileUniqueId').textContent = user.uniqueId;
            
            // Аватар
            const avatar = document.getElementById('userProfileAvatar');
            if (user.avatar) {
                avatar.style.backgroundImage = `url(${user.avatar})`;
                avatar.textContent = '';
            } else {
                avatar.style.backgroundImage = '';
                avatar.textContent = user.name.split(' ').map(n => n[0]).join('');
            }
            
            // Био
            const bio = user.bio || 'Пользователь еще не добавил информацию о себе';
            document.getElementById('userProfileBio').textContent = bio;
            
            // Местоположение
            const locationElement = document.getElementById('userProfileLocation');
            if (user.location) {
                locationElement.innerHTML = `<i class="fas fa-map-marker-alt"></i><span>${user.location}</span>`;
                locationElement.style.display = 'flex';
            } else {
                locationElement.style.display = 'none';
            }
            
            // Статистика
            const posts = cloudStorage.getPosts().filter(post => post.userId === user.id);
            const stories = cloudStorage.getStories().filter(story => story.userId === user.id);
            const familyCount = user.family ? user.family.length : 0;
            
            document.getElementById('userProfilePostsCount').textContent = posts.length;
            document.getElementById('userProfileStoriesCount').textContent = stories.length;
            document.getElementById('userProfileFamilyCount').textContent = familyCount;
            
            // Заполняем вкладку "Информация"
            document.getElementById('userProfileAboutName').textContent = user.name;
            document.getElementById('userProfileAboutId').textContent = user.uniqueId;
            
            if (user.birthday) {
                const birthday = new Date(user.birthday);
                document.getElementById('userProfileAboutBirthday').textContent = birthday.toLocaleDateString('ru-RU');
            } else {
                document.getElementById('userProfileAboutBirthday').textContent = 'Не указана';
            }
            
            if (user.gender) {
                document.getElementById('userProfileAboutGender').textContent = 
                    user.gender === 'male' ? 'Мужской' : 'Женский';
            } else {
                document.getElementById('userProfileAboutGender').textContent = 'Не указан';
            }
            
            if (user.registrationDate) {
                const regDate = new Date(user.registrationDate);
                document.getElementById('userProfileAboutRegDate').textContent = regDate.toLocaleDateString('ru-RU');
            } else {
                document.getElementById('userProfileAboutRegDate').textContent = 'Не указана';
            }
            
            // Био в информации
            const aboutBio = document.getElementById('userProfileAboutBio');
            if (user.bio) {
                aboutBio.textContent = user.bio;
                document.getElementById('userProfileAboutBioItem').style.display = 'flex';
            } else {
                document.getElementById('userProfileAboutBioItem').style.display = 'none';
            }
            
            // Местоположение в информации
            const aboutLocation = document.getElementById('userProfileAboutLocation');
            if (user.location) {
                aboutLocation.textContent = user.location;
                document.getElementById('userProfileAboutLocationItem').style.display = 'flex';
            } else {
                document.getElementById('userProfileAboutLocationItem').style.display = 'none';
            }
            
            // Загружаем посты пользователя
            loadUserProfilePosts(user.id);
            
            // Загружаем истории пользователя
            loadUserProfileStories(user.id);
            
            // Показываем модальное окно
            userProfileModal.style.display = 'flex';
            
            // Активируем первую вкладку
            switchUserProfileTab('posts');
        }
        
        // Загрузка постов пользователя для профиля
        function loadUserProfilePosts(userId) {
            const postsContainer = document.getElementById('userProfilePostsContainer');
            postsContainer.innerHTML = '';
            
            const allPosts = cloudStorage.getPosts();
            const userPosts = allPosts.filter(post => post.userId === userId);
            
            // Фильтруем посты в зависимости от настроек видимости
            const currentUserId = currentUser ? currentUser.id : null;
            const filteredPosts = userPosts.filter(post => {
                // Если пользователь просматривает свой собственный профиль, показываем все посты
                if (currentUserId === userId) return true;
                
                // Если пост только для семьи, проверяем, находится ли текущий пользователь в семье автора
                if (post.familyOnly) {
                    const postAuthor = cloudStorage.findUserById(post.userId);
                    return postAuthor && postAuthor.family && postAuthor.family.includes(currentUserId);
                }
                
                // Если пост для новых пользователей, проверяем дату регистрации
                if (post.showToNewUsers && currentUser) {
                    const userRegDate = new Date(currentUser.registrationDate);
                    const postDate = new Date(post.timestamp);
                    return userRegDate >= postDate;
                }
                
                // Во всех остальных случаях показываем пост
                return true;
            });
            
            if (filteredPosts.length === 0) {
                postsContainer.innerHTML = '<div style="text-align: center; padding: 20px; color: var(--text-secondary);">Нет доступных постов</div>';
                return;
            }
            
            filteredPosts.forEach(post => {
                const postElement = document.createElement('div');
                postElement.className = 'post';
                
                let mediaContent = '';
                if (post.image) {
                    mediaContent = `<img src="${post.image}" alt="Post image" class="post-image">`;
                } else if (post.video) {
                    mediaContent = `<video controls class="post-image video-player">
                                      <source src="${post.video}" type="video/mp4">
                                      Ваш браузер не поддерживает видео.
                                   </video>`;
                }
                
                postElement.innerHTML = `
                    <div class="post-header">
                        <div class="avatar" data-user-id="${post.userId}" style="${post.userAvatar ? `background-image: url(${post.userAvatar})` : ''}">${!post.userAvatar ? post.userName.split(' ').map(n => n[0]).join('') : ''}</div>
                        <div class="post-user">
                            <div class="name">${post.userName}</div>
                            <div class="time">
                                ${formatTime(post.timestamp)} <i class="fas fa-globe-americas"></i>
                            </div>
                        </div>
                        ${post.showToNewUsers ? '<div class="post-badge">Новым пользователям</div>' : ''}
                        ${post.familyOnly ? '<div class="post-badge" style="background: var(--family);">Семья</div>' : ''}
                    </div>
                    <div class="post-content">
                        <div class="post-text">${post.text}</div>
                        ${mediaContent}
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
                        <div class="post-action-btn ${post.likes.includes(currentUserId) ? 'active' : ''}" data-post-id="${post.id}">
                            <i class="${post.likes.includes(currentUserId) ? 'fas' : 'far'} fa-thumbs-up"></i>
                            <span>Нравится</span>
                        </div>
                        <div class="post-action-btn" data-post-id="${post.id}">
                            <i class="far fa-comment"></i>
                            <span>Комментировать</span>
                        </div>
                    </div>
                    <div class="comments">
                        ${post.comments.slice(0, 2).map(comment => `
                            <div class="comment">
                                <div class="avatar" data-user-id="${comment.userId}" style="${comment.userAvatar ? `background-image: url(${comment.userAvatar})` : ''}">${!comment.userAvatar ? comment.userName.split(' ').map(n => n[0]).join('') : ''}</div>
                                <div class="comment-content">
                                    <div class="name">${comment.userName}</div>
                                    <div class="text">${comment.text}</div>
                                    <div class="comment-actions">
                                        <span class="comment-action">${formatTime(comment.timestamp)}</span>
                                    </div>
                                </div>
                            </div>
                        `).join('')}
                        ${post.comments.length > 2 ? 
                            `<div style="text-align: center; padding: 10px; color: var(--primary); cursor: pointer;">
                                Показать все ${post.comments.length} комментариев
                            </div>` : ''}
                    </div>
                `;
                
                postsContainer.appendChild(postElement);
            });
            
            // Добавляем обработчики для лайков
            document.querySelectorAll('#userProfilePostsContainer .post-action-btn[data-post-id]').forEach(button => {
                if (button.querySelector('.fa-thumbs-up')) {
                    button.addEventListener('click', function() {
                        const postId = parseInt(this.dataset.postId);
                        const posts = cloudStorage.getPosts();
                        const post = posts.find(p => p.id === postId);
                        
                        if (currentUser) {
                            if (post.likes.includes(currentUser.id)) {
                                post.likes = post.likes.filter(id => id !== currentUser.id);
                            } else {
                                post.likes.push(currentUser.id);
                            }
                            
                            cloudStorage.updatePost(post);
                            loadUserProfilePosts(viewingUser.id);
                        }
                    });
                }
            });
        }
        
        // Загрузка историй пользователя для профиля
        function loadUserProfileStories(userId) {
            const storiesContainer = document.getElementById('userProfileStoriesContainer');
            storiesContainer.innerHTML = '';
            
            const allStories = cloudStorage.getStories();
            const userStories = allStories.filter(story => story.userId === userId);
            
            if (userStories.length === 0) {
                storiesContainer.innerHTML = '<div style="text-align: center; padding: 20px; color: var(--text-secondary);">Нет доступных историй</div>';
                return;
            }
            
            userStories.forEach(story => {
                const storyElement = document.createElement('div');
                storyElement.className = 'user-profile-story';
                storyElement.innerHTML = `
                    <div class="user-profile-story-bg" style="background-image: url(${story.image})"></div>
                `;
                
                storiesContainer.appendChild(storyElement);
            });
        }
        
        // Переключение вкладок в профиле пользователя
        function switchUserProfileTab(tabName) {
            // Скрываем все вкладки и убираем активный класс
            document.querySelectorAll('.user-profile-tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            document.querySelectorAll('.user-profile-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Показываем выбранную вкладку и добавляем активный класс
            document.getElementById(`userProfile${tabName.charAt(0).toUpperCase() + tabName.slice(1)}Tab`).classList.add('active');
            document.querySelector(`.user-profile-tab[data-tab="${tabName}"]`).classList.add('active');
        }
        
        // Загрузка постов
        function loadPosts() {
            const posts = cloudStorage.getPosts();
            postsContainer.innerHTML = '';
            
            if (posts.length === 0) {
                postsContainer.innerHTML = '<div class="post"><div class="post-content"><p>Пока нет постов. Будьте первым, кто поделится чем-то интересным!</p></div></div>';
                return;
            }
            
            const userRegDate = new Date(currentUser.registrationDate);
            const filteredPosts = posts.filter(post => {
                if (post.userId === currentUser.id) return true;
                if (post.familyOnly) {
                    // Проверяем, находится ли пользователь в семье автора поста
                    const postAuthor = cloudStorage.findUserById(post.userId);
                    return postAuthor && postAuthor.family && postAuthor.family.includes(currentUser.id);
                }
                if (post.showToNewUsers) {
                    const postDate = new Date(post.timestamp);
                    return userRegDate >= postDate;
                }
                return true;
            });
            
            filteredPosts.forEach(post => {
                const postElement = document.createElement('div');
                postElement.className = 'post';
                
                let mediaContent = '';
                if (post.image) {
                    mediaContent = `<img src="${post.image}" alt="Post image" class="post-image">`;
                } else if (post.video) {
                    mediaContent = `<video controls class="post-image video-player">
                                      <source src="${post.video}" type="video/mp4">
                                      Ваш браузер не поддерживает видео.
                                   </video>`;
                }
                
                postElement.innerHTML = `
                    <div class="post-header">
                        <div class="avatar" data-user-id="${post.userId}" style="${post.userAvatar ? `background-image: url(${post.userAvatar})` : ''}">${!post.userAvatar ? post.userName.split(' ').map(n => n[0]).join('') : ''}</div>
                        <div class="post-user">
                            <div class="name">${post.userName}</div>
                            <div class="time">
                                ${formatTime(post.timestamp)} <i class="fas fa-globe-americas"></i>
                            </div>
                        </div>
                        ${post.showToNewUsers ? '<div class="post-badge">Новым пользователям</div>' : ''}
                        ${post.familyOnly ? '<div class="post-badge" style="background: var(--family);">Семья</div>' : ''}
                    </div>
                    <div class="post-content">
                        <div class="post-text">${post.text}</div>
                        ${mediaContent}
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
                                <div class="avatar" data-user-id="${comment.userId}" style="${comment.userAvatar ? `background-image: url(${comment.userAvatar})` : ''}">${!comment.userAvatar ? comment.userName.split(' ').map(n => n[0]).join('') : ''}</div>
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
            
            // Обработчики для лайков
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
            
            // Обработчики для комментариев
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
        
        // Загрузка контактов
        function loadContacts() {
            const contactsList = document.getElementById('contactsList');
            const users = cloudStorage.getUsers();
            
            // Показываем только публичных пользователей, кроме текущего
            const contacts = users.filter(user => 
                user.isPublic && user.id !== currentUser.id
            ).slice(0, 10);
            
            if (contacts.length === 0) {
                contactsList.innerHTML = '<div style="padding: 10px; text-align: center; color: var(--text-secondary);">Контакты не найдены</div>';
                return;
            }
            
            contacts.forEach(user => {
                const contactElement = document.createElement('div');
                contactElement.className = 'contact';
                contactElement.dataset.userId = user.id;
                contactElement.innerHTML = `
                    <div class="avatar" style="${user.avatar ? `background-image: url(${user.avatar})` : ''}">
                        ${!user.avatar ? user.name.split(' ').map(n => n[0]).join('') : ''}
                    </div>
                    <div>${user.name}</div>
                `;
                contactsList.appendChild(contactElement);
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
