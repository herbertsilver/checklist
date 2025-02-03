<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página com Abas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        .container {
            max-width: 600px;
            margin: 50px auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: left;
        }
        .tabs {
            display: flex;
            justify-content: flex-start;
            margin-bottom: 20px;
        }
        .tab {
            padding: 10px 20px;
            cursor: pointer;
            background: #007BFF;
            color: white;
            border: none;
            border-radius: 5px 5px 0 0;
            margin-right: 5px;
        }
        .tab:hover {
            background: #0056b3;
        }
        .tab-content {
            display: none;
        }
        .active {
            display: block;
        }
        textarea {
            width: 100%;
            max-width: 100%;
            height: 510px;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
            box-sizing: border-box;
            resize: none;
        }
        .checklist-container {
            list-style: none;
            padding: 0;
            max-height: 380px;
            overflow-y: auto;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
        }
        .checklist-container li {
            display: flex;
            align-items: center;
        }
        .checklist-container input[type="checkbox"] {
            margin-right: 10px;
        }
        .select-all-btn {
            background: #28a745;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-bottom: 10px;
        }
        .select-all-btn:hover {
            background: #218838;
        }
        .action-buttons {
            margin-top: 10px;
            display: flex;
            justify-content: flex-end;
        }
        .action-btn {
            background: #007BFF;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-left: 5px;
        }
        .action-btn:hover {
            background: #0056b3;
        }
    </style>
    <script>
        function openTab(tabName) {
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
            document.getElementById(tabName).classList.add('active');
        }
        function toggleSelectAll() {
            let checkboxes = document.querySelectorAll('.checklist-container input[type="checkbox"]');
            let allChecked = Array.from(checkboxes).every(checkbox => checkbox.checked);
            checkboxes.forEach(checkbox => checkbox.checked = !allChecked);
        }
    </script>
</head>
<body>
    <div class="container">
        <div class="tabs">
            <button class="tab" onclick="openTab('checklist')">Recursos</button>
            <button class="tab" onclick="openTab('textbox')">Log de Execução</button>
        </div>
        
        <div id="checklist" class="tab-content active">
            <h2>Recursos</h2>
            <button class="select-all-btn" onclick="toggleSelectAll()">Selecionar/Desmarcar Tudo</button>
            <ul class="checklist-container">
                <li><input type="checkbox"> Item 1</li>
                <li><input type="checkbox"> Item 2</li>
                <li><input type="checkbox"> Item 3</li>
                <li><input type="checkbox"> Item 4</li>
                <li><input type="checkbox"> Item 5</li>
                <li><input type="checkbox"> Item 6</li>
                <li><input type="checkbox"> Item 7</li>
                <li><input type="checkbox"> Item 8</li>
                <li><input type="checkbox"> Item 9</li>
                <li><input type="checkbox"> Item 10</li>
                <li><input type="checkbox"> Item 11</li>
                <li><input type="checkbox"> Item 12</li>
                <li><input type="checkbox"> Item 13</li>
                <li><input type="checkbox"> Item 14</li>
                <li><input type="checkbox"> Item 15</li>
                <li><input type="checkbox"> Item 16</li>
                <li><input type="checkbox"> Item 17</li>
                <li><input type="checkbox"> Item 18</li>
                <li><input type="checkbox"> Item 19</li>
                <li><input type="checkbox"> Item 20</li>
            </ul>
            <div class="action-buttons">
                <button class="action-btn">Ação 1</button>
                <button class="action-btn">Ação 2</button>
                <button class="action-btn">Ação 3</button>
            </div>
        </div>
        
        <div id="textbox" class="tab-content">
            <h2>Log de Execução</h2>
            <textarea id="logArea" readonly></textarea>
        </div>
    </div>
</body>
</html>
