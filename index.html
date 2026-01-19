<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestion Master IWS - Firebase</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&family=Roboto+Condensed:wght@300;400;700&display=swap" rel="stylesheet">
    
    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
    
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Roboto', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #B3E0F2 0%, #A8D5E2 100%);
            padding: 20px;
            min-height: 100vh;
        }
        
        /* Auth Modal */
        #authModal {
            display: flex;
            position: fixed;
            z-index: 10000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            align-items: center;
            justify-content: center;
        }
        
        .auth-container {
            background: white;
            padding: 40px;
            border-radius: 15px;
            width: 90%;
            max-width: 450px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }
        
        .auth-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .auth-header h2 {
            color: #0098DB;
            font-size: 2em;
            margin-bottom: 10px;
        }
        
        .auth-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 25px;
        }
        
        .auth-tab {
            flex: 1;
            padding: 12px;
            background: #e9ecef;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .auth-tab.active {
            background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%);
            color: white;
        }
        
        .auth-form {
            display: none;
        }
        
        .auth-form.active {
            display: block;
        }
        
        .auth-form-group {
            margin-bottom: 20px;
        }
        
        .auth-form-group label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 600;
        }
        
        .auth-form-group input {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 14px;
            font-family: 'Roboto', sans-serif;
        }
        
        .auth-form-group input:focus {
            outline: none;
            border-color: #0098DB;
        }
        
        .auth-submit {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s;
        }
        
        .auth-submit:hover {
            transform: translateY(-2px);
        }
        
        .auth-error {
            background: #ffe0e0;
            color: #c0392b;
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 20px;
            display: none;
        }
        
        .auth-error.show {
            display: block;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 10px 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .user-email {
            flex: 1;
            font-weight: 600;
            color: #0098DB;
        }
        
        .btn-logout {
            padding: 8px 16px;
            background: linear-gradient(135deg, #f5576c 0%, #c0392b 100%);
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: transform 0.2s;
        }
        
        .btn-logout:hover {
            transform: translateY(-2px);
        }
        
        #appContent {
            display: none;
        }
        
        .loading {
            text-align: center;
            padding: 50px;
            color: white;
            font-size: 1.5em;
        }
        
        .container { max-width: 1400px; margin: 0 auto; }
        
        header {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin-bottom: 30px;
            transition: transform 0.3s ease-in-out;
        }
        
        .header-content { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 20px; }
        .header-title { flex: 1; text-align: center; }
        h1 { color: #0098DB; font-size: 2.5em; margin-bottom: 10px; font-weight: 700; }
        .subtitle { color: #666; font-size: 1.1em; }
        
        .export-import-buttons { display: flex; gap: 10px; }
        .btn-export, .btn-import {
            padding: 10px 20px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: transform 0.2s;
        }
        .btn-export { background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%); color: white; }
        .btn-import { background: linear-gradient(135deg, #ee9ca7 0%, #ffdde1 100%); color: #333; }
        .btn-export:hover, .btn-import:hover { transform: translateY(-2px); }
        #importFileInput { display: none; }
        
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
        }
        
        .modal-content {
            background-color: white;
            margin: 5% auto;
            padding: 30px;
            border-radius: 15px;
            width: 80%;
            max-width: 800px;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            border-bottom: 2px solid #667eea;
            padding-bottom: 15px;
        }
        
        .modal-close {
            font-size: 28px;
            font-weight: bold;
            color: #999;
            cursor: pointer;
            transition: color 0.3s;
        }
        .modal-close:hover { color: #333; }
        
        .main-content { display: grid; grid-template-columns: 1fr 2fr; gap: 20px; }
        .sidebar, .content-area {
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        .sidebar { height: fit-content; }
        
        h2 {
            color: #0098DB;
            margin-bottom: 20px;
            font-size: 1.8em;
            border-bottom: 3px solid #0098DB;
            padding-bottom: 10px;
            font-weight: 700;
        }
        
        h3 { color: #764ba2; margin: 20px 0 15px; }
        .form-group { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; color: #333; font-weight: 600; font-family: 'Roboto', sans-serif; }
        
        input, select, textarea {
            width: 100%;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 14px;
            transition: border-color 0.3s;
            font-family: 'Roboto', sans-serif;
        }
        input:focus, select:focus, textarea:focus { outline: none; border-color: #0098DB; }
        textarea { resize: vertical; min-height: 80px; }
        
        .radio-group { display: flex; gap: 20px; margin-top: 8px; }
        .radio-option { display: flex; align-items: center; cursor: pointer; }
        .radio-option input[type="radio"] { width: auto; margin-right: 8px; cursor: pointer; }
        .radio-option label { margin: 0; cursor: pointer; font-weight: normal; }
        
        .checkbox-group { display: flex; flex-direction: column; gap: 12px; }
        .checkbox-option {
            display: flex;
            align-items: center;
            padding: 10px;
            background: #f8f9fa;
            border-radius: 5px;
            transition: background 0.2s;
        }
        .checkbox-option:hover { background: #e9ecef; }
        .checkbox-option input[type="checkbox"] { width: 18px; height: 18px; margin-right: 10px; cursor: pointer; }
        .checkbox-option label { margin: 0; cursor: pointer; font-weight: normal; color: #495057; }
        
        .section-depliable {
            margin-top: 20px;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            overflow: hidden;
        }
        
        .section-header {
            background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%);
            color: white;
            padding: 12px 20px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.3s;
        }
        .section-header:hover { background: linear-gradient(135deg, #3AA5D5 0%, #0086C4 100%); }
        .section-header h3 { margin: 0; color: white; font-size: 1em; }
        .section-toggle { font-size: 1.2em; transition: transform 0.3s; }
        
        .section-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            background: white;
        }
        .section-content.active { 
            max-height: 450px; 
            padding: 20px;
            overflow-y: auto;
        }
        
        button {
            background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            margin-top: 10px;
            font-family: 'Roboto', sans-serif;
        }
        button:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(0, 152, 219, 0.4); }
        button:active { transform: translateY(0); }
        .btn-secondary { background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%); margin-left: 10px; }
        
        .filters {
            margin-bottom: 20px;
            padding: 20px;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            border-radius: 10px;
            border: 3px solid #00C0B5;
            box-shadow: 0 3px 10px rgba(0, 192, 181, 0.2);
        }
        .filter-group { 
            display: inline-block; 
            margin-right: 20px; 
            margin-bottom: 15px;
            vertical-align: middle;
        }
        .filter-group label { 
            display: inline-block;
            margin-right: 10px; 
            font-weight: 600;
            font-size: 18px;
            color: #333;
        }
        .filter-group select { 
            width: auto; 
            display: inline-block; 
            padding: 12px 18px;
            font-size: 17px;
            min-width: 200px;
            border: 3px solid #00C0B5;
            background: white;
            font-family: 'Roboto', sans-serif;
        }
        .btn-filter {
            padding: 12px 28px;
            font-size: 17px;
            margin-right: 10px;
            vertical-align: middle;
            background: linear-gradient(135deg, #00C0B5 0%, #00a89f 100%);
        }
        .btn-reset {
            background: linear-gradient(135deg, #00C0B5 0%, #00a89f 100%);
            padding: 12px 28px;
            font-size: 17px;
            vertical-align: middle;
            margin-left: 0;
        }
        
        .resultats-count {
            display: none;
            margin-top: 15px;
            padding: 15px 25px;
            background: white;
            border-radius: 8px;
            font-weight: 600;
            font-size: 18px;
            color: #0098DB;
            border: 2px solid #0098DB;
            text-align: center;
            box-shadow: 0 2px 8px rgba(0, 152, 219, 0.15);
        }
        
        .student-card {
            background: #f8f9fa;
            padding: 15px 20px;
            border-radius: 10px;
            margin-bottom: 10px;
            border-left: 5px solid #0098DB;
            transition: all 0.3s;
            cursor: pointer;
        }
        .student-card.h2o { border-left-color: #00a8e8; }
        .student-card.h2o.incomplete {
            border-left-color: #e74c3c;
            background: linear-gradient(to right, #ffe0e0 0%, #f8f9fa 100%);
        }
        .student-card:hover { background: #e9ecef; transform: translateX(5px); }
        .student-card.expanded { background: white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); cursor: default; }
        .student-card.expanded:hover { transform: none; }
        
        .student-card-compact { display: flex; justify-content: space-between; align-items: center; }
        .student-card-details { display: none; margin-top: 20px; padding-top: 20px; border-top: 2px solid #e9ecef; }
        .student-card.expanded .student-card-details { display: block; }
        
        .student-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; }
        .student-name { font-size: 1.3em; font-weight: bold; color: #333; }
        .badges { display: flex; gap: 10px; }
        .badge-warning {
            background: #e74c3c;
            color: white;
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 0.85em;
            margin-left: 8px;
            font-weight: 600;
        }
        
        .student-promo { background: #0098DB; color: white; padding: 5px 15px; border-radius: 20px; font-size: 0.9em; }
        .student-parcours { padding: 5px 15px; border-radius: 20px; font-size: 0.9em; font-weight: 600; }
        .parcours-classique { background: #e8eaf6; color: #5e35b1; }
        .parcours-h2o { background: #b3e5fc; color: #0277bd; }
        
        .student-info { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-top: 10px; }
        .info-item { padding: 8px; background: white; border-radius: 5px; }
        .info-label { font-weight: 600; color: #0098DB; font-size: 0.9em; }
        .info-value { color: #555; margin-top: 3px; }
        
        .actions { margin-top: 15px; text-align: right; }
        .btn-small { padding: 8px 15px; font-size: 14px; margin-left: 5px; }
        .btn-delete { background: linear-gradient(135deg, #f5576c 0%, #c0392b 100%); }
        .btn-edit { background: linear-gradient(135deg, #f093fb 0%, #764ba2 100%); }
        
        .empty-state { text-align: center; padding: 50px; color: #999; }
        .empty-state-icon { font-size: 4em; margin-bottom: 20px; }
        
        .stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; margin-bottom: 25px; }
        .stat-card {
            background: linear-gradient(135deg, #00C0B5 0%, #00a89f 100%);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }
        .stat-card.h2o-stat { background: linear-gradient(135deg, #00a8e8 0%, #0077b6 100%); }
        .stat-number { font-size: 2.5em; font-weight: bold; }
        .stat-label { font-size: 0.9em; opacity: 0.9; }
        
        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            border-bottom: 3px solid #0098DB;
        }
        
        .tab {
            padding: 15px 30px;
            background: #e9ecef;
            border: none;
            border-radius: 10px 10px 0 0;
            font-size: 17px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            color: #666;
        }
        
        .tab:hover {
            background: #dee2e6;
        }
        
        .tab.active {
            background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%);
            color: white;
            transform: translateY(3px);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .footer-maj {
            text-align: center;
            padding: 15px;
            margin-top: 30px;
            color: #fff;
            font-size: 0.85em;
            opacity: 0.8;
            font-family: 'Roboto', sans-serif;
        }
        
        .competences-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            padding: 10px;
        }
        
        .ue-card {
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: all 0.3s ease;
            border-left: 5px solid #C8C4BC;
        }
        
        .ue-card:hover {
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
            transform: translateY(-2px);
        }
        
        .ue-header {
            background: linear-gradient(135deg, #D9D5CE 0%, #C8C4BC 100%);
            color: white;
            padding: 20px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.3s;
        }
        
        .ue-header:hover {
            background: linear-gradient(135deg, #CCC8C1 0%, #BBB7AF 100%);
        }
        
        .ue-title {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.2em;
            font-weight: 600;
            font-family: 'Roboto', sans-serif;
        }
        
        .ue-icon {
            font-size: 1.5em;
            background: rgba(255, 255, 255, 0.5);
            padding: 8px 12px;
            border-radius: 8px;
        }
        
        .ue-toggle {
            font-size: 1.3em;
            transition: transform 0.3s;
        }
        
        .ue-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease-out;
            background: white;
        }
        
        .ue-content.active {
            max-height: 600px;
            padding: 25px;
            overflow-y: auto;
        }
        
        .ue-description {
            color: #555;
            line-height: 1.6;
            margin-bottom: 20px;
            font-size: 1.05em;
            font-family: 'Roboto', sans-serif;
            text-align: justify;
        }
        
        .competences-titre {
            color: #A8A49C;
            font-weight: 600;
            font-size: 1.1em;
            margin-bottom: 12px;
            font-family: 'Roboto', sans-serif;
        }
        
        .competences-liste {
            list-style: none;
            padding: 0;
        }
        
        .competences-liste li {
            padding: 10px 0;
            padding-left: 30px;
            position: relative;
            color: #444;
            line-height: 1.5;
            font-family: 'Roboto', sans-serif;
        }
        
        .competences-liste li:before {
            content: "✓";
            position: absolute;
            left: 0;
            color: #C8C4BC;
            font-weight: bold;
            font-size: 1.2em;
        }
        
        @media screen and (max-width: 768px) {
            body {
                padding: 10px;
            }
            
            .container {
                max-width: 100%;
            }
            
            header {
                padding: 15px;
            }
            
            h1 {
                font-size: 1.8em;
            }
            
            .subtitle {
                font-size: 0.9em;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            .export-import-buttons {
                flex-direction: column;
                width: 100%;
            }
            
            .btn-export, .btn-import {
                width: 100%;
                margin-bottom: 10px;
            }
            
            .main-content {
                grid-template-columns: 1fr;
                gap: 15px;
            }
            
            .sidebar {
                order: 2;
            }
            
            .content-area {
                order: 1;
            }
            
            .stats {
                grid-template-columns: 1fr;
                gap: 10px;
            }
            
            .filters {
                padding: 15px;
            }
            
            .filter-group {
                display: block;
                width: 100%;
                margin-right: 0;
                margin-bottom: 15px;
            }
            
            .filter-group label {
                display: block;
                margin-bottom: 8px;
            }
            
            .filter-group select,
            #filterNom {
                width: 100% !important;
                min-width: 100% !important;
            }
            
            .btn-filter, .btn-reset {
                width: 100%;
                margin: 5px 0;
            }
            
            .tabs {
                flex-direction: column;
                gap: 5px;
            }
            
            .tab {
                width: 100%;
                text-align: center;
            }
            
            .student-card-compact {
                flex-direction: column;
                gap: 10px;
            }
            
            .badges {
                justify-content: center;
            }
            
            .student-info {
                grid-template-columns: 1fr;
            }
            
            .actions {
                text-align: center;
            }
            
            .btn-small {
                display: block;
                width: 100%;
                margin: 5px 0;
            }
            
            h2 {
                font-size: 1.5em;
            }
            
            .form-group {
                margin-bottom: 15px;
            }
            
            button {
                width: 100%;
                margin-top: 10px;
            }
            
            .btn-secondary {
                margin-left: 0;
                margin-top: 10px;
            }
            
            .radio-group {
                flex-direction: column;
                gap: 10px;
            }
        }
        
        @media screen and (max-width: 768px) {
            header {
                position: sticky;
                top: 0;
                z-index: 999;
                margin-bottom: 15px;
                border-radius: 0 0 15px 15px;
                padding: 10px;
            }
            
            header.header-hidden {
                transform: translateY(-100%);
            }
            
            h1 {
                font-size: 1.3em;
                margin-bottom: 5px;
            }
            
            .subtitle {
                display: none;
            }
            
            .export-import-buttons {
                display: none !important;
            }
            
            .user-email {
                display: none;
            }
        }
        
        @media screen and (max-width: 480px) {
            h1 {
                font-size: 1.5em;
            }
            
            .stat-number {
                font-size: 2em;
            }
            
            .stat-label {
                font-size: 0.85em;
            }
            
            canvas {
                max-height: 250px !important;
            }
            
            
            /* Sur mobile: cacher la sidebar par défaut */
            .sidebar {
                display: none !important;
            }
            
            .main-content {
                grid-template-columns: 1fr !important;
            }
            
            /* Montrer la sidebar seulement dans l'onglet étudiants */
            #liste-etudiants .sidebar-mobile {
                display: block !important;
                width: 100% !important;
                margin-bottom: 20px !important;
                background: white !important;
                padding: 15px !important;
                border-radius: 10px !important;
            }
            
            /* Navigation bottom mobile */
            .tabs {
                position: fixed !important;
                bottom: 0 !important;
                left: 0 !important;
                right: 0 !important;
                z-index: 1000 !important;
                flex-direction: row !important;
                gap: 0 !important;
                margin: 0 !important;
                padding: 0 !important;
                background: white !important;
                border-top: 2px solid #0098DB !important;
                border-bottom: none !important;
                box-shadow: 0 -4px 20px rgba(0, 0, 0, 0.1) !important;
            }
            
            .tab {
                flex: 1 !important;
                padding: 10px 5px !important;
                font-size: 10px !important;
                border-radius: 0 !important;
                flex-direction: column !important;
                gap: 2px !important;
                border-right: 1px solid #e9ecef !important;
            }
            
            .tab:last-child {
                border-right: none !important;
            }
            
            .tab.active {
                transform: translateY(0) !important;
                background: linear-gradient(180deg, #e3f5ff 0%, white 100%) !important;
            }
            
            .tab-icon {
                font-size: 20px !important;
            }
            
            .content-area {
                padding-bottom: 80px !important;
            }
        }
    
        /* Cacher les boutons du header (maintenant dans l'onglet Admin) */
        .export-import-buttons {
            display: none !important;
        }
        
        #btnAccessRequests {
            display: none !important;
        }
        
</style>
</head>
<body>
    <!-- Modal d'authentification -->
    <div id="authModal">
        <div class="auth-container">
            <div class="auth-header">
                <h2>🎓 Gestion Master IWS</h2>
                <p style="color: #666; margin-top: 10px;">Connectez-vous pour accéder à l'application</p>
            </div>
            
            <div class="auth-error" id="authError"></div>
            
            <div class="auth-tabs">
                <button class="auth-tab active" onclick="switchAuthTab('login')">Connexion</button>
                <button class="auth-tab" onclick="switchAuthTab('register')">Inscription</button>
            </div>
            
            <!-- Formulaire de connexion -->
            <form id="loginForm" class="auth-form active" onsubmit="handleLogin(event)">
                <div class="auth-form-group">
                    <label for="loginEmail">Email</label>
                    <input type="email" id="loginEmail" required placeholder="votre.email@exemple.com">
                </div>
                <div class="auth-form-group">
                    <label for="loginPassword">Mot de passe</label>
                    <input type="password" id="loginPassword" required placeholder="••••••••">
                </div>
                <button type="submit" class="auth-submit">Se connecter</button>
            </form>
            
            <!-- Formulaire d'inscription -->
            <form id="registerForm" class="auth-form" onsubmit="handleRegister(event)">
                <div class="auth-form-group">
                    <label for="registerEmail">Email</label>
                    <input type="email" id="registerEmail" required placeholder="votre.email@exemple.com">
                </div>
                <div class="auth-form-group">
                    <label for="registerPassword">Mot de passe</label>
                    <input type="password" id="registerPassword" required placeholder="••••••••" minlength="6">
                    <small style="color: #666; font-size: 0.85em; margin-top: 5px; display: block;">Minimum 6 caractères</small>
                </div>
                <div class="auth-form-group">
                    <label for="registerPasswordConfirm">Confirmer le mot de passe</label>
                    <input type="password" id="registerPasswordConfirm" required placeholder="••••••••">
                </div>
                <button type="submit" class="auth-submit">S'inscrire</button>
            </form>
        </div>
    </div>

    <!-- Modal des demandes d'accès -->
    <div id="accessRequestsModal" style="display: none; position: fixed; z-index: 10000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.7); overflow-y: auto;">
        <div style="background: white; margin: 50px auto; padding: 30px; border-radius: 15px; width: 90%; max-width: 900px; box-shadow: 0 10px 40px rgba(0,0,0,0.3);">
            <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px; border-bottom: 3px solid #FFB612; padding-bottom: 15px;">
                <h2 style="color: #FFB612; margin: 0;">👥 Demandes d'accès en attente</h2>
                <span onclick="fermerDemandesAcces()" style="font-size: 28px; font-weight: bold; color: #999; cursor: pointer; transition: color 0.3s;">&times;</span>
            </div>
            
            <div id="accessRequestsList" style="max-height: 500px; overflow-y: auto;">
                <!-- Les demandes seront ajoutées ici dynamiquement -->
            </div>
        </div>
    </div>

    <!-- Modal d'attente de validation -->
    <div id="pendingModal" style="display: none; position: fixed; z-index: 10000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.7);">
        <div style="background: white; margin: 15% auto; padding: 40px; border-radius: 15px; width: 90%; max-width: 500px; box-shadow: 0 10px 40px rgba(0,0,0,0.3); text-align: center;">
            <div style="font-size: 4em; margin-bottom: 20px;">⏳</div>
            <h2 style="color: #FFB612; margin-bottom: 15px;">Compte en attente de validation</h2>
            <p style="color: #666; line-height: 1.6; margin-bottom: 25px;">
                Votre compte a été créé avec succès !<br><br>
                Cependant, l'administrateur doit valider votre accès avant que vous puissiez utiliser l'application.<br><br>
                Vous recevrez une notification par email une fois votre compte approuvé.
            </p>
            <button onclick="handleLogout()" style="background: linear-gradient(135deg, #4DB8E8 0%, #0098DB 100%); color: white; border: none; padding: 12px 30px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer;">
                OK, j'ai compris
            </button>
        </div>
    </div>

    <!-- Contenu de l'application -->
    <div id="appContent">
        <div class="container">
            <header>
                <div class="header-content">
                    <div class="header-title">
                        <h1>🎓 Gestion Master IWS</h1>
                        <p class="subtitle">Interface de recensement des étudiants et de leurs parcours</p>
                    </div>
                    <div class="user-info">
                        <span class="user-email" id="userEmail"></span>
                        <button class="btn-access-requests" id="btnAccessRequests" onclick="ouvrirDemandesAcces()" style="display:none; background: linear-gradient(135deg, #FFB612 0%, #FF6319 100%); color: white; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 600; cursor: pointer; margin-right: 10px;">
                            👥 Demandes d'accès <span id="pendingCount" style="background: white; color: #FF6319; padding: 2px 8px; border-radius: 12px; font-size: 0.9em; margin-left: 5px;">0</span>
                        </button>
                        <button class="btn-logout" onclick="handleLogout()">Déconnexion</button>
                    </div>
                    <div class="export-import-buttons" id="exportImportButtons">
                        <button class="btn-export" onclick="exporterDonnees()">📥 Exporter en Excel</button>
                        <button class="btn-import" id="btnImport" onclick="document.getElementById('importFileInput').click()">📤 Importer Excel</button>
                        <input type="file" id="importFileInput" accept=".xlsx, .xls" onchange="importerDonnees(event)">
                    </div>
                </div>
            </header>

            <div class="main-content">
                <div class="sidebar">
                    <h2>➕ Ajouter un étudiant</h2>
                    <form id="studentForm">
                        <div class="form-group">
                            <label for="nom">Nom complet *</label>
                            <input type="text" id="nom" required placeholder="Ex: Dupont Jean">
                        </div>

                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" placeholder="Ex: jean.dupont@email.com">
                        </div>

                        <div class="form-group">
                            <label for="promotion">Promotion *</label>
                            <select id="promotion" required>
                                <option value="">-- Sélectionner --</option>
                                <option value="2022-2023">2022-2023</option>
                                <option value="2023-2024">2023-2024</option>
                                <option value="2024-2025">2024-2025</option>
                                <option value="2025-2026">2025-2026</option>
                                <option value="2026-2027">2026-2027</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label>Parcours *</label>
                            <div class="radio-group">
                                <div class="radio-option">
                                    <input type="radio" id="parcoursClassique" name="parcours" value="classique" checked onchange="verifierSections()">
                                    <label for="parcoursClassique">Master IWS Classique</label>
                                </div>
                                <div class="radio-option">
                                    <input type="radio" id="parcoursH2O" name="parcours" value="h2o" onchange="verifierSections()">
                                    <label for="parcoursH2O">Label H2O'Lyon 💧</label>
                                </div>
                            </div>
                        </div>

                        <div id="sectionConditionsH2O" class="section-depliable" style="display: none;">
                            <div class="section-header" onclick="toggleSection('conditionsH2O')">
                                <h3>💧 Conditions de validation H2O'Lyon</h3>
                                <span class="section-toggle">▼</span>
                            </div>
                            <div id="contentConditionsH2O" class="section-content">
                                <div class="form-group">
                                    <div class="checkbox-group">
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond1" name="conditions">
                                            <label for="cond1">Expérience internationale</label>
                                        </div>
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond2" name="conditions">
                                            <label for="cond2">Projet interdisciplinaire et/ou avec partenaires non académiques et/ou international (2 des 3 items)</label>
                                        </div>
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond3" name="conditions">
                                            <label for="cond3">Production en anglais</label>
                                        </div>
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond4" name="conditions">
                                            <label for="cond4">École d'été en lien avec l'eau</label>
                                        </div>
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond5" name="conditions">
                                            <label for="cond5">Cours interdisciplinaire dans un autre master</label>
                                        </div>
                                        <div class="checkbox-option">
                                            <input type="checkbox" id="cond6" name="conditions">
                                            <label for="cond6">Niveau B2 anglais certifié</label>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div id="sectionStages" class="section-depliable">
                            <div class="section-header" onclick="toggleSection('stages')">
                                <h3>📝 Productions de stage</h3>
                                <span class="section-toggle">▼</span>
                            </div>
                            <div id="contentStages" class="section-content">
                                <div class="form-group">
                                    <label for="stageIndividuel">Stage individuel</label>
                                    <textarea id="stageIndividuel" placeholder="Titre et description du stage individuel..."></textarea>
                                </div>
                                <div class="form-group">
                                    <label for="projetGrappe">Projet grappe</label>
                                    <textarea id="projetGrappe" placeholder="Titre et description du projet grappe..."></textarea>
                                </div>
                                <div class="form-group">
                                    <label for="liensProductions">Liens vers productions de stage</label>
                                    <textarea id="liensProductions" placeholder="Ajoutez les liens vers les productions (un par ligne)..."></textarea>
                                </div>
                            </div>
                        </div>

                        <div id="sectionSituation" class="section-depliable">
                            <div class="section-header" onclick="toggleSection('situation')">
                                <h3>💼 Situation actuelle</h3>
                                <span class="section-toggle">▼</span>
                            </div>
                            <div id="contentSituation" class="section-content">
                                <div class="form-group">
                                    <label for="situationActuelle">Que fait l'étudiant maintenant ?</label>
                                    <textarea id="situationActuelle" placeholder="Poste actuel, entreprise, domaine d'activité..."></textarea>
                                </div>
                            </div>
                        </div>

                        <button type="submit" id="submitBtn">Ajouter l'étudiant</button>
                        <button type="button" class="btn-secondary" id="cancelBtn" style="display:none;">Annuler</button>
                    </form>
                </div>

                <div class="content-area">
                    <h2>🏫 Tableau de bord IWS</h2>

                    <div class="tabs">
                        <button class="tab active" onclick="changerOnglet('dashboard')">
                            <span class="tab-icon">🏠</span>
                            <span class="tab-text">Accueil</span>
                        </button>
                        <button class="tab" onclick="changerOnglet('liste-etudiants')">
                            <span class="tab-icon">👥</span>
                            <span class="tab-text">Étudiants</span>
                        </button>
                        <button class="tab" onclick="changerOnglet('comparaison-parcours')">
                            <span class="tab-icon">📊</span>
                            <span class="tab-text">Stats</span>
                        </button>
                        <button class="tab" onclick="changerOnglet('competences-master')">
                            <span class="tab-icon">🎓</span>
                            <span class="tab-text">Compétences</span>
                        </button>
                        <button class="tab" onclick="changerOnglet('admin-panel')" id="admin-tab-btn" style="display: none;">
                            <span class="tab-icon">⚙️</span>
                            <span class="tab-text">Admin</span>
                        </button>
                    </div>

                    <div id="dashboard" class="tab-content active">
                        <div class="stats">
                            <div class="stat-card">
                                <div class="stat-number" id="totalEtudiants">0</div>
                                <div class="stat-label">Total étudiants</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number" id="totalClassique">0</div>
                                <div class="stat-label">Parcours classique</div>
                            </div>
                            <div class="stat-card h2o-stat">
                                <div class="stat-number" id="totalH2O">0</div>
                                <div class="stat-label">Label H2O'Lyon</div>
                            </div>
                        </div>

                        <div style="background: white; padding: 20px; border-radius: 10px; margin-bottom: 20px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
                            <h3 style="color: #0098DB; margin-bottom: 15px;">📊 Répartition actuelle des diplômés</h3>
                            <canvas id="situationsChart" style="max-height: 300px;"></canvas>
                        </div>
                    </div>

                    <div id="liste-etudiants" class="tab-content">
                        <!-- Formulaire mobile (sera rempli par JS) -->
                        <div id="formulaire-mobile" class="sidebar-mobile" style="display: none;"></div>
                        
                        <div class="filters">
                            <div class="filter-group">
                                <label>Rechercher :</label>
                                <input type="text" id="filterNom" placeholder="Nom de l'étudiant..." style="width: 250px; padding: 12px 18px; font-size: 17px; border: 3px solid #00C0B5; font-family: 'Roboto', sans-serif;">
                            </div>
                            <div class="filter-group">
                                <label>Promotion :</label>
                                <select id="filterPromotion">
                                    <option value="">Toutes</option>
                                    <option value="2022-2023">2022-2023</option>
                                    <option value="2023-2024">2023-2024</option>
                                    <option value="2024-2025">2024-2025</option>
                                    <option value="2025-2026">2025-2026</option>
                                    <option value="2026-2027">2026-2027</option>
                                </select>
                            </div>
                            <div class="filter-group">
                                <label>Parcours :</label>
                                <select id="filterParcours">
                                    <option value="">Tous</option>
                                    <option value="classique">Master IWS Classique</option>
                                    <option value="h2o">Label H2O'Lyon</option>
                                </select>
                            </div>
                            <button class="btn-filter" onclick="rechercherEtudiants()">🔍 Filtrer</button>
                            <button class="btn-reset" onclick="reinitialiserFiltres()">🔄 Réinitialiser</button>
                        </div>
                        
                        <div id="resultatsCount" class="resultats-count"></div>
                        <div id="studentsList">
                            <div class="empty-state">
                                <div class="empty-state-icon">📚</div>
                                <p>Aucun étudiant enregistré pour le moment.</p>
                                <p>Utilisez le formulaire à gauche pour ajouter des étudiants.</p>
                            </div>
                        </div>
                    </div>

                    <div id="comparaison-parcours" class="tab-content">
                        <div style="background: white; padding: 30px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); margin-bottom: 30px;">
                            <h3 style="color: #0098DB; margin-bottom: 20px; text-align: center;">📈 Évolution du nombre d'étudiants H2O'Lyon</h3>
                            <canvas id="evolutionChart" style="max-height: 400px;"></canvas>
                        </div>
                        
                        <div style="background: white; padding: 30px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
                            <h3 style="color: #0098DB; margin-bottom: 20px; text-align: center;">📊 Insertion des diplômés</h3>
                            <canvas id="comparaisonChart" style="max-height: 500px;"></canvas>
                        </div>
                    </div>

                    <div id="competences-master" class="tab-content">
                        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
                            <h2 style="color: #0098DB;">🎓 Référentiel de compétences du Master</h2>
                            <button id="btnEditCompetences" onclick="ouvrirEditionCompetences()" style="display: none; background: linear-gradient(135deg, #f093fb 0%, #764ba2 100%); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; transition: transform 0.2s;">
                                ✏️ Modifier les compétences
                            </button>
                        </div>
                        <div class="competences-grid" id="competences-container">
                            <!-- UE 1 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue1')">
                                    <div class="ue-title">
                                        <span class="ue-icon">🌊</span>
                                        <span>Challenges in Water Sciences</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue1">▼</span>
                                </div>
                                <div id="content-ue1" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours explore les défis contemporains liés à l'eau à travers trois modules thématiques. Le premier module aborde le cycle global de l'eau, les flux d'énergie et de masse associés, ainsi que le contrôle de la qualité et de la quantité des ressources hydriques. Les défis actuels et futurs sont placés dans le contexte des objectifs de développement durable des Nations Unies. Le deuxième module couvre les principales catégories et le fonctionnement des différents hydrosystèmes : rivières, lacs, zones humides, eaux souterraines et eaux virtuelles. Le troisième module permet de discuter des défis liés à l'eau au niveau des bassins versants et d'identifier les menaces sur les principales rivières.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Observer, décrire et caractériser l'état hydrologique, biogéochimique et écologique des bassins versants et des zones humides en général</li>
                                        <li>Analyser, résoudre et gérer les problèmes liés à la protection des hydrosystèmes</li>
                                        <li>Organiser la prévention et la prévision des risques hydrologiques</li>
                                        <li>Mobiliser des savoirs hautement spécialisés, dont certains sont à l'avant-garde du savoir dans un domaine de travail ou d'études, comme base d'une pensée originale</li>
                                        <li>Apporter des contributions novatrices dans le cadre d'échanges de haut niveau, et dans des contextes internationaux</li>
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 2 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue2')">
                                    <div class="ue-title">
                                        <span class="ue-icon">🔗</span>
                                        <span>Inter and Trans-disciplinarity</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue2">▼</span>
                                </div>
                                <div id="content-ue2" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours développe les notions d'interdisciplinarité et de transdisciplinarité en abordant l'évolution de l'organisation disciplinaire, les bases de l'épistémologie des sciences et l'approche systémique. Il explore des exemples d'application dans la recherche et la gestion des enjeux liés à l'eau, en mettant l'accent sur les positions épistémologiques à l'interface de plusieurs disciplines. Des études de cas du consortium H2O'Lyon sont étudiées pour comprendre les modalités de mise en œuvre, les avantages et les limites de ces approches. Les étudiants mèneront des entretiens avec des chercheurs, élaboreront une matrice des risques interdisciplinaires et exploreront le lien entre interdisciplinarité et pédagogies innovantes à travers un serious game.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Développer une conscience critique des savoirs dans un domaine et/ou à l'interface de plusieurs domaines</li>
                                        <li>Résoudre des problèmes pour développer de nouveaux savoirs et de nouvelles procédures et intégrer les savoirs de différents domaines</li>
                                        <li>Apporter des contributions novatrices dans le cadre d'échanges de haut niveau, et dans des contextes internationaux</li>
                                        <li>Conduire une analyse réflexive et distanciée prenant en compte les enjeux, les problématiques et la complexité d'une demande ou d'une situation afin de proposer des solutions adaptées et/ou innovantes</li>
                                        <li>Concevoir, mener et analyser des entretiens semi-directifs permettant d'analyser les perceptions et discours</li>
                                        <li>Utiliser des outils d'analyse avancée pour la gestion des risques et la prise de décision dans des contextes pluridisciplinaires</li>
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                        <li>Prendre des responsabilités pour contribuer aux savoirs et aux pratiques professionnelles et/ou pour réviser la performance stratégique d'une équipe</li>
                                        <li>Conduire un projet pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                        <li>Respecter les principes d'éthique, de déontologie et de responsabilité environnementale</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 3 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue3')">
                                    <div class="ue-title">
                                        <span class="ue-icon">📚</span>
                                        <span>Disciplinary Basis</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue3">▼</span>
                                </div>
                                <div id="content-ue3" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours est organisé en quatre modules disciplinaires complémentaires. Le premier module aborde la gestion durable et adaptative des ressources communes en mobilisant sociologie, droit et économie. Le deuxième module couvre les principes fondamentaux d'hydrologie, d'hydraulique et de géomorphologie fluviale, ainsi que les interactions entre l'eau, les rivières et les villes. Le troisième module traite du fonctionnement des écosystèmes, du couplage terrestre-aquatique et de la biodiversité mondiale. Le quatrième module est consacré à la chimie de l'eau, l'écotoxicologie et la microbiologie, incluant les méthodes d'échantillonnage, les indicateurs et l'évaluation de la qualité.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Comprendre les principes fondamentaux et outils dévelopés par différentes disciplines pour répondre aux enjeux de la gestion de l'eau et des écosystèmes associés</li>
                                        <li>Intégrer les savoirs de différentes disciplines pour développer de nouvelles connaissances et répondre à des problématiques</li>
                                        <li>Développer une conscience critique des savoirs dans un domaine et/ou à l'interface de plusieurs domaines</li>
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                        <li>Conduire un projet (conception, pilotage, coordination d'équipe, mise en œuvre et gestion, évaluation, diffusion) pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 4 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue4')">
                                    <div class="ue-title">
                                        <span class="ue-icon">🌐</span>
                                        <span>Cross-disciplinary Issues</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue4">▼</span>
                                </div>
                                <div id="content-ue4" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours confronte les étudiants aux questions interdisciplinaires à travers des interactions avec différents acteurs : chercheurs, opérationnels et grand public. Les interactions sont basées sur l'organisation d'événements variés qui changent chaque année : expositions, ateliers scientifiques, séminaires, visites d'aménagements, prototypes, webinaires ou collaborations internationales. Les partenaires associés incluent le Musée de Confluence, Pop'Sciences, Fablab et chercheurs internationaux. Le cours repose sur un socle de connaissances lié à l'évolution de la gestion des eaux pluviales urbaines, renforcé par une revue de littérature en groupe sur un sujet différent chaque année.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Conduire une analyse réflexive et distanciée prenant en compte les enjeux, les problématiques et la complexité d'une demande ou d'une situation afin de proposer des solutions adaptées et/ou innovantes en respect des évolutions de la réglementation</li>
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Concevoir et piloter des projets de médiation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                        <li>Gérer des contextes professionnels ou d'études complexes, imprévisibles et qui nécessitent des approches stratégiques nouvelles</li>
                                        <li>Conduire un projet (conception, pilotage, coordination d'équipe, mise en œuvre et gestion, évaluation, diffusion) pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                        <li>Respecter les principes d'éthique, de déontologie et de responsabilité environnementale</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 5 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue5')">
                                    <div class="ue-title">
                                        <span class="ue-icon">🎯</span>
                                        <span>Mentored Project</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue5">▼</span>
                                </div>
                                <div id="content-ue5" class="ue-content">
                                    <p class="ue-description">
                                        Dans ce cours, les étudiants travaillent en petits groupes interdisciplinaires (clusters) pour définir leur problématique de recherche. Cette problématique constitue la base d'un projet de recherche plus large, construit en collaboration avec les partenaires académiques et externes. Les étudiants schématisent la problématique pour la faire correspondre aux attentes des partenaires opérationnels et des encadrants académiques. Ils programment ensuite les activités du second semestre : bibliographie, collecte de données terrain, analyse, synthèse interdisciplinaire et réunions d'avancement. Enfin, ils produisent une synthèse bibliographique structurée.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                        <li>Gérer des contextes professionnels ou d'études complexes, imprévisibles et qui nécessitent des approches stratégiques nouvelles</li>
                                        <li>Conduire un projet (conception, pilotage, coordination d'équipe, mise en œuvre et gestion, évaluation, diffusion) pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                        <li>Respecter les principes d'éthique, de déontologie et de responsabilité environnementale</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 6 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue6')">
                                    <div class="ue-title">
                                        <span class="ue-icon">🔬</span>
                                        <span>Technics and Methods</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue6">▼</span>
                                </div>
                                <div id="content-ue6" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours permet aux étudiants d'acquérir un socle commun de connaissances techniques correspondant à plusieurs champs thématiques : sciences sociales, hydrologie, géomorphologie, statistiques et systèmes d'information géographique. Les étudiants apprennent à définir les outils propres à chaque discipline et à mettre en œuvre une démarche de recherche associée. Le cours développe également une approche inter et transdisciplinaire pour traiter des problèmes réels liés aux questions sociétales. Les compétences acquises incluent la maîtrise des méthodes d'échantillonnage, d'analyse de données, de modélisation et d'utilisation des outils numériques avancés.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Mettre en place une stratégie d'échantillonnage adaptée</li>
                                        <li>Élaborer une démarche pour la mesure de l'état écologique (qualité) des eaux et des milieux</li>
                                        <li>Utiliser les outils statistiques descriptifs et prendre en compte les incertitudes et biais dans l'analyse des données</li>
                                        <li>Interpréter et analyser des données géologiques, biogéochimiques, écologiques et environnementales</li>
                                        <li>Utiliser les outils des Systèmes d'Information Géographique et de télédétection</li>
                                        <li>Mobiliser des données disponibles sur des bases en ligne (sciences ouvertes)</li>
                                        <li>Se servir de façon autonome des outils numériques avancés pour un ou plusieurs métiers ou secteurs de recherche du domaine</li>
                                        <li>Résoudre des problèmes pour développer de nouveaux savoirs et de nouvelles procédures et intégrer les savoirs de différents domaines</li>
                                        <li>Conduire un projet (conception, pilotage, coordination d'équipe, mise en œuvre et gestion, évaluation, diffusion) pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- UE 7 -->
                            <div class="ue-card">
                                <div class="ue-header" onclick="toggleUE('ue7')">
                                    <div class="ue-title">
                                        <span class="ue-icon">💬</span>
                                        <span>Communication and Application</span>
                                    </div>
                                    <span class="ue-toggle" id="toggle-ue7">▼</span>
                                </div>
                                <div id="content-ue7" class="ue-content">
                                    <p class="ue-description">
                                        Ce cours développe les compétences en communication scientifique et professionnelle adaptées à différents publics. Les étudiants apprennent pourquoi et comment communiquer efficacement pour la diffusion des connaissances scientifiques, la collaboration et la co-construction avec divers acteurs. Le cours présente les moyens de communication les plus appropriés selon les contextes et les publics : dépliants, webinaires, séminaires, tables rondes et présentations scientifiques. Les étudiants développent leur capacité à adapter leur discours en fonction du type d'audience pour transmettre efficacement des messages, idées et connaissances. Ce cours est également coordonné avec les autres unités d'enseignement.
                                    </p>
                                    <div class="competences-titre">Compétences acquises :</div>
                                    <ul class="competences-liste">
                                        <li>Identifier, sélectionner et analyser avec esprit critique diverses ressources spécialisées pour documenter un sujet et synthétiser ces données en vue de leur exploitation</li>
                                        <li>Concevoir et piloter des projets de médiation</li>
                                        <li>Communiquer à des fins de formation ou de transfert de connaissances, par oral et par écrit, en français et dans au moins une langue étrangère</li>
                                        <li>Savoir adapter son discours en fonction du type de public pour faire passer des messages, idées et connaissances</li>
                                        <li>Développer une conscience critique des savoirs dans un domaine et/ou à l'interface de plusieurs domaines</li>
                                        <li>Gérer des contextes professionnels ou d'études complexes, imprévisibles et qui nécessitent des approches stratégiques nouvelles</li>
                                        <li>Analyser, résoudre et gérer les problèmes liés à la protection des hydrosystèmes</li>
                                        <li>Conduire un projet (conception, pilotage, coordination d'équipe, mise en œuvre et gestion, évaluation, diffusion) pouvant mobiliser des compétences pluridisciplinaires dans un cadre collaboratif</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- ONGLET ADMIN -->
                    <div id="admin-panel" class="tab-content">
                        <h3 style="color: #FFB612; margin-bottom: 20px;">⚙️ Panneau d'administration</h3>
                        
                        <!-- Section Import/Export -->
                        <div style="background: white; padding: 25px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); margin-bottom: 20px;">
                            <h4 style="color: #0098DB; margin-bottom: 15px; border-bottom: 2px solid #0098DB; padding-bottom: 10px;">
                                📊 Gestion des données
                            </h4>
                            <div style="display: flex; gap: 15px; flex-wrap: wrap;">
                                <button onclick="exporterExcel()" style="background: linear-gradient(135deg, #5FCF80 0%, #27ae60 100%); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; transition: transform 0.2s; display: flex; align-items: center; gap: 8px;">
                                    <span>📥</span> Exporter en Excel
                                </button>
                                <button onclick="document.getElementById('fileInput').click()" style="background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; transition: transform 0.2s; display: flex; align-items: center; gap: 8px;">
                                    <span>📤</span> Importer Excel
                                </button>
                                <input type="file" id="fileInput" accept=".xlsx, .xls" style="display: none;" onchange="importerExcel(event)">
                                <span id="fileStatus" style="align-self: center; color: #666; font-size: 14px;">Aucun fichier n'a été sélectionné</span>
                            </div>
                        </div>
                        
                        <!-- Section Demandes d'accès -->
                        <div style="background: white; padding: 30px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); margin-bottom: 20px;">
                            <h4 style="color: #0098DB; margin-bottom: 20px; border-bottom: 2px solid #0098DB; padding-bottom: 10px;">
                                👥 Demandes d'accès en attente
                            </h4>
                            
                            <div id="admin-requests-list">
                                <div style="text-align: center; padding: 50px; color: #999;">
                                    <div style="font-size: 3em; margin-bottom: 20px;">⏳</div>
                                    <p style="font-size: 1.1em;">Chargement des demandes...</p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
            
            <div class="footer-maj" id="derniereMaj">
                MAJ : --/--/---- - --h--
            </div>
        </div>
    </div>

    <!-- Modal d'édition des compétences -->
    <div id="modalEditCompetences" style="display: none; position: fixed; z-index: 10000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.7); overflow-y: auto;">
        <div style="background: white; margin: 50px auto; padding: 30px; border-radius: 15px; max-width: 900px; box-shadow: 0 10px 40px rgba(0,0,0,0.3);">
            <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 30px; border-bottom: 2px solid #0098DB; padding-bottom: 15px;">
                <h2 style="color: #0098DB; margin: 0;">✏️ Modifier les compétences</h2>
                <button onclick="fermerEditionCompetences()" style="background: #e74c3c; color: white; border: none; padding: 10px 20px; border-radius: 8px; cursor: pointer; font-weight: 600;">✖ Fermer</button>
            </div>
            
            <div id="editCompetencesContent" style="max-height: 70vh; overflow-y: auto;">
                <!-- Le contenu sera chargé dynamiquement -->
            </div>
            
            <div style="margin-top: 30px; text-align: right; border-top: 2px solid #eee; padding-top: 20px;">
                <button onclick="sauvegarderCompetences()" style="background: linear-gradient(135deg, #5FCF80 0%, #27ae60 100%); color: white; border: none; padding: 15px 30px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; margin-right: 10px;">
                    💾 Sauvegarder les modifications
                </button>
                <button onclick="fermerEditionCompetences()" style="background: #95a5a6; color: white; border: none; padding: 15px 30px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer;">
                    Annuler
                </button>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/chartjs-plugin-datalabels/2.2.0/chartjs-plugin-datalabels.min.js"></script>
    
    <script>
        // ============================================
        // CONFIGURATION FIREBASE
        // ============================================
        // IMPORTANT : Remplacez ces valeurs par celles de votre projet Firebase
        const firebaseConfig = {
            apiKey: "AIzaSyB27z5Q7vxlefaiflloguZmiSkN_WtF8os",
            authDomain: "interface-iws.firebaseapp.com",
            projectId: "interface-iws",
            storageBucket: "interface-iws.firebasestorage.app",
            messagingSenderId: "796278870852",
            appId: "1:796278870852:web:03bf3be4fd30cdbcb67d11"
        };

        // Initialiser Firebase
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();
        const db = firebase.firestore();

        // ============================================
        // VARIABLES GLOBALES
        // ============================================
        let etudiants = [];
        let editingId = null;
        let situationsChart = null;
        let comparaisonChart = null;
        let evolutionChart = null;
        let currentUser = null;
        let isAdmin = false;
        const ADMIN_EMAIL = 'lilibailly1803@gmail.com';

        // ============================================
        // GESTION DE L'AUTHENTIFICATION
        // ============================================
        auth.onAuthStateChanged(async user => {
            if (user) {
                currentUser = user;
                isAdmin = (user.email === ADMIN_EMAIL);
                
                // Vérifier le statut de l'utilisateur
                const userDoc = await db.collection('users').doc(user.uid).get();
                
                if (!userDoc.exists) {
                    // Cas où l'utilisateur n'a pas de document (ancien compte)
                    // Créer le document avec statut approved
                    await db.collection('users').doc(user.uid).set({
                        email: user.email,
                        status: isAdmin ? 'approved' : 'approved',
                        createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                        approvedAt: firebase.firestore.FieldValue.serverTimestamp()
                    });
                }
                
                const userData = userDoc.exists ? userDoc.data() : { status: 'approved' };
                
                // Si le statut est "pending", afficher la modal d'attente
                if (userData.status === 'pending') {
                    document.getElementById('authModal').style.display = 'none';
                    document.getElementById('appContent').style.display = 'none';
                    document.getElementById('pendingModal').style.display = 'block';
                    return;
                }
                
                // Si le statut est "rejected", déconnecter
                if (userData.status === 'rejected') {
                    alert('Votre demande d\'accès a été refusée par l\'administrateur.');
                    await auth.signOut();
                    return;
                }
                
                // Sinon, l'utilisateur est approuvé
                document.getElementById('authModal').style.display = 'none';
                document.getElementById('appContent').style.display = 'block';
                document.getElementById('pendingModal').style.display = 'none';
                document.getElementById('userEmail').textContent = user.email;
                
                // Afficher le badge admin si c'est un admin
                if (isAdmin) {
                    document.getElementById('userEmail').innerHTML = user.email + ' <span style="background: #FFB612; color: #333; padding: 2px 8px; border-radius: 12px; font-size: 0.8em; margin-left: 8px; font-weight: 600;">👑 ADMIN</span>';
                    document.getElementById('btnAccessRequests').style.display = 'inline-block';
                    document.getElementById('admin-tab-btn').style.display = 'inline-block';
                    document.getElementById('btnEditCompetences').style.display = 'inline-block';
                    chargerDemandesEnAttente();
                }
                
                // Masquer le formulaire d'ajout si pas admin
                if (!isAdmin) {
                    document.querySelector('.sidebar').style.display = 'none';
                    document.querySelector('.main-content').style.gridTemplateColumns = '1fr';
                    document.getElementById('btnImport').style.display = 'none';
                    document.getElementById('admin-tab-btn').style.display = 'none';
                }
                
                chargerEtudiants();
                chargerCompetences();
            } else {
                currentUser = null;
                isAdmin = false;
                document.getElementById('authModal').style.display = 'flex';
                document.getElementById('appContent').style.display = 'none';
                document.getElementById('pendingModal').style.display = 'none';
                if (document.getElementById('admin-tab-btn')) {
                    document.getElementById('admin-tab-btn').style.display = 'none';
                }
            }
        });

        // Gestion du header qui se cache au scroll sur mobile
        let lastScrollTop = 0;
        let scrollTimeout;
        const header = document.querySelector('header');
        
        if (window.innerWidth <= 768) {
            window.addEventListener('scroll', function() {
                clearTimeout(scrollTimeout);
                
                scrollTimeout = setTimeout(() => {
                    const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
                    
                    if (scrollTop > lastScrollTop && scrollTop > 100) {
                        header.classList.add('header-hidden');
                    } else if (scrollTop < lastScrollTop) {
                        header.classList.remove('header-hidden');
                    }
                    
                    lastScrollTop = scrollTop <= 0 ? 0 : scrollTop;
                }, 50);
            }, false);
        }

        // Sur mobile: dupliquer le formulaire dans l'onglet étudiants
        if (window.innerWidth <= 768) {
            window.addEventListener('DOMContentLoaded', function() {
                const sidebar = document.querySelector('.sidebar');
                const formulaireMobile = document.getElementById('formulaire-mobile');
                
                if (sidebar && formulaireMobile) {
                    // Cloner le contenu de la sidebar
                    formulaireMobile.innerHTML = sidebar.innerHTML;
                    formulaireMobile.style.display = 'block';
                }
            });
        }

        function switchAuthTab(tab) {
            const tabs = document.querySelectorAll('.auth-tab');
            const forms = document.querySelectorAll('.auth-form');
            
            tabs.forEach(t => t.classList.remove('active'));
            forms.forEach(f => f.classList.remove('active'));
            
            if (tab === 'login') {
                tabs[0].classList.add('active');
                document.getElementById('loginForm').classList.add('active');
            } else {
                tabs[1].classList.add('active');
                document.getElementById('registerForm').classList.add('active');
            }
            
            document.getElementById('authError').classList.remove('show');
        }

        function showAuthError(message, type = 'error') {
            const errorDiv = document.getElementById('authError');
            errorDiv.textContent = message;
            errorDiv.classList.add('show');
            
            if (type === 'success') {
                errorDiv.style.background = 'linear-gradient(135deg, #38ef7d 0%, #11998e 100%)';
                errorDiv.style.color = 'white';
            } else {
                errorDiv.style.background = 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)';
                errorDiv.style.color = 'white';
            }
        }

        async function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            try {
                await auth.signInWithEmailAndPassword(email, password);
            } catch (error) {
                let message = 'Erreur de connexion';
                if (error.code === 'auth/user-not-found') {
                    message = 'Aucun compte trouvé avec cet email';
                } else if (error.code === 'auth/wrong-password') {
                    message = 'Mot de passe incorrect';
                } else if (error.code === 'auth/invalid-email') {
                    message = 'Email invalide';
                }
                showAuthError(message);
            }
        }

        async function handleRegister(e) {
            e.preventDefault();
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const passwordConfirm = document.getElementById('registerPasswordConfirm').value;
            
            if (password !== passwordConfirm) {
                showAuthError('Les mots de passe ne correspondent pas');
                return;
            }
            
            try {
                const userCredential = await auth.createUserWithEmailAndPassword(email, password);
                const user = userCredential.user;
                
                // Créer un document utilisateur avec statut "pending" (sauf pour l'admin)
                const isAdminEmail = (email === ADMIN_EMAIL);
                await db.collection('users').doc(user.uid).set({
                    email: email,
                    status: isAdminEmail ? 'approved' : 'pending',
                    createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                    approvedAt: isAdminEmail ? firebase.firestore.FieldValue.serverTimestamp() : null
                });
                
                // Si ce n'est pas l'admin, afficher message puis déconnecter
                if (!isAdminEmail) {
                    showAuthError('✅ Votre demande d\'accès a été envoyée avec succès ! L\'administrateur va examiner votre compte.', 'success');
                    await new Promise(resolve => setTimeout(resolve, 3000));
                    await auth.signOut();
                }
            } catch (error) {
                let message = 'Erreur lors de l\'inscription';
                if (error.code === 'auth/email-already-in-use') {
                    message = 'Un compte existe déjà avec cet email';
                } else if (error.code === 'auth/weak-password') {
                    message = 'Le mot de passe est trop faible';
                } else if (error.code === 'auth/invalid-email') {
                    message = 'Email invalide';
                }
                showAuthError(message);
            }
        }

        async function handleLogout() {
            if (confirm('Êtes-vous sûr de vouloir vous déconnecter ?')) {
                await auth.signOut();
            }
        }

        // ============================================
        // GESTION DES DONNÉES FIRESTORE
        // ============================================
        async function chargerEtudiants() {
            try {
                const snapshot = await db.collection('etudiants').orderBy('nom').get();
                etudiants = [];
                snapshot.forEach(doc => {
                    etudiants.push({
                        id: doc.id,
                        ...doc.data()
                    });
                });
                afficherEtudiants();
                mettreAJourStatistiques();
                creerGraphiqueSituations();
                creerGraphiqueComparaison();
                creerGraphiqueEvolution();
                mettreAJourDateMaj();
            } catch (error) {
                console.error('Erreur lors du chargement:', error);
                alert('Erreur lors du chargement des données');
            }
        }

        async function ajouterEtudiant(etudiant) {
            try {
                const docRef = await db.collection('etudiants').add(etudiant);
                return docRef.id;
            } catch (error) {
                console.error('Erreur lors de l\'ajout:', error);
                throw error;
            }
        }

        async function modifierEtudiantDB(id, etudiant) {
            try {
                await db.collection('etudiants').doc(id).update(etudiant);
            } catch (error) {
                console.error('Erreur lors de la modification:', error);
                throw error;
            }
        }

        async function supprimerEtudiantDB(id) {
            try {
                await db.collection('etudiants').doc(id).delete();
            } catch (error) {
                console.error('Erreur lors de la suppression:', error);
                throw error;
            }
        }

        // ============================================
        // FORMULAIRE D'AJOUT/MODIFICATION
        // ============================================
        document.getElementById('studentForm').addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const nomSaisi = document.getElementById('nom').value.trim();
            
            if (!editingId && etudiants.some(et => et.nom.toLowerCase().trim() === nomSaisi.toLowerCase())) {
                alert(`⚠️ Attention : Un étudiant nommé "${nomSaisi}" existe déjà !`);
                return;
            }
            
            const conditions = [];
            if (document.querySelector('input[name="parcours"]:checked').value === 'h2o') {
                document.querySelectorAll('#contentConditionsH2O input[type="checkbox"]:checked').forEach(cb => {
                    conditions.push(cb.nextElementSibling.textContent);
                });
            }
            
            const etudiant = {
                nom: nomSaisi,
                email: document.getElementById('email').value || 'Non renseigné',
                promotion: document.getElementById('promotion').value,
                parcours: document.querySelector('input[name="parcours"]:checked').value,
                conditionsH2O: conditions,
                stageIndividuel: document.getElementById('stageIndividuel').value || 'Non renseigné',
                projetGrappe: document.getElementById('projetGrappe').value || 'Non renseigné',
                liensProductions: document.getElementById('liensProductions').value || 'Aucun lien fourni',
                situationActuelle: document.getElementById('situationActuelle').value || 'Non renseignée',
                createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                createdBy: currentUser.uid
            };

            try {
                if (editingId) {
                    await modifierEtudiantDB(editingId, etudiant);
                    editingId = null;
                    document.getElementById('submitBtn').textContent = 'Ajouter l\'étudiant';
                    document.getElementById('cancelBtn').style.display = 'none';
                } else {
                    await ajouterEtudiant(etudiant);
                }

                document.getElementById('studentForm').reset();
                document.getElementById('parcoursClassique').checked = true;
                await chargerEtudiants();
                verifierSections();
            } catch (error) {
                alert('Erreur lors de l\'enregistrement: ' + error.message);
            }
        });

        document.getElementById('cancelBtn').addEventListener('click', () => {
            editingId = null;
            document.getElementById('studentForm').reset();
            document.getElementById('submitBtn').textContent = 'Ajouter l\'étudiant';
            document.getElementById('cancelBtn').style.display = 'none';
            verifierSections();
        });

        // ============================================
        // FONCTIONS DE L'INTERFACE (inchangées)
        // ============================================
        function mettreAJourDateMaj() {
            const now = new Date();
            const jour = String(now.getDate()).padStart(2, '0');
            const mois = String(now.getMonth() + 1).padStart(2, '0');
            const annee = now.getFullYear();
            const heures = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            
            const footerElement = document.getElementById('derniereMaj');
            footerElement.textContent = `MAJ : ${jour}/${mois}/${annee} - ${heures}h${minutes}`;
        }

        function toggleSection(sectionName) {
            const content = document.getElementById('content' + sectionName.charAt(0).toUpperCase() + sectionName.slice(1));
            const toggle = content.previousElementSibling.querySelector('.section-toggle');
            
            if (content.classList.contains('active')) {
                content.classList.remove('active');
                toggle.textContent = '▼';
            } else {
                content.classList.add('active');
                toggle.textContent = '▲';
            }
        }

        function verifierSections() {
            const parcours = document.querySelector('input[name="parcours"]:checked').value;
            const sectionH2O = document.getElementById('sectionConditionsH2O');
            const sectionStages = document.getElementById('sectionStages');
            
            if (parcours === 'h2o') {
                sectionH2O.style.display = 'block';
                sectionStages.style.display = 'none';
            } else {
                sectionH2O.style.display = 'none';
                sectionStages.style.display = 'block';
            }
        }

        document.getElementById('filterNom').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                e.preventDefault();
                rechercherEtudiants();
            }
        });

        function afficherEtudiants() {
            const filterPromo = document.getElementById('filterPromotion').value;
            const filterParcours = document.getElementById('filterParcours').value;
            const filterNom = document.getElementById('filterNom').value.toLowerCase().trim();
            
            let etudiantsFiltres = etudiants.filter(e => 
                (!filterPromo || e.promotion === filterPromo) && 
                (!filterParcours || e.parcours === filterParcours) &&
                (!filterNom || e.nom.toLowerCase().includes(filterNom))
            );

            const container = document.getElementById('studentsList');
            const countElement = document.getElementById('resultatsCount');
            
            const nbResultats = etudiantsFiltres.length;
            if (filterPromo || filterParcours || filterNom) {
                countElement.textContent = `👥 ${nbResultats} étudiant${nbResultats > 1 ? 's' : ''} trouvé${nbResultats > 1 ? 's' : ''}`;
                countElement.style.display = 'block';
            } else {
                countElement.style.display = 'none';
            }

            if (etudiantsFiltres.length === 0) {
                container.innerHTML = '<div class="empty-state"><div class="empty-state-icon">❌</div><p>Aucun étudiant trouvé.</p></div>';
                return;
            }

            const etudiantsClassique = etudiantsFiltres.filter(e => e.parcours === 'classique').sort((a, b) => a.nom.localeCompare(b.nom));
            const etudiantsH2O = etudiantsFiltres.filter(e => e.parcours === 'h2o').sort((a, b) => a.nom.localeCompare(b.nom));

            let html = '';

            if (etudiantsClassique.length > 0) {
                html += `
                    <div class="section-depliable" style="margin-bottom: 20px;">
                        <div class="section-header" onclick="toggleSectionListe('classique')">
                            <h3>🎓 Master IWS Classique (${etudiantsClassique.length})</h3>
                            <span class="section-toggle" id="toggle-classique">▼</span>
                        </div>
                        <div id="content-classique" class="section-content">
                            ${genererListeEtudiants(etudiantsClassique)}
                        </div>
                    </div>
                `;
            }

            if (etudiantsH2O.length > 0) {
                html += `
                    <div class="section-depliable" style="margin-bottom: 20px;">
                        <div class="section-header" onclick="toggleSectionListe('h2o')">
                            <h3>💧 Label H2O'Lyon (${etudiantsH2O.length})</h3>
                            <span class="section-toggle" id="toggle-h2o">▼</span>
                        </div>
                        <div id="content-h2o" class="section-content">
                            ${genererListeEtudiants(etudiantsH2O)}
                        </div>
                    </div>
                `;
            }

            container.innerHTML = html;
        }

        function genererListeEtudiants(etudiants) {
            return etudiants.map(etudiant => {
                const isH2OIncomplete = etudiant.parcours === 'h2o' && (!etudiant.conditionsH2O || etudiant.conditionsH2O.length < 6);
                let cardClass = etudiant.parcours === 'h2o' ? 'student-card h2o' : 'student-card';
                if (isH2OIncomplete) cardClass += ' incomplete';
                
                const nbConditions = etudiant.conditionsH2O ? etudiant.conditionsH2O.length : 0;
                const warningBadge = isH2OIncomplete ? `<span class="badge-warning">⚠️ ${nbConditions}/6</span>` : '';
                
                let conditionsHTML = '';
                if (etudiant.parcours === 'h2o') {
                    const conditionsValidees = etudiant.conditionsH2O && etudiant.conditionsH2O.length > 0 
                        ? etudiant.conditionsH2O.map(c => `<div style="padding: 4px 0;">• ${c}</div>`).join('')
                        : '<div style="padding: 4px 0; color: #e74c3c;">Aucune condition validée</div>';
                    
                    conditionsHTML = `<div class="info-item" style="grid-column: 1 / -1;">
                        <div class="info-label">✅ Conditions validées (${nbConditions}/6)</div>
                        <div class="info-value" style="margin-top: 8px;">${conditionsValidees}</div>
                    </div>`;
                }
                
                let stagesHTML = '';
                if (etudiant.parcours === 'classique') {
                    let liensHTML = etudiant.liensProductions;
                    if (liensHTML !== 'Aucun lien fourni') {
                        liensHTML = liensHTML.split('\n').filter(l => l.trim()).map(lien => {
                            const url = lien.trim();
                            return (url.startsWith('http://') || url.startsWith('https://'))
                                ? `<a href="${url}" target="_blank" style="color: #0098DB; text-decoration: underline;">${url}</a>`
                                : url;
                        }).join('<br>');
                    }
                    
                    stagesHTML = `
                        <div class="info-item"><div class="info-label">Stage individuel</div><div class="info-value">${etudiant.stageIndividuel}</div></div>
                        <div class="info-item"><div class="info-label">Projet grappe</div><div class="info-value">${etudiant.projetGrappe}</div></div>
                        <div class="info-item" style="grid-column: 1 / -1;"><div class="info-label">🔗 Liens productions</div><div class="info-value">${liensHTML}</div></div>`;
                }
                
                return `<div class="${cardClass}" id="card-${etudiant.id}" onclick="toggleCard('${etudiant.id}')">
                    <div class="student-card-compact">
                        <div class="student-header" style="margin: 0;">
                            <div class="student-name">${etudiant.nom}${warningBadge}</div>
                        </div>
                        <div class="badges">
                            <div class="student-parcours ${etudiant.parcours === 'h2o' ? 'parcours-h2o' : 'parcours-classique'}">
                                ${etudiant.parcours === 'h2o' ? '💧 Label' : '🎓 IWS'}
                            </div>
                            <div class="student-promo">Promo ${etudiant.promotion}</div>
                        </div>
                    </div>
                    <div class="student-card-details">
                        <div class="student-info">
                            <div class="info-item"><div class="info-label">📧 Email</div><div class="info-value">${etudiant.email}</div></div>
                            ${conditionsHTML}${stagesHTML}
                        </div>
                        <div class="info-item" style="margin-top: 10px;">
                            <div class="info-label">💼 Situation actuelle</div>
                            <div class="info-value">${etudiant.situationActuelle}</div>
                        </div>
                        ${isAdmin ? `<div class="actions">
                            <button class="btn-small btn-edit" onclick="event.stopPropagation(); modifierEtudiant('${etudiant.id}')">✏️ Modifier</button>
                            <button class="btn-small btn-delete" onclick="event.stopPropagation(); supprimerEtudiant('${etudiant.id}')">🗑️ Supprimer</button>
                        </div>` : ''}
                    </div>
                </div>`;
            }).join('');
        }
        
        function toggleSectionListe(sectionName) {
            const content = document.getElementById('content-' + sectionName);
            const toggle = document.getElementById('toggle-' + sectionName);
            
            if (content.classList.contains('active')) {
                content.classList.remove('active');
                toggle.textContent = '▼';
            } else {
                content.classList.add('active');
                toggle.textContent = '▲';
            }
        }

        function rechercherEtudiants() { afficherEtudiants(); }
        
        function reinitialiserFiltres() {
            document.getElementById('filterNom').value = '';
            document.getElementById('filterPromotion').value = '';
            document.getElementById('filterParcours').value = '';
            afficherEtudiants();
        }
        
        function changerOnglet(ongletId) {
            document.querySelectorAll('.tab').forEach(tab => tab.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(content => content.classList.remove('active'));
            
            event.target.classList.add('active');
            document.getElementById(ongletId).classList.add('active');
            
            // Charger les demandes d'accès quand on ouvre l'onglet admin
            if (ongletId === 'admin-panel' && isAdmin) {
                chargerDemandesOngletAdmin();
            }
        }
        
        function toggleCard(id) { document.getElementById(`card-${id}`).classList.toggle('expanded'); }

        function toggleUE(ueId) {
            const content = document.getElementById(`content-${ueId}`);
            const toggle = document.getElementById(`toggle-${ueId}`);
            
            if (content.classList.contains('active')) {
                content.classList.remove('active');
                toggle.textContent = '▼';
            } else {
                content.classList.add('active');
                toggle.textContent = '▲';
            }
        }

        function modifierEtudiant(id) {
            const etudiant = etudiants.find(e => e.id === id);
            if (!etudiant) return;

            editingId = id;
            document.getElementById('nom').value = etudiant.nom;
            document.getElementById('email').value = etudiant.email !== 'Non renseigné' ? etudiant.email : '';
            document.getElementById('promotion').value = etudiant.promotion;
            
            if (etudiant.parcours === 'h2o') {
                document.getElementById('parcoursH2O').checked = true;
                document.querySelectorAll('#contentConditionsH2O input[type="checkbox"]').forEach(cb => cb.checked = false);
                if (etudiant.conditionsH2O) {
                    etudiant.conditionsH2O.forEach(condition => {
                        document.querySelectorAll('#contentConditionsH2O input[type="checkbox"]').forEach(cb => {
                            if (cb.nextElementSibling.textContent === condition) cb.checked = true;
                        });
                    });
                }
                document.getElementById('contentConditionsH2O').classList.add('active');
            } else {
                document.getElementById('parcoursClassique').checked = true;
                document.getElementById('stageIndividuel').value = etudiant.stageIndividuel !== 'Non renseigné' ? etudiant.stageIndividuel : '';
                document.getElementById('projetGrappe').value = etudiant.projetGrappe !== 'Non renseigné' ? etudiant.projetGrappe : '';
                document.getElementById('liensProductions').value = etudiant.liensProductions !== 'Aucun lien fourni' ? etudiant.liensProductions : '';
                document.getElementById('contentStages').classList.add('active');
            }
                        
            document.getElementById('situationActuelle').value = etudiant.situationActuelle !== 'Non renseignée' ? etudiant.situationActuelle : '';
            document.getElementById('contentSituation').classList.add('active');

            document.getElementById('submitBtn').textContent = 'Mettre à jour';
            document.getElementById('cancelBtn').style.display = 'inline-block';
            window.scrollTo({ top: 0, behavior: 'smooth' });
            verifierSections();
        }

        async function supprimerEtudiant(id) {
            if (confirm('Êtes-vous sûr de vouloir supprimer cet étudiant ?')) {
                try {
                    await supprimerEtudiantDB(id);
                    await chargerEtudiants();
                } catch (error) {
                    alert('Erreur lors de la suppression: ' + error.message);
                }
            }
        }

        function mettreAJourStatistiques() {
            document.getElementById('totalEtudiants').textContent = etudiants.length;
            document.getElementById('totalClassique').textContent = etudiants.filter(e => e.parcours === 'classique').length;
            document.getElementById('totalH2O').textContent = etudiants.filter(e => e.parcours === 'h2o').length;
        }

        // Les fonctions de graphiques restent identiques à votre version originale
        function creerGraphiqueSituations() {
            const now = new Date();
            const annee = now.getFullYear();
            const anneeEnCours = (now.getMonth() + 1) >= 9 ? `${annee}-${annee + 1}` : `${annee - 1}-${annee}`;
            
            const etudiantsFiltre = etudiants.filter(e => e.promotion !== anneeEnCours);
            
            if (etudiantsFiltre.length === 0) {
                if (situationsChart) {
                    situationsChart.destroy();
                    situationsChart = null;
                }
                return;
            }

            const situations = {};
            etudiantsFiltre.forEach(e => {
                const sit = e.situationActuelle && e.situationActuelle !== 'Non renseignée' 
                    ? categorizerSituation(e.situationActuelle)
                    : 'Non renseignée';
                situations[sit] = (situations[sit] || 0) + 1;
            });

            const sortedEntries = Object.entries(situations).sort((a, b) => b[1] - a[1]);
            const labels = sortedEntries.map(entry => entry[0]);
            const data = sortedEntries.map(entry => entry[1]);
            const colors = ['#0098DB', '#00C0B5', '#32D17E', '#FFB612', '#FF6319', '#ED2939', '#93509E', '#989386', '#2962FF', '#01579B'];

            const ctx = document.getElementById('situationsChart');
            if (situationsChart) situationsChart.destroy();

            situationsChart = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: labels,
                    datasets: [{
                        label: 'Nombre d\'étudiants',
                        data: data,
                        backgroundColor: colors.slice(0, labels.length),
                        borderColor: '#FFFFFF',
                        borderWidth: 3
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: true,
                    plugins: {
                        legend: { 
                            display: true,
                            position: 'right',
                            labels: {
                                font: { size: 15, family: 'Roboto', weight: '500' },
                                padding: 18,
                                usePointStyle: true,
                                pointStyle: 'circle'
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: ctx => {
                                    const total = ctx.dataset.data.reduce((a, b) => a + b, 0);
                                    return `${ctx.label}: ${ctx.parsed} étudiant(s) (${((ctx.parsed / total) * 100).toFixed(1)}%)`;
                                }
                            },
                            backgroundColor: 'rgba(0, 0, 0, 0.8)',
                            padding: 12,
                            titleFont: { size: 14, family: 'Roboto' },
                            bodyFont: { size: 13, family: 'Roboto' }
                        },
                        datalabels: {
                            formatter: (val, ctx) => {
                                const total = ctx.dataset.data.reduce((a, b) => a + b, 0);
                                const percentage = ((val / total) * 100).toFixed(1);
                                return percentage > 5 ? `${val}\n(${percentage}%)` : '';
                            },
                            color: '#FFFFFF',
                            font: { weight: 'bold', size: 13, family: 'Roboto' },
                            textAlign: 'center'
                        }
                    }
                },
                plugins: [ChartDataLabels]
            });
        }

        function categorizerSituation(situation) {
            const sit = situation.toLowerCase();
            if (sit.includes('doctorat') || sit.includes('thèse') || sit.includes('phd')) return 'Doctorat';
            if (sit.includes('fonctionnaire') || sit.includes('fonction publique') || sit.includes('titulaire') || sit.includes('territorial')) return 'Fonctionnaire';
            if (sit.includes('cdi') || sit.includes('cdd') || sit.includes('emploi') || sit.includes('ingénieur') || sit.includes('chargé') || sit.includes('contrat')) return 'CDI/CDD';
            if (sit.includes('stage') || sit.includes('stagiaire')) return 'Stage';
            if (sit.includes('recherche') || sit.includes('cherche')) return 'Recherche emploi';
            if (sit.includes('freelance') || sit.includes('indépendant') || sit.includes('auto-entrepreneur')) return 'Freelance';
            if (sit.includes('vie') || sit.includes('via') || sit.includes('volontariat') || sit.includes('césure') || sit.includes('cesure')) return 'VIE/VIA/Césure';
            return 'Réorientation/Études';
        }

        function categorizerSituationSimplifiee(situation) {
            const sit = situation.toLowerCase();
            
            if (sit.includes('cdi') || sit.includes('emploi') || sit.includes('ingénieur') || sit.includes('chargé') ||
                sit.includes('cdd') || sit.includes('contrat') ||
                sit.includes('freelance') || sit.includes('indépendant') || sit.includes('auto-entrepreneur') ||
                sit.includes('vie') || sit.includes('via') || sit.includes('volontariat') ||
                sit.includes('stage') || sit.includes('stagiaire') ||
                sit.includes('fonctionnaire') || sit.includes('fonction publique') || sit.includes('titulaire') || sit.includes('territorial')) {
                return 'Emploi';
            }
            
            if (sit.includes('doctorat') || sit.includes('thèse') || sit.includes('phd')) {
                return 'Doctorat';
            }
            
            if (sit.includes('master') || sit.includes('étude') || sit.includes('etude') || sit.includes('formation') || 
                sit.includes('école') || sit.includes('ecole') || sit.includes('université') || sit.includes('universite')) {
                return 'Poursuite d\'études';
            }
            
            return 'Autres';
        }

        function creerGraphiqueComparaison() {
            const now = new Date();
            const annee = now.getFullYear();
            const anneeEnCours = (now.getMonth() + 1) >= 9 ? `${annee}-${annee + 1}` : `${annee - 1}-${annee}`;
            
            const etudiantsFiltre = etudiants.filter(e => e.promotion !== anneeEnCours);
            
            if (etudiantsFiltre.length === 0) {
                if (comparaisonChart) {
                    comparaisonChart.destroy();
                    comparaisonChart = null;
                }
                return;
            }

            const etudiantsClassique = etudiantsFiltre.filter(e => e.parcours === 'classique');
            const etudiantsH2O = etudiantsFiltre.filter(e => e.parcours === 'h2o');

            const situationsClassique = {};
            const situationsH2O = {};

            etudiantsClassique.forEach(e => {
                const sit = e.situationActuelle && e.situationActuelle !== 'Non renseignée' 
                    ? categorizerSituationSimplifiee(e.situationActuelle)
                    : 'Autres';
                situationsClassique[sit] = (situationsClassique[sit] || 0) + 1;
            });

            etudiantsH2O.forEach(e => {
                const sit = e.situationActuelle && e.situationActuelle !== 'Non renseignée' 
                    ? categorizerSituationSimplifiee(e.situationActuelle)
                    : 'Autres';
                situationsH2O[sit] = (situationsH2O[sit] || 0) + 1;
            });

            const labels = ['Emploi', 'Doctorat', 'Poursuite d\'études', 'Autres'];
            const dataClassique = labels.map(label => situationsClassique[label] || 0);
            const dataH2O = labels.map(label => situationsH2O[label] || 0);

            const ctx = document.getElementById('comparaisonChart');
            if (comparaisonChart) comparaisonChart.destroy();

            comparaisonChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: labels,
                    datasets: [
                        {
                            label: 'Master IWS Classique',
                            data: dataClassique,
                            backgroundColor: '#5FCF80',
                            borderColor: '#5FCF80',
                            borderWidth: 1,
                            borderRadius: 8,
                            barThickness: 20
                        },
                        {
                            label: 'Label H2O\'Lyon',
                            data: dataH2O,
                            backgroundColor: '#F56B73',
                            borderColor: '#F56B73',
                            borderWidth: 1,
                            borderRadius: 8,
                            barThickness: 20
                        }
                    ]
                },
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: true,
                    plugins: {
                        legend: {
                            display: true,
                            position: 'top',
                            labels: {
                                font: { size: 15, family: 'Roboto', weight: '600' },
                                padding: 20
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return `${context.dataset.label}: ${context.parsed.x} étudiant(s)`;
                                }
                            },
                            backgroundColor: 'rgba(0, 0, 0, 0.8)',
                            padding: 12,
                            titleFont: { size: 14, family: 'Roboto' },
                            bodyFont: { size: 13, family: 'Roboto' }
                        },
                        datalabels: {
                            anchor: function(context) {
                                return context.dataset.data[context.dataIndex] <= 2 ? 'end' : 'center';
                            },
                            align: function(context) {
                                return context.dataset.data[context.dataIndex] <= 2 ? 'end' : 'center';
                            },
                            formatter: (value) => value > 0 ? value : '',
                            color: function(context) {
                                if (context.dataset.data[context.dataIndex] <= 2) {
                                    return context.dataset.backgroundColor;
                                }
                                return '#FFFFFF';
                            },
                            font: { weight: 'bold', size: 13, family: 'Roboto' },
                            offset: 4
                        }
                    },
                    scales: {
                        x: { display: false, beginAtZero: true },
                        y: {
                            ticks: {
                                font: { size: 14, family: 'Roboto', weight: '500' },
                                padding: 10
                            },
                            title: { display: false },
                            grid: { display: false }
                        }
                    },
                    layout: {
                        padding: { left: 20, right: 40, top: 20, bottom: 20 }
                    },
                    categoryPercentage: 0.5,
                    barPercentage: 0.9
                },
                plugins: [ChartDataLabels]
            });
        }

        function creerGraphiqueEvolution() {
            const now = new Date();
            const annee = now.getFullYear();
            const anneeEnCours = (now.getMonth() + 1) >= 9 ? `${annee}-${annee + 1}` : `${annee - 1}-${annee}`;
            
            const promotions = {};
            
            etudiants.forEach(e => {
                if (e.promotion && e.promotion !== anneeEnCours) {
                    if (!promotions[e.promotion]) {
                        promotions[e.promotion] = { total: 0, classique: 0, h2o: 0 };
                    }
                    promotions[e.promotion].total++;
                    if (e.parcours === 'classique') {
                        promotions[e.promotion].classique++;
                    } else if (e.parcours === 'h2o') {
                        promotions[e.promotion].h2o++;
                    }
                }
            });

            const promotionsTriees = Object.keys(promotions).sort();
            
            if (promotionsTriees.length === 0) {
                if (evolutionChart) {
                    evolutionChart.destroy();
                    evolutionChart = null;
                }
                return;
            }

            const labels = promotionsTriees;
            const dataClassique = labels.map(p => promotions[p].classique);
            const dataH2O = labels.map(p => promotions[p].h2o);

            const ctx = document.getElementById('evolutionChart');
            if (evolutionChart) evolutionChart.destroy();

            evolutionChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: labels,
                    datasets: [
                        {
                            label: 'Master IWS Classique',
                            data: dataClassique,
                            borderColor: '#5FCF80',
                            backgroundColor: 'rgba(95, 207, 128, 0.1)',
                            borderWidth: 3,
                            tension: 0.4,
                            fill: true,
                            pointRadius: 5,
                            pointHoverRadius: 7,
                            pointBackgroundColor: '#5FCF80',
                            pointBorderColor: '#FFFFFF',
                            pointBorderWidth: 2
                        },
                        {
                            label: 'Label H2O\'Lyon',
                            data: dataH2O,
                            borderColor: '#F56B73',
                            backgroundColor: 'rgba(245, 107, 115, 0.1)',
                            borderWidth: 3,
                            tension: 0.4,
                            fill: true,
                            pointRadius: 5,
                            pointHoverRadius: 7,
                            pointBackgroundColor: '#F56B73',
                            pointBorderColor: '#FFFFFF',
                            pointBorderWidth: 2
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: true,
                    plugins: {
                        legend: {
                            display: true,
                            position: 'top',
                            labels: {
                                font: { size: 14, family: 'Roboto', weight: '600' },
                                padding: 15,
                                usePointStyle: true
                            }
                        },
                        tooltip: {
                            backgroundColor: 'rgba(0, 0, 0, 0.8)',
                            padding: 12,
                            titleFont: { size: 14, family: 'Roboto' },
                            bodyFont: { size: 13, family: 'Roboto' },
                            callbacks: {
                                label: function(context) {
                                    return `${context.dataset.label}: ${context.parsed.y} étudiant(s)`;
                                }
                            }
                        },
                        datalabels: { display: false }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                stepSize: 1,
                                font: { size: 12, family: 'Roboto' }
                            },
                            title: {
                                display: true,
                                text: 'Nombre d\'étudiants',
                                font: { size: 13, family: 'Roboto', weight: '600' }
                            },
                            grid: { color: 'rgba(0, 0, 0, 0.05)' }
                        },
                        x: {
                            ticks: {
                                font: { size: 12, family: 'Roboto' },
                                maxRotation: 45,
                                minRotation: 45
                            },
                            title: {
                                display: true,
                                text: 'Promotion',
                                font: { size: 13, family: 'Roboto', weight: '600' }
                            },
                            grid: { display: false }
                        }
                    }
                },
                plugins: [ChartDataLabels]
            });
        }

        function exporterDonnees() {
            // Code identique à votre version originale
        }

        async function importerDonnees(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = async function(e) {
                try {
                    const data = new Uint8Array(e.target.result);
                    const workbook = XLSX.read(data, { type: 'array' });
                    const jsonData = XLSX.utils.sheet_to_json(workbook.Sheets[workbook.SheetNames[0]]);

                    if (jsonData.length === 0) {
                        alert('❌ Le fichier Excel est vide !');
                        return;
                    }

                    if (!confirm(`Voulez-vous importer ${jsonData.length} étudiant(s) ?\n\nCela ajoutera ces données aux données existantes.`)) return;

                    for (const row of jsonData) {
                        const parcours = row['Parcours']?.toLowerCase().includes('h2o') ? 'h2o' : 'classique';
                        const etudiant = {
                            nom: row['Nom'] || 'Nom inconnu',
                            email: row['Email'] || 'Non renseigné',
                            promotion: row['Promotion'] || '',
                            parcours: parcours,
                            situationActuelle: row['Situation actuelle'] || 'Non renseignée',
                            createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                            createdBy: currentUser.uid
                        };

                        if (parcours === 'h2o') {
                            etudiant.conditionsH2O = row['Conditions H2O validées'] ? row['Conditions H2O validées'].split(' | ') : [];
                            etudiant.stageIndividuel = 'Non renseigné';
                            etudiant.projetGrappe = 'Non renseigné';
                            etudiant.liensProductions = 'Aucun lien fourni';
                        } else {
                            etudiant.conditionsH2O = [];
                            etudiant.stageIndividuel = row['Stage individuel'] || 'Non renseigné';
                            etudiant.projetGrappe = row['Projet grappe'] || 'Non renseigné';
                            etudiant.liensProductions = row['Liens productions'] || 'Aucun lien fourni';
                        }
                        
                        await ajouterEtudiant(etudiant);
                    }

                    event.target.value = '';
                    await chargerEtudiants();
                    alert(`✅ ${jsonData.length} étudiant(s) importé(s) avec succès !`);
                } catch (error) {
                    alert('❌ Erreur lors de l\'import : ' + error.message);
                }
            };
            reader.readAsArrayBuffer(file);
        }

        // ============================================
        // GESTION DES DEMANDES D'ACCÈS
        // ============================================
        async function chargerDemandesEnAttente() {
            try {
                const snapshot = await db.collection('users').where('status', '==', 'pending').get();
                const count = snapshot.size;
                document.getElementById('pendingCount').textContent = count;
                
                // Changer la couleur du badge si des demandes sont en attente
                const badge = document.getElementById('pendingCount');
                if (count > 0) {
                    badge.style.background = '#e74c3c';
                    badge.style.color = 'white';
                } else {
                    badge.style.background = 'white';
                    badge.style.color = '#FF6319';
                }
            } catch (error) {
                console.error('Erreur chargement demandes:', error);
            }
        }

        async function ouvrirDemandesAcces() {
            document.getElementById('accessRequestsModal').style.display = 'block';
            await afficherDemandesAcces();
        }

        function fermerDemandesAcces() {
            document.getElementById('accessRequestsModal').style.display = 'none';
        }

        async function afficherDemandesAcces() {
            try {
                const snapshot = await db.collection('users').where('status', '==', 'pending').get();
                const container = document.getElementById('accessRequestsList');
                
                if (snapshot.empty) {
                    container.innerHTML = `
                        <div style="text-align: center; padding: 50px; color: #999;">
                            <div style="font-size: 4em; margin-bottom: 20px;">✅</div>
                            <p style="font-size: 1.2em;">Aucune demande en attente</p>
                        </div>
                    `;
                    return;
                }
                
                let html = '';
                const demandes = [];
                snapshot.forEach(doc => {
                    demandes.push({ id: doc.id, data: doc.data() });
                });
                
                // Trier par date dans le code JavaScript au lieu de Firestore
                demandes.sort((a, b) => {
                    const dateA = a.data.createdAt ? a.data.createdAt.toDate() : new Date(0);
                    const dateB = b.data.createdAt ? b.data.createdAt.toDate() : new Date(0);
                    return dateB - dateA; // Plus récent en premier
                });
                
                demandes.forEach(item => {
                    const data = item.data;
                    const date = data.createdAt ? data.createdAt.toDate().toLocaleString('fr-FR') : 'Date inconnue';
                    
                    html += `
                        <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin-bottom: 15px; border-left: 4px solid #FFB612;">
                            <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 15px;">
                                <div style="flex: 1; min-width: 200px;">
                                    <div style="font-size: 1.2em; font-weight: 600; color: #333; margin-bottom: 5px;">
                                        📧 ${data.email}
                                    </div>
                                    <div style="color: #666; font-size: 0.9em;">
                                        🕐 Demande créée le ${date}
                                    </div>
                                </div>
                                <div style="display: flex; gap: 10px;">
                                    <button onclick="approuverUtilisateur('${item.id}', '${data.email}')" 
                                            style="background: linear-gradient(135deg, #38ef7d 0%, #11998e 100%); color: white; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 600; cursor: pointer; transition: transform 0.2s;">
                                        ✅ Approuver
                                    </button>
                                    <button onclick="refuserUtilisateur('${item.id}', '${data.email}')" 
                                            style="background: linear-gradient(135deg, #f5576c 0%, #c0392b 100%); color: white; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 600; cursor: pointer; transition: transform 0.2s;">
                                        ❌ Refuser
                                    </button>
                                </div>
                            </div>
                        </div>
                    `;
                });
                
                container.innerHTML = html;
            } catch (error) {
                console.error('Erreur affichage demandes:', error);
                alert('Erreur lors du chargement des demandes: ' + error.message);
            }
        }

        // ========================================
        // FONCTION POUR L'ONGLET ADMIN
        // ========================================
        async function chargerDemandesOngletAdmin() {
            try {
                const snapshot = await db.collection('users').where('status', '==', 'pending').get();
                const container = document.getElementById('admin-requests-list');
                
                if (snapshot.empty) {
                    container.innerHTML = `
                        <div style="text-align: center; padding: 50px; color: #999;">
                            <div style="font-size: 3em; margin-bottom: 20px;">✅</div>
                            <p style="font-size: 1.1em;">Aucune demande en attente</p>
                            <p style="font-size: 0.9em; margin-top: 10px;">Toutes les demandes d'accès ont été traitées.</p>
                        </div>
                    `;
                    return;
                }
                
                let html = '';
                const demandes = [];
                snapshot.forEach(doc => {
                    demandes.push({ id: doc.id, data: doc.data() });
                });
                
                // Trier par date
                demandes.sort((a, b) => {
                    const dateA = a.data.createdAt ? a.data.createdAt.toDate() : new Date(0);
                    const dateB = b.data.createdAt ? b.data.createdAt.toDate() : new Date(0);
                    return dateB - dateA;
                });
                
                // Créer les cartes
                demandes.forEach(item => {
                    const data = item.data;
                    const dateCreation = data.createdAt ? data.createdAt.toDate().toLocaleDateString('fr-FR', {
                        day: '2-digit',
                        month: '2-digit',
                        year: 'numeric',
                        hour: '2-digit',
                        minute: '2-digit'
                    }) : 'Date inconnue';
                    
                    html += `
                        <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin-bottom: 15px; border-left: 4px solid #FFB612;">
                            <div style="display: flex; justify-content: space-between; align-items: start; gap: 20px; flex-wrap: wrap;">
                                <div style="flex: 1;">
                                    <div style="font-size: 1.2em; font-weight: 600; color: #333; margin-bottom: 5px;">
                                        📧 ${data.email}
                                    </div>
                                    <div style="color: #666; font-size: 0.9em;">
                                        📅 Demande effectuée le ${dateCreation}
                                    </div>
                                </div>
                                <div style="display: flex; gap: 10px;">
                                    <button onclick="approuverUtilisateurAdmin('${item.id}', '${data.email}')" 
                                            style="background: linear-gradient(135deg, #5FCF80 0%, #27ae60 100%); color: white; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                                        ✅ Approuver
                                    </button>
                                    <button onclick="refuserUtilisateurAdmin('${item.id}', '${data.email}')" 
                                            style="background: linear-gradient(135deg, #f5576c 0%, #c0392b 100%); color: white; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                                        ❌ Refuser
                                    </button>
                                </div>
                            </div>
                        </div>
                    `;
                });
                
                container.innerHTML = html;
            } catch (error) {
                console.error('Erreur chargement demandes onglet admin:', error);
                document.getElementById('admin-requests-list').innerHTML = `
                    <div style="text-align: center; padding: 50px; color: #e74c3c;">
                        <div style="font-size: 3em; margin-bottom: 20px;">⚠️</div>
                        <p style="font-size: 1.1em;">Erreur lors du chargement des demandes</p>
                        <p style="font-size: 0.9em; margin-top: 10px;">${error.message}</p>
                    </div>
                `;
            }
        }

        async function approuverUtilisateurAdmin(userId, email) {
            if (!confirm(`Voulez-vous approuver l'accès pour ${email} ?`)) return;
            
            try {
                await db.collection('users').doc(userId).update({
                    status: 'approved',
                    approvedAt: firebase.firestore.FieldValue.serverTimestamp(),
                    approvedBy: currentUser.email
                });
                
                alert(`✅ Accès approuvé pour ${email}`);
                await chargerDemandesOngletAdmin();
                await chargerDemandesEnAttente();
            } catch (error) {
                console.error('Erreur approbation:', error);
                alert('Erreur lors de l\'approbation');
            }
        }

        async function refuserUtilisateurAdmin(userId, email) {
            if (!confirm(`Voulez-vous refuser l'accès pour ${email} ?`)) return;
            
            try {
                await db.collection('users').doc(userId).update({
                    status: 'rejected',
                    rejectedAt: firebase.firestore.FieldValue.serverTimestamp(),
                    rejectedBy: currentUser.email
                });
                
                alert(`❌ Accès refusé pour ${email}`);
                await chargerDemandesOngletAdmin();
                await chargerDemandesEnAttente();
            } catch (error) {
                console.error('Erreur refus:', error);
                alert('Erreur lors du refus');
            }
        }

        async function approuverUtilisateur(userId, email) {
            if (!confirm(`Voulez-vous approuver l'accès pour ${email} ?`)) return;
            
            try {
                await db.collection('users').doc(userId).update({
                    status: 'approved',
                    approvedAt: firebase.firestore.FieldValue.serverTimestamp(),
                    approvedBy: currentUser.email
                });
                
                alert(`✅ Accès approuvé pour ${email}`);
                await afficherDemandesAcces();
                await chargerDemandesEnAttente();
            } catch (error) {
                console.error('Erreur approbation:', error);
                alert('Erreur lors de l\'approbation');
            }
        }

        async function refuserUtilisateur(userId, email) {
            if (!confirm(`Voulez-vous refuser l'accès pour ${email} ?`)) return;
            
            try {
                await db.collection('users').doc(userId).update({
                    status: 'rejected',
                    rejectedAt: firebase.firestore.FieldValue.serverTimestamp(),
                    rejectedBy: currentUser.email
                });
                
                alert(`❌ Accès refusé pour ${email}`);
                await afficherDemandesAcces();
                await chargerDemandesEnAttente();
            } catch (error) {
                console.error('Erreur refus:', error);
                alert('Erreur lors du refus');
            }
        }

        // ========================================
        // GESTION DES COMPÉTENCES
        // ========================================
        
        // Données par défaut des compétences (utilisées si rien dans Firebase)
        const competencesParDefaut = [
            {
                id: 'ue1',
                icon: '🌊',
                titre: 'Challenges in Water Sciences',
                description: 'Ce cours explore les défis contemporains liés à l\'eau à travers trois modules thématiques...',
                competences: [
                    'Observer, décrire et caractériser l\'état hydrologique, biogéochimique et écologique des bassins versants',
                    'Analyser, résoudre et gérer les problèmes liés à la protection des hydrosystèmes',
                    'Organiser la prévention et la prévision des risques hydrologiques'
                ]
            },
            {
                id: 'ue2',
                icon: '🔬',
                titre: 'Water Quality',
                description: 'Ce cours se concentre sur la compréhension et l\'analyse de la qualité de l\'eau...',
                competences: [
                    'Maîtriser les méthodes d\'analyse physico-chimiques de l\'eau',
                    'Évaluer la qualité des ressources en eau',
                    'Proposer des solutions pour améliorer la qualité de l\'eau'
                ]
            }
        ];

        async function chargerCompetences() {
            try {
                const doc = await db.collection('configuration').doc('competences').get();
                let competences;
                
                if (doc.exists) {
                    competences = doc.data().ues || competencesParDefaut;
                } else {
                    // Initialiser avec les données par défaut si rien n'existe
                    competences = competencesParDefaut;
                    await db.collection('configuration').doc('competences').set({
                        ues: competences,
                        derniereMaj: firebase.firestore.FieldValue.serverTimestamp()
                    });
                }
                
                afficherCompetences(competences);
            } catch (error) {
                console.error('Erreur chargement compétences:', error);
                afficherCompetences(competencesParDefaut);
            }
        }

        function afficherCompetences(competences) {
            const container = document.getElementById('competences-container');
            if (!container) return;
            
            let html = '';
            competences.forEach(ue => {
                html += `
                    <div class="ue-card">
                        <div class="ue-header" onclick="toggleUE('${ue.id}')">
                            <div class="ue-title">
                                <span class="ue-icon">${ue.icon}</span>
                                <span>${ue.titre}</span>
                            </div>
                            <span class="ue-toggle" id="toggle-${ue.id}">▼</span>
                        </div>
                        <div id="content-${ue.id}" class="ue-content">
                            <p class="ue-description">${ue.description}</p>
                            <div class="competences-titre">Compétences acquises :</div>
                            <ul class="competences-liste">
                                ${ue.competences.map(comp => `<li>${comp}</li>`).join('')}
                            </ul>
                        </div>
                    </div>
                `;
            });
            
            container.innerHTML = html;
        }

        async function ouvrirEditionCompetences() {
            try {
                const doc = await db.collection('configuration').doc('competences').get();
                const competences = doc.exists ? doc.data().ues : competencesParDefaut;
                
                let html = '<div style="display: flex; flex-direction: column; gap: 20px;">';
                
                competences.forEach((ue, index) => {
                    html += `
                        <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; border-left: 4px solid #0098DB;">
                            <div style="margin-bottom: 15px;">
                                <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Icône UE ${index + 1}</label>
                                <input type="text" id="icon-${index}" value="${ue.icon}" style="width: 100px; padding: 8px; border: 2px solid #ddd; border-radius: 5px; font-size: 24px;">
                            </div>
                            <div style="margin-bottom: 15px;">
                                <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Titre UE ${index + 1}</label>
                                <input type="text" id="titre-${index}" value="${ue.titre}" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 16px;">
                            </div>
                            <div style="margin-bottom: 15px;">
                                <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Description</label>
                                <textarea id="desc-${index}" rows="3" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 14px; font-family: inherit;">${ue.description}</textarea>
                            </div>
                            <div style="margin-bottom: 15px;">
                                <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Compétences (une par ligne)</label>
                                <textarea id="comp-${index}" rows="6" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 14px; font-family: inherit;">${ue.competences.join('\n')}</textarea>
                            </div>
                            <button onclick="supprimerUE(${index})" style="background: #e74c3c; color: white; border: none; padding: 8px 16px; border-radius: 5px; cursor: pointer; font-weight: 600;">
                                🗑️ Supprimer cette UE
                            </button>
                        </div>
                    `;
                });
                
                html += `
                    <button onclick="ajouterUE()" style="background: linear-gradient(135deg, #5FCF80 0%, #27ae60 100%); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; width: 100%;">
                        ➕ Ajouter une nouvelle UE
                    </button>
                `;
                
                html += '</div>';
                
                document.getElementById('editCompetencesContent').innerHTML = html;
                document.getElementById('modalEditCompetences').style.display = 'block';
            } catch (error) {
                console.error('Erreur ouverture édition:', error);
                alert('Erreur lors de l\'ouverture de l\'édition');
            }
        }

        function fermerEditionCompetences() {
            document.getElementById('modalEditCompetences').style.display = 'none';
        }

        async function sauvegarderCompetences() {
            try {
                const inputs = document.querySelectorAll('[id^="titre-"]');
                const competences = [];
                
                inputs.forEach((input, index) => {
                    const icon = document.getElementById(`icon-${index}`).value;
                    const titre = document.getElementById(`titre-${index}`).value;
                    const desc = document.getElementById(`desc-${index}`).value;
                    const compText = document.getElementById(`comp-${index}`).value;
                    const compArray = compText.split('\n').filter(c => c.trim() !== '');
                    
                    competences.push({
                        id: `ue${index + 1}`,
                        icon: icon,
                        titre: titre,
                        description: desc,
                        competences: compArray
                    });
                });
                
                await db.collection('configuration').doc('competences').set({
                    ues: competences,
                    derniereMaj: firebase.firestore.FieldValue.serverTimestamp()
                });
                
                alert('✅ Compétences sauvegardées avec succès !');
                fermerEditionCompetences();
                chargerCompetences();
            } catch (error) {
                console.error('Erreur sauvegarde compétences:', error);
                alert('Erreur lors de la sauvegarde : ' + error.message);
            }
        }

        function ajouterUE() {
            const container = document.getElementById('editCompetencesContent');
            const inputs = document.querySelectorAll('[id^="titre-"]');
            const index = inputs.length;
            
            const nouvelleUE = `
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; border-left: 4px solid #0098DB; animation: slideIn 0.3s;">
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Icône UE ${index + 1}</label>
                        <input type="text" id="icon-${index}" value="📚" style="width: 100px; padding: 8px; border: 2px solid #ddd; border-radius: 5px; font-size: 24px;">
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Titre UE ${index + 1}</label>
                        <input type="text" id="titre-${index}" value="Nouvelle UE" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 16px;">
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Description</label>
                        <textarea id="desc-${index}" rows="3" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 14px; font-family: inherit;">Description de la nouvelle UE...</textarea>
                    </div>
                    <div style="margin-bottom: 15px;">
                        <label style="display: block; font-weight: 600; margin-bottom: 5px; color: #333;">Compétences (une par ligne)</label>
                        <textarea id="comp-${index}" rows="6" style="width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; font-size: 14px; font-family: inherit;">Compétence 1\nCompétence 2\nCompétence 3</textarea>
                    </div>
                    <button onclick="supprimerUE(${index})" style="background: #e74c3c; color: white; border: none; padding: 8px 16px; border-radius: 5px; cursor: pointer; font-weight: 600;">
                        🗑️ Supprimer cette UE
                    </button>
                </div>
            `;
            
            const btnAjouter = container.querySelector('button[onclick="ajouterUE()"]');
            btnAjouter.insertAdjacentHTML('beforebegin', nouvelleUE);
        }

        function supprimerUE(index) {
            if (confirm('Êtes-vous sûr de vouloir supprimer cette UE ?')) {
                const container = document.getElementById('editCompetencesContent');
                const divs = container.querySelectorAll('[style*="background: #f8f9fa"]');
                if (divs[index]) {
                    divs[index].remove();
                }
            }
        }
    </script>
</body>
</html>
