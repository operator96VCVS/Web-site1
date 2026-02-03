
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Saluton! - Основы эсперанто</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: white;
            color: #333;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
        }

        /* Зеленая полоса внизу */
        body::after {
            content: '';
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 150px;
            background-color: #2e8b57;
            z-index: -1;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            flex: 1;
        }

        /* Стили навигации */
        nav {
            background-color: white;
            padding: 20px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #2e8b57;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-link {
            color: #333;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-link:hover {
            color: #2e8b57;
        }

        /* Стили главной страницы */
        .welcome-section {
            text-align: center;
            padding: 60px 0 40px;
        }

        h1 {
            color: #2e8b57;
            font-size: 3.5rem;
            margin-bottom: 20px;
            letter-spacing: 1px;
        }

        .subtitle {
            font-size: 1.4rem;
            color: #666;
            max-width: 600px;
            margin: 0 auto 40px;
            line-height: 1.6;
            font-weight: 500;
        }

        .buttons-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
            margin-top: 50px;
        }

        .btn {
            background-color: #2e8b57;
            color: white;
            border: none;
            padding: 16px 32px;
            font-size: 1.1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            min-width: 200px;
            text-decoration: none;
            display: inline-block;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .btn:hover {
            background-color: #26734d;
            transform: translateY(-3px);
            box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
        }

        /* Стили страницы алфавита */
        .alphabet-section {
            padding: 40px 0 80px;
        }

        .page-title {
            text-align: center;
            color: #2e8b57;
            margin-bottom: 40px;
            font-size: 2.5rem;
        }

        .alphabet-container {
            background-color: #2e8b57;
            border-radius: 15px;
            padding: 30px;
            margin: 0 auto;
            max-width: 900px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .alphabet-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 15px;
        }

        .letter-item {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .letter-btn {
            background-color: white;
            color: #2e8b57;
            border: none;
            border-radius: 12px;
            font-size: 1.8rem;
            font-weight: 700;
            width: 100px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
        }

        .letter-btn:hover {
            background-color: #f0f0f0;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }

        .letter-name {
            font-size: 0.8rem;
            margin-top: 8px;
            color: white;
            font-weight: 500;
            text-align: center;
            line-height: 1.3;
            min-height: 2em;
        }

        /* Стили страницы списка слов */
        .word-list-section {
            padding: 40px 0 80px;
        }

        .word-list-container {
            background-color: #f9f9f9;
            border-radius: 15px;
            padding: 40px;
            margin: 0 auto;
            max-width: 800px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .word-list-title {
            text-align: center;
            color: #2e8b57;
            margin-bottom: 30px;
            font-size: 1.8rem;
        }

        .word-list-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .word-pair {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 3px 6px rgba(0, 0, 0, 0.08);
            transition: all 0.3s;
        }

        .word-pair:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.12);
        }

        .esperanto-word {
            color: #2e8b57;
            font-weight: 700;
            font-size: 1.2rem;
        }

        .translation {
            color: #333;
            font-size: 1.1rem;
            font-weight: 500;
        }

        /* Стили футера */
        footer {
            background-color: #2e8b57;
            color: white;
            padding: 20px 0;
            text-align: center;
            margin-top: auto;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Убрали правую часть футера с названием компании */
        .footer-content > div:first-child {
            width: 100%;
            text-align: center;
        }

        .footer-links {
            display: none;
        }

        /* Страницы по умолчанию скрыты */
        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        /* Адаптивность */
        @media (max-width: 992px) {
            .alphabet-grid {
                grid-template-columns: repeat(4, 1fr);
                gap: 15px;
            }
            
            .alphabet-container {
                max-width: 700px;
            }
            
            .word-list-grid {
                grid-template-columns: 1fr;
                gap: 15px;
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.8rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .buttons-container {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
                max-width: 300px;
            }
            
            .alphabet-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 12px;
            }
            
            .letter-btn {
                width: 80px;
                height: 80px;
                font-size: 1.6rem;
                border-radius: 10px;
            }
            
            .word-list-container {
                padding: 25px;
            }
            
            .word-pair {
                padding: 12px 15px;
            }
            
            .esperanto-word {
                font-size: 1.1rem;
            }
            
            .translation {
                font-size: 1rem;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 15px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .subtitle {
                font-size: 1.1rem;
            }
            
            .alphabet-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 10px;
            }
            
            .letter-btn {
                width: 70px;
                height: 70px;
                font-size: 1.5rem;
            }
            
            .alphabet-container {
                padding: 20px;
            }
            
            .letter-name {
                font-size: 0.7rem;
            }
            
            .word-list-title {
                font-size: 1.5rem;
            }
            
            .word-pair {
                flex-direction: column;
                align-items: flex-start;
                gap: 8px;
            }
        }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav>
        <div class="container">
            <div class="nav-content">
                <a href="#" class="logo" data-page="home">Saluton!</a>
                <div class="nav-links">
                    <a href="#" class="nav-link" data-page="home">Главная</a>
                    <a href="#" class="nav-link" data-page="alphabet">Алфавит</a>
                    <a href="#" class="nav-link" data-page="word-list">Список слов</a>
                    <a href="#" class="nav-link" data-page="practice">Практика слов</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Главная страница -->
    <div id="home" class="page active">
        <div class="container">
            <div class="welcome-section">
                <h1>Saluton!</h1>
                <p class="subtitle">Основы эсперанто онлайн</p>
                
                <div class="buttons-container">
                    <button class="btn" data-page="alphabet">Алфавит</button>
                    <button class="btn" data-page="word-list">Список слов</button>
                    <button class="btn" data-page="practice">Практика слов</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Страница алфавита -->
    <div id="alphabet" class="page">
        <div class="container">
            <div class="alphabet-section">
                <h2 class="page-title">Алфавит эсперанто</h2>
                <div class="alphabet-container">
                    <div class="alphabet-grid" id="alphabet-grid">
                        <!-- Буквы алфавита эсперанто будут сгенерированы через JavaScript -->
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Страница списка слов -->
    <div id="word-list" class="page">
        <div class="container">
            <div class="word-list-section">
                <h2 class="page-title">Список слов эсперанто</h2>
                <div class="word-list-container">
                    <h3 class="word-list-title">Основные слова и выражения</h3>
                    <div class="word-list-grid" id="word-list-grid">
                        <!-- Слова эсперанто и их переводы будут добавлены через JavaScript -->
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Страница практики слов -->
    <div id="practice" class="page">
        <div class="container">
            <div class="alphabet-section">
                <h2 class="page-title">Практика слов эсперанто</h2>
                <p style="text-align: center; margin-bottom: 30px; font-size: 1.2rem;">Здесь вы сможете практиковать слова эсперанто с помощью интерактивных упражнений.</p>
                <div style="background-color: #f9f9f9; padding: 30px; border-radius: 10px; max-width: 800px; margin: 0 auto;">
                    <p>Страница находится в разработке. Вскоре здесь появятся упражнения для запоминания слов, тесты и игры для практики эсперанто.</p>
                    <button class="btn" data-page="home" style="margin-top: 30px;">Вернуться на главную</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Футер -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div>&copy; 2026 Saluton! - Основы эсперанто онлайн</div>
            </div>
        </div>
    </footer>

    <script>
        // Полный алфавит эсперанто (28 букв) с исправленными названиями
        const esperantoAlphabet = [
            { letter: 'A', name: 'а' },
            { letter: 'B', name: 'бо' },
            { letter: 'C', name: 'цо' },
            { letter: 'Ĉ', name: 'чо' },
            { letter: 'D', name: 'до' },
            { letter: 'E', name: 'э' },
            { letter: 'F', name: 'фо' },
            { letter: 'G', name: 'го' },
            { letter: 'Ĝ', name: 'джо' },
            { letter: 'H', name: 'хо/го' },
            { letter: 'Ĥ', name: 'хо' },
            { letter: 'I', name: 'и' },
            { letter: 'J', name: 'йо' },
            { letter: 'Ĵ', name: 'жо' },
            { letter: 'K', name: 'ко' },
            { letter: 'L', name: 'ло' },
            { letter: 'M', name: 'мо' },
            { letter: 'N', name: 'но' },
            { letter: 'O', name: 'о' },
            { letter: 'P', name: 'по' },
            { letter: 'R', name: 'ро' },
            { letter: 'S', name: 'со' },
            { letter: 'Ŝ', name: 'шо' },
            { letter: 'T', name: 'то' },
            { letter: 'U', name: 'у' },
            { letter: 'Ŭ', name: 'у краткое' },
            { letter: 'V', name: 'во' },
            { letter: 'Z', name: 'зо' }
        ];

        // Слова эсперанто и их переводы
        const wordList = [
            { esperanto: 'Saluton', translation: 'Привет' },
            { esperanto: 'Bonan matenon', translation: 'Доброе утро' },
            { esperanto: 'Bonan tagon', translation: 'Добрый день' },
            { esperanto: 'Bonan vesperon', translation: 'Добрый вечер' },
            { esperanto: 'Ĝis revido', translation: 'До свидания' },
            { esperanto: 'Jes', translation: 'Да' },
            { esperanto: 'Ne', translation: 'Нет' },
            { esperanto: 'Estas', translation: 'Есть' },
            { esperanto: 'Havas', translation: 'Иметь' }
        ];

        // Генерация алфавита эсперанто
        function generateAlphabet() {
            const alphabetGrid = document.getElementById('alphabet-grid');
            alphabetGrid.innerHTML = '';
            
            esperantoAlphabet.forEach(item => {
                const letterElement = document.createElement('div');
                letterElement.className = 'letter-item';
                
                const button = document.createElement('button');
                button.className = 'letter-btn';
                button.textContent = item.letter;
                button.addEventListener('click', () => {
                    alert(`Буква: ${item.letter}\nНазвание: ${item.name}\n\nЭсперанто - язык с фонетическим произношением, где каждая буква читается одинаково всегда!`);
                });
                
                const nameElement = document.createElement('div');
                nameElement.className = 'letter-name';
                nameElement.textContent = item.name;
                
                letterElement.appendChild(button);
                letterElement.appendChild(nameElement);
                alphabetGrid.appendChild(letterElement);
            });
        }

        // Генерация списка слов
        function generateWordList() {
            const wordListGrid = document.getElementById('word-list-grid');
            if (!wordListGrid) return;
            
            wordListGrid.innerHTML = '';
            
            wordList.forEach(item => {
                const wordElement = document.createElement('div');
                wordElement.className = 'word-pair';
                
                const esperantoWord = document.createElement('div');
                esperantoWord.className = 'esperanto-word';
                esperantoWord.textContent = item.esperanto;
                
                const translation = document.createElement('div');
                translation.className = 'translation';
                translation.textContent = item.translation;
                
                wordElement.appendChild(esperantoWord);
                wordElement.appendChild(translation);
                wordListGrid.appendChild(wordElement);
            });
        }

        // Навигация между страницами
        function navigateToPage(pageId) {
            // Скрыть все страницы
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Показать выбранную страницу
            const activePage = document.getElementById(pageId);
            if (activePage) {
                activePage.classList.add('active');
                
                // Если переходим на страницу алфавита, генерируем алфавит
                if (pageId === 'alphabet') {
                    generateAlphabet();
                }
                // Если переходим на страницу списка слов, генерируем список
                else if (pageId === 'word-list') {
                    generateWordList();
                }
            }
        }

        // Инициализация навигации
        document.addEventListener('DOMContentLoaded', function() {
            // Генерация алфавита на главной странице
            generateAlphabet();
            
            // Генерация списка слов
            generateWordList();
            
            // Обработчики для навигации
            document.querySelectorAll('[data-page]').forEach(element => {
                element.addEventListener('click', function(e) {
                    e.preventDefault();
                    const pageId = this.getAttribute('data-page');
                    navigateToPage(pageId);
                });
            });
        });
    </script>
</body>
</html>
