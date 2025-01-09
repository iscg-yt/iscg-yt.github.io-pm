<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>玩家地圖推薦</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
        }
        .hamburger {
            position: fixed;
            top: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .hamburger div {
            height: 6px;
            width: 100%;
            background-color: black;
            border-radius: 3px;
        }
        .menu {
            display: none;
            position: fixed;
            top: 80px;
            right: 20px;
            background-color: white;
            border: 2px solid #ccc;
            border-radius: 12px;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
            padding: 20px;
            width: 250px;
        }
        .menu a {
            text-decoration: none;
            color: black;
            font-size: 18px;
            display: block;
            padding: 12px 15px;
            border-bottom: 1px solid #ccc;
        }
        .menu a:last-child {
            border-bottom: none;
        }
        .search-bar {
            display: flex;
            justify-content: center;
            margin: 20px 0;
        }
        .search-bar input {
            width: 300px;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 8px;
            margin-right: 10px;
        }
        .search-bar button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }
        .search-bar button:hover {
            background-color: #0056b3;
        }
        .container {
            max-width: 800px;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            margin: 20px auto;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .section {
            text-align: center;
            margin-bottom: 30px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="hamburger" onclick="toggleMenu()">
        <div></div>
        <div></div>
        <div></div>
    </div>
    <div class="menu" id="menu">
        <a href="https://iscg-yt.github.io"><p style="font-size: 30px;">1.Map code</p></a>
        <a href="https://linktr.ee/ff.cg"><p style="font-size: 30px;">2. All social medias</p></a>
        <a href="https://forms.zohopublic.com/sobrickffgm1/form/Playersmaprecommend/formperma/lsD3viLptVn5sEEwdmRBHRpsjEWC7ZF-q0gihbwDW7k"><p style="font-size: 30px;">3. Players map recommend（問卷）</p></a>
        <a href="https://linktr.ee/ff.cg"><p style="font-size: 30px;">4. Players map recommend（地圖）</p></a>
    </div>
    <div class="search-bar">
        <input type="text" id="searchInput" placeholder="搜尋關鍵字...">
        <button onclick="searchContent()">搜尋</button>
    </div>
    <div class="container">
        <!-- Section 1 -->
        <div class="section" data-keywords="">
            <h1>up coming</h1>
            <img src="" alt="up coming">
            <p id="text1">#</p>
            <button class="copy-btn" onclick="copyText('text1')">複製代碼</button>
        </div>
        <!-- Section 1 -->
        <div class="section" data-keywords="">
            <h1>up coming</h1>
            <img src="" alt="up coming">
            <p id="text1">#</p>
            <button class="copy-btn" onclick="copyText('text1')">複製代碼</button>
        </div>
    <script>
        // 切換漢堡菜單顯示
        function toggleMenu() {
            const menu = document.getElementById('menu');
            menu.style.display = menu.style.display === 'block' ? 'none' : 'block';
        }
        // 複製文字功能
        function copyText(elementId) {
            const text = document.getElementById(elementId).innerText;
            navigator.clipboard.writeText(text).then(() => {
                alert("已複製！快去玩玩看地圖吧！");
            }).catch(err => {
                alert("複製失敗，請重試！");
            });
        }
        // 搜尋功能
        function filterSections() {
            const query = document.getElementById('search').value.toLowerCase();
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                const keywords = section.getAttribute('data-keywords').toLowerCase();
                if (keywords.includes(query)) {
                    section.style.display = "block";
                } else {
                    section.style.display = "none";
                }
            });
        }
    </script>
</body>
</html>
