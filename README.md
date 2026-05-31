# EG2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>英语学习网站 - 与小动物一起学英语</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#4F46E5',
                        secondary: '#EC4899',
                        accent: '#10B981',
                        neutral: '#F3F4F6',
                        'neutral-dark': '#6B7280',
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                    animation: {
                        'bounce-slow': 'bounce 2s infinite',
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .text-shadow { text-shadow: 2px 2px 4px rgba(0,0,0,0.2); }
            .animal-card {
                @apply bg-white rounded-2xl shadow-lg p-4 cursor-pointer transform transition-all hover:scale-105 hover:shadow-xl;
            }
            .btn-primary { @apply bg-[#4F46E5] text-white px-6 py-3 rounded-lg font-semibold hover:bg-opacity-90 transition-all shadow-md; }
            .btn-secondary { @apply bg-[#EC4899] text-white px-6 py-3 rounded-lg font-semibold hover:bg-opacity-90 transition-all shadow-md; }
            .btn-accent { @apply bg-[#10B981] text-white px-6 py-3 rounded-lg font-semibold hover:bg-opacity-90 transition-all shadow-md; }
            .input-primary {
                @apply border-2 border-gray-300 rounded-lg px-4 py-3 focus:outline-none focus:border-[#4F46E5] transition-all;
            }
            .card { @apply bg-white rounded-2xl shadow-lg p-6; }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-blue-50 to-purple-50 min-h-screen">
    <div id="app" class="container mx-auto px-4 py-8">
        <!-- 欢迎屏幕 -->
        <div id="welcome-screen" class="flex flex-col items-center justify-center min-h-[80vh]">
            <h1 class="text-5xl md:text-6xl font-bold text-center mb-8 text-[#4F46E5] text-shadow">
                与小动物一起学英语
            </h1>
            <p class="text-xl text-center mb-12 max-w-2xl text-gray-500">
                选择你喜欢的小动物伙伴，开始你的英语学习之旅吧！
            </p>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 w-full max-w-5xl">
                <div class="animal-card" data-animal="cat">
                    <img src="https://p11-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/1686b166e6c046acbb09e90843dcbddf~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=vBoICUN7ybD456lDpyADIhfPy1E%3D" alt="猫" class="w-full h-48 object-contain mb-4">
                    <h3 class="text-xl font-bold text-center text-[#4F46E5]">语语</h3>
                </div>
                <div class="animal-card" data-animal="dog">
                    <img src="https://p11-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/78e1e263807b4060891ef3c24f4f3955~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=rKjHHxHRAD51w9cqBX8M5dRbnU8%3D" alt="狗" class="w-full h-48 object-contain mb-4">
                    <h3 class="text-xl font-bold text-center text-[#4F46E5]">旺旺</h3>
                </div>
                <div class="animal-card" data-animal="rabbit">
                    <img src="https://p6-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/a62a49f6497848e78ffcaced9c2ea5d6~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=srhf%2FAtdcjOvgXaq5AcUIVJTi3E%3D" alt="兔子" class="w-full h-48 object-contain mb-4">
                    <h3 class="text-xl font-bold text-center text-[#4F46E5]">跳跳</h3>
                </div>
                <div class="animal-card" data-animal="panda">
                    <img src="https://p26-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/30d09d3445244ef796892a67a4014469~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247886&x-signature=pEUZ7vHOAlF1FK3Wj%2FuKOl98l2M%3D" alt="熊猫" class="w-full h-48 object-contain mb-4">
                    <h3 class="text-xl font-bold text-center text-[#4F46E5]">盼盼</h3>
                </div>
            </div>
        </div>

        <!-- 学习屏幕 -->
        <div id="learning-screen" class="hidden">
            <div class="flex justify-between items-center mb-8">
                <button id="back-btn" class="flex items-center text-[#4F46E5] font-semibold">
                    <i class="fa fa-arrow-left mr-2"></i> 返回选择
                </button>
                <h2 class="text-2xl font-bold text-[#4F46E5]">英语学习</h2>
                <div class="w-20"></div>
            </div>

            <div class="flex flex-col lg:flex-row gap-8">
                <!-- 左侧动物区 -->
                <div class="lg:w-1/3 flex flex-col items-center">
                    <div id="selected-animal" class="w-64 h-64 mb-6 animate-bounce-slow"></div>
                    <div id="animal-speech-bubble" class="bg-white rounded-2xl p-4 shadow-lg mb-6 max-w-xs text-center">
                        你好！我是你的英语学习伙伴。请输入一个单词开始学习吧！
                    </div>
                    <button id="listen-btn" class="btn-primary flex items-center">
                        <i class="fa fa-volume-up mr-2"></i> 听发音
                    </button>
                </div>

                <!-- 右侧功能模块 -->
                <div class="lg:w-2/3">
                    <!-- 单词查询 -->
                    <div class="card mb-8">
                        <h3 class="text-xl font-bold mb-4 text-[#4F46E5]">单词学习</h3>
                        <div class="flex gap-4 mb-6">
                            <input id="word-input" type="text" class="input-primary flex-grow" placeholder="输入英语单词查询...">
                            <button id="search-btn" class="btn-primary">
                                <i class="fa fa-search mr-2"></i> 查询
                            </button>
                        </div>
                        <div id="word-result" class="hidden">
                            <div class="flex justify-between items-center mb-4">
                                <h4 id="word-title" class="text-2xl font-bold text-[#4F46E5]"></h4>
                                <button id="play-pronunciation" class="text-[#10B981] hover:text-opacity-80 transition-all">
                                    <i class="fa fa-volume-up text-2xl"></i>
                                </button>
                            </div>
                            <p id="word-phonetic" class="text-gray-500 mb-4 hidden"></p>
                            <div id="word-meanings" class="space-y-4"></div>
                        </div>
                    </div>

                    <!-- 发音练习 -->
                    <div class="card mb-8">
                        <h3 class="text-xl font-bold mb-4 text-[#4F46E5]">发音练习</h3>
                        <p class="mb-4 text-gray-500">输入任意英语单词，点击“开始录音”练习发音</p>
                        <div class="mb-4">
                            <input id="practice-word-input" type="text" class="input-primary w-full" placeholder="在这里输入要练习的单词...">
                        </div>
                        <div class="flex gap-4 mb-4">
                            <button id="start-recording" class="btn-secondary flex items-center">
                                <i class="fa fa-microphone mr-2"></i> 开始录音
                            </button>
                            <button id="stop-recording" class="btn-secondary flex items-center hidden">
                                <i class="fa fa-stop mr-2"></i> 停止录音
                            </button>
                        </div>
                        <div id="recording-status" class="mt-4 hidden">
                            <div class="flex items-center">
                                <div class="w-4 h-4 bg-red-500 rounded-full animate-pulse mr-2"></div>
                                <span>正在录音...</span>
                            </div>
                        </div>
                        <div id="pronunciation-result" class="mt-4 hidden">
                            <h4 class="font-semibold mb-2">发音评分：<span id="pronunciation-score" class="text-[#10B981]"></span></h4>
                            <div class="w-full bg-gray-200 rounded-full h-2.5">
                                <div id="score-bar" class="bg-[#10B981] h-2.5 rounded-full" style="width: 0%"></div>
                            </div>
                            <p id="pronunciation-feedback" class="mt-2 text-sm"></p>
                        </div>
                    </div>

                    <!-- 听写练习 -->
                    <div class="card">
                        <h3 class="text-xl font-bold mb-4 text-[#4F46E5]">听写练习</h3>
                        <p class="mb-4 text-gray-500">选择单词数量，开始听写练习</p>
                        <div class="flex flex-wrap gap-4 mb-6">
                            <button class="dictation-btn px-4 py-2 border-2 border-[#4F46E5] text-[#4F46E5] rounded-lg hover:bg-[#4F46E5] hover:text-white transition-all" data-count="10">10个单词</button>
                            <button class="dictation-btn px-4 py-2 border-2 border-[#4F46E5] text-[#4F46E5] rounded-lg hover:bg-[#4F46E5] hover:text-white transition-all" data-count="15">15个单词</button>
                            <button class="dictation-btn px-4 py-2 border-2 border-[#4F46E5] text-[#4F46E5] rounded-lg hover:bg-[#4F46E5] hover:text-white transition-all" data-count="20">20个单词</button>
                            <button class="dictation-btn px-4 py-2 border-2 border-[#4F46E5] text-[#4F46E5] rounded-lg hover:bg-[#4F46E5] hover:text-white transition-all" data-count="30">30个单词</button>
                        </div>
                        <div id="dictation-area" class="hidden">
                            <div class="flex justify-between items-center mb-4">
                                <h4 class="font-semibold">当前进度：<span id="dictation-progress">0/0</span></h4>
                                <button id="play-dictation-word" class="text-[#10B981] hover:text-opacity-80 transition-all">
                                    <i class="fa fa-volume-up text-2xl"></i>
                                </button>
                            </div>
                            <input id="dictation-input" type="text" class="input-primary w-full mb-4" placeholder="请输入你听到的单词...">
                            <div class="flex gap-4">
                                <button id="check-dictation" class="btn-accent">检查答案</button>
                                <button id="next-dictation" class="btn-primary hidden">下一个</button>
                            </div>
                            <div id="dictation-result" class="mt-4 hidden">
                                <div id="dictation-correct" class="hidden">
                                    <p class="text-[#10B981] font-semibold"><i class="fa fa-check-circle mr-2"></i> 正确！</p>
                                </div>
                                <div id="dictation-wrong" class="hidden">
                                    <p class="text-red-500 font-semibold"><i class="fa fa-times-circle mr-2"></i> 错误</p>
                                    <p>正确答案：<span id="dictation-correct-answer" class="font-semibold"></span></p>
                                </div>
                            </div>
                            <div id="dictation-summary" class="mt-6 hidden">
                                <h4 class="font-bold text-lg mb-2">练习完成！</h4>
                                <p>正确率：<span id="dictation-accuracy" class="font-semibold text-[#4F46E5]"></span></p>
                                <button id="restart-dictation" class="btn-primary mt-4">重新开始</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        const animals = {
            cat: {
                name: "语语",
                image: "https://p11-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/1686b166e6c046acbb09e90843dcbddf~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=vBoICUN7ybD456lDpyADIhfPy1E%3D",
                greetings: ["你好！我是语语，很高兴成为你的英语学习伙伴！","让我们一起学习英语吧！","输入一个单词，开始我们的学习之旅！"]
            },
            dog: {
                name: "旺旺",
                image: "https://p11-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/78e1e263807b4060891ef3c24f4f3955~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=rKjHHxHRAD51w9cqBX8M5dRbnU8%3D",
                greetings: ["汪汪！我是旺旺，你的英语学习伙伴！","准备好学习英语了吗？","输入单词，我们一起学习吧！"]
            },
            rabbit: {
                name: "跳跳",
                image: "https://p6-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/a62a49f6497848e78ffcaced9c2ea5d6~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247882&x-signature=srhf%2FAtdcjOvgXaq5AcUIVJTi3E%3D",
                greetings: ["大家好！我是跳跳，很高兴认识你！","让我们一起快乐学习英语吧！","输入单词开始学习吧！"]
            },
            panda: {
                name: "盼盼",
                image: "https://p26-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/rc/pc/super_tool/30d09d3445244ef796892a67a4014469~tplv-a9rns2rl98-image.image?lk3s=8e244e95&rcl=202604082144195267D366128EDE0FC5A1&rrcfp=f06b921b&x-expires=1778247886&x-signature=pEUZ7vHOAlF1FK3Wj%2FuKOl98l2M%3D",
                greetings: ["你好！我是盼盼，你的英语学习伙伴！","让我们一起学习英语吧！","输入单词，开始学习！"]
            }
        };

        const wordDictionary = {
            "access": "v. 获取 n. 接近，入口",
            "project": "n. 工程；课题、作业",
            "intention": "n. 打算，意图",
            "equivalence": "n. 等值，相等",
            "negotiate": "v. 谈判，协商，交涉",
            "disappointing": "adj. 令人失望的",
            "alternative": "n. 代替品",
            "generous": "adj. 慷慨的",
            "administration": "n. 管理；管理部门",
            "skillful": "adj. 灵巧的，娴熟的",
            "data": "n. 数据；资料",
            "pollution": "n. 污染",
            "possession": "n. 有，所有；占有物",
            "manly": "adj. 男子气概的，果断的",
            "reverse": "v. 颠倒；翻转 n. 背面",
            "giant": "adj. 巨大的 n. 巨人，巨物；才智超群的人",
            "arbitrary": "adj. 随心所欲的， 专断的",
            "fearful": "adj. 害怕的， 可怕的； 不安的， 忧虑的",
            "accent": "n. 口音， 腔调； 重音",
            "passive": "adj. 被动的， 消极的",
            "fertilizer": "n. 肥料",
            "lorry": "n. 运货汽车， 卡车",
            "carrier": "n. 运输工具， 运载工具； 带菌者； 载重架， 置物架",
            "fragment": "v. 成碎片 n. 碎片，破片，碎块",
            "corresponding": "adj. 相应的， 符合的",
            "response": "n. 回答， 答复； 反应， 响应",
            "treaty": "n. 条约， 协议， 协定",
            "responsive": "adj. 响应的； 敏感的， 易受影响的",
            "ounce": "n. 盎司",
            "biological": "adj. 生物的",
            "strategy": "n. 策略，战略",
            "paradox": "n. 悖论；自相矛盾",
            "primary": "adj. 主要的，基本的",
            "standpoint": "n. 立场",
            "grab": "v. 抢先，抢占，抢夺",
            "crucial": "adj. 至关重要的",
            "flaw": "n. 缺点；错误",
            "depressed": "adj. 萧条的；沮丧的",
            "obstacle": "n. 阻碍"
        };

        const englishWords = Object.keys(wordDictionary);

        let currentState = {
            selectedAnimal: null,
            currentWord: null,
            practiceWord: "",
            recording: false,
            recognition: null,
            targetWordCache: null,
            dictationWords: [],
            currentDictationIndex: 0,
            dictationCorrectCount: 0,
            manualStop: false,        // 是否手动点击停止
        };

        // DOM 元素引用
        const welcomeScreen = document.getElementById('welcome-screen');
        const learningScreen = document.getElementById('learning-screen');
        const animalCards = document.querySelectorAll('.animal-card');
        const backBtn = document.getElementById('back-btn');
        const selectedAnimal = document.getElementById('selected-animal');
        const animalSpeechBubble = document.getElementById('animal-speech-bubble');
        const wordInput = document.getElementById('word-input');
        const searchBtn = document.getElementById('search-btn');
        const wordResult = document.getElementById('word-result');
        const wordTitle = document.getElementById('word-title');
        const wordPhonetic = document.getElementById('word-phonetic');
        const wordMeanings = document.getElementById('word-meanings');
        const playPronunciation = document.getElementById('play-pronunciation');
        const practiceWordInput = document.getElementById('practice-word-input');
        const startRecording = document.getElementById('start-recording');
        const stopRecording = document.getElementById('stop-recording');
        const recordingStatus = document.getElementById('recording-status');
        const pronunciationResult = document.getElementById('pronunciation-result');
        const pronunciationScore = document.getElementById('pronunciation-score');
        const scoreBar = document.getElementById('score-bar');
        const pronunciationFeedback = document.getElementById('pronunciation-feedback');
        const listenBtn = document.getElementById('listen-btn');
        const dictationBtns = document.querySelectorAll('.dictation-btn');
        const dictationArea = document.getElementById('dictation-area');
        const dictationProgress = document.getElementById('dictation-progress');
        const playDictationWord = document.getElementById('play-dictation-word');
        const dictationInput = document.getElementById('dictation-input');
        const checkDictation = document.getElementById('check-dictation');
        const nextDictation = document.getElementById('next-dictation');
        const dictationResult = document.getElementById('dictation-result');
        const dictationCorrect = document.getElementById('dictation-correct');
        const dictationWrong = document.getElementById('dictation-wrong');
        const dictationCorrectAnswer = document.getElementById('dictation-correct-answer');
        const dictationSummary = document.getElementById('dictation-summary');
        const dictationAccuracy = document.getElementById('dictation-accuracy');
        const restartDictation = document.getElementById('restart-dictation');

        function init() {
            // 动物选择
            animalCards.forEach(card => {
                card.addEventListener('click', () => selectAnimal(card.dataset.animal));
            });
            backBtn.addEventListener('click', showWelcomeScreen);

            // 单词查询
            searchBtn.addEventListener('click', () => {
                const word = wordInput.value.trim();
                if (word) searchWord(word);
            });
            wordInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    const word = wordInput.value.trim();
                    if (word) searchWord(word);
                }
            });
            playPronunciation.addEventListener('click', () => {
                if (currentState.currentWord) playWordPronunciation(currentState.currentWord);
                else showAnimalMessage("请先在“单词学习”中查询一个单词。");
            });

            // 发音练习输入同步
            practiceWordInput.addEventListener('input', () => {
                currentState.practiceWord = practiceWordInput.value.trim();
            });

            // 录音按钮
            startRecording.addEventListener('click', startPronunciationRecording);
            stopRecording.addEventListener('click', () => {
                currentState.manualStop = true;
                stopPronunciationRecording();
            });

            // 听写练习
            dictationBtns.forEach(btn => {
                btn.addEventListener('click', () => startDictation(parseInt(btn.dataset.count)));
            });
            playDictationWord.addEventListener('click', () => {
                if (currentState.dictationWords.length > 0 &&
                    currentState.currentDictationIndex < currentState.dictationWords.length) {
                    speakText(currentState.dictationWords[currentState.currentDictationIndex]);
                }
            });
            checkDictation.addEventListener('click', checkDictationAnswer);
            nextDictation.addEventListener('click', nextDictationWord);
            restartDictation.addEventListener('click', () => startDictation(currentState.dictationWords.length));
            listenBtn.addEventListener('click', () => {
                if (animalSpeechBubble.textContent) speakText(animalSpeechBubble.textContent);
            });

            // 初始化语音识别（并请求麦克风权限）
            initSpeechRecognition();
        }

        function selectAnimal(animalType) {
            currentState.selectedAnimal = animalType;
            const animal = animals[animalType];
            selectedAnimal.innerHTML = `<img src="${animal.image}" alt="${animal.name}" class="w-full h-full object-contain">`;
            const randomGreeting = animal.greetings[Math.floor(Math.random() * animal.greetings.length)];
            showAnimalMessage(randomGreeting);
            showLearningScreen();
            currentState.practiceWord = "";
            practiceWordInput.value = "";
        }

        function showWelcomeScreen() {
            welcomeScreen.classList.remove('hidden');
            learningScreen.classList.add('hidden');
            currentState.selectedAnimal = null;
            currentState.currentWord = null;
            currentState.practiceWord = "";
            resetWordResult();
            resetPronunciationResult();
            resetDictationArea();
        }

        function showLearningScreen() {
            welcomeScreen.classList.add('hidden');
            learningScreen.classList.remove('hidden');
        }

        function showAnimalMessage(message) {
            animalSpeechBubble.textContent = message;
        }

        function searchWord(word) {
            const inputWord = word.trim().toLowerCase();
            currentState.currentWord = { word: inputWord };
            if (wordDictionary[inputWord]) {
                wordTitle.textContent = inputWord;
                wordPhonetic.classList.add('hidden');
                wordMeanings.innerHTML = `
                    <div class="mb-2">
                        <h5 class="font-semibold text-[#4F46E5]">中文释义</h5>
                        <p class="pl-1 mt-1">${wordDictionary[inputWord]}</p>
                    </div>`;
                wordResult.classList.remove('hidden');
                showAnimalMessage(`"${inputWord}" 的意思是：${wordDictionary[inputWord]}`);
            } else {
                showAnimalMessage(`词库里没有"${word}"，但你可以用发音练习来学习它！`);
                resetWordResult();
                currentState.currentWord = null;
            }
        }

        function resetWordResult() {
            wordResult.classList.add('hidden');
            wordTitle.textContent = '';
            wordPhonetic.textContent = '';
            wordMeanings.innerHTML = '';
        }

        function playWordPronunciation(wordData) {
            speakText(wordData.word);
        }

        function speakText(text) {
            if (!('speechSynthesis' in window)) return;
            window.speechSynthesis.cancel();
            const utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = 'en-US';
            utterance.rate = 0.9;
            utterance.pitch = 1;
            const setVoice = () => {
                const voices = window.speechSynthesis.getVoices();
                const enVoice = voices.find(v => v.lang.startsWith('en'));
                if (enVoice) utterance.voice = enVoice;
                window.speechSynthesis.speak(utterance);
            };
            if (window.speechSynthesis.getVoices().length === 0) {
                window.speechSynthesis.onvoiceschanged = setVoice;
            } else {
                setVoice();
            }
        }

        function initSpeechRecognition() {
            const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
            if (!SpeechRecognition) {
                startRecording.disabled = true;
                showAnimalMessage("您的浏览器不支持语音识别，请使用最新版Chrome。");
                return;
            }

            // 预请求麦克风权限
            if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
                navigator.mediaDevices.getUserMedia({ audio: true })
                    .then(() => console.log('麦克风权限已获取'))
                    .catch(err => {
                        startRecording.disabled = true;
                        showAnimalMessage("请允许麦克风权限才能使用录音功能。");
                        console.error('麦克风权限被拒绝', err);
                    });
            }

            const recognition = new SpeechRecognition();
            recognition.continuous = false;   // 单次识别
            recognition.interimResults = false;
            recognition.lang = 'en-US';

            recognition.onresult = (event) => {
                const transcript = event.results[0][0].transcript.trim();
                evaluatePronunciation(transcript);
            };

            // 关键修复：区分不同类型的错误
            recognition.onerror = (event) => {
                console.error('Speech recognition error:', event.error);
                if (event.error === 'no-speech') {
                    // 没有检测到语音，不做任何事，等待 onend 自动重启
                    return;
                }
                if (event.error === 'aborted') {
                    // 通常由手动停止引起，忽略
                    return;
                }
                // 其他错误（如 not-allowed, network 等）才停止
                stopPronunciationRecording();
                if (event.error === 'not-allowed' || event.error === 'service-not-allowed') {
                    showAnimalMessage("麦克风权限被拒绝，请在浏览器设置中允许。");
                } else {
                    showAnimalMessage("语音识别出错，请重试。");
                }
            };

            recognition.onend = () => {
                // 如果还在录音状态，并且不是手动停止，自动重新开始监听
                if (currentState.recording && !currentState.manualStop) {
                    try {
                        recognition.start();
                    } catch (e) {
                        stopPronunciationRecording();
                    }
                }
            };

            currentState.recognition = recognition;
        }

        function getTargetWord() {
            if (currentState.practiceWord) return currentState.practiceWord;
            if (currentState.currentWord) return currentState.currentWord.word;
            return null;
        }

        function startPronunciationRecording() {
            const recognition = currentState.recognition;
            if (!recognition) {
                showAnimalMessage("语音识别功能不可用。");
                return;
            }

            const targetWord = getTargetWord();
            if (!targetWord) {
                showAnimalMessage("请先在“发音练习”输入框中输入单词，或在“单词学习”中查询。");
                return;
            }

            // 缓存目标单词
            currentState.targetWordCache = targetWord;
            currentState.manualStop = false;   // 重置手动停止标志

            // 朗读标准发音
            speakText(targetWord);

            resetPronunciationResult();
            currentState.recording = true;
            startRecording.classList.add('hidden');
            stopRecording.classList.remove('hidden');
            recordingStatus.classList.remove('hidden');

            try {
                recognition.start();
            } catch (error) {
                console.error(error);
                stopPronunciationRecording();
            }
        }

        function stopPronunciationRecording() {
            const recognition = currentState.recognition;
            if (!recognition) return;
            currentState.recording = false;
            startRecording.classList.remove('hidden');
            stopRecording.classList.add('hidden');
            recordingStatus.classList.add('hidden');
            try {
                recognition.stop();
            } catch (error) {
                console.error('停止录音出错:', error);
            }
        }

        function evaluatePronunciation(transcript) {
            stopPronunciationRecording();
            const targetWord = currentState.targetWordCache || getTargetWord();
            if (!targetWord) return;

            const target = targetWord.toLowerCase();
            const user = transcript.toLowerCase();

            let score = calculateSimilarity(target, user);
            score = Math.max(0, Math.min(100, score));

            pronunciationScore.textContent = `${Math.round(score)}%`;
            scoreBar.style.width = `${score}%`;

            if (score >= 80) {
                scoreBar.className = 'bg-[#10B981] h-2.5 rounded-full';
                pronunciationFeedback.textContent = "太棒了！发音非常准确！";
                pronunciationFeedback.className = 'mt-2 text-sm text-[#10B981]';
                showAnimalMessage("你的发音太标准了！继续加油！");
            } else if (score >= 60) {
                scoreBar.className = 'bg-yellow-500 h-2.5 rounded-full';
                pronunciationFeedback.textContent = "不错！发音基本准确，继续练习。";
                pronunciationFeedback.className = 'mt-2 text-sm text-yellow-500';
                showAnimalMessage("还不错，再练习一下就更好了！");
            } else {
                scoreBar.className = 'bg-red-500 h-2.5 rounded-full';
                pronunciationFeedback.textContent = "需要继续练习，注意每个音节。";
                pronunciationFeedback.className = 'mt-2 text-sm text-red-500';
                showAnimalMessage("别灰心，多听多读就能进步！");
            }
            pronunciationResult.classList.remove('hidden');
        }

        function calculateSimilarity(str1, str2) {
            if (str1 === str2) return 100;
            if (str2.includes(str1)) return 85;
            if (str1.includes(str2)) return 75;
            const distance = levenshteinDistance(str1, str2);
            const maxLength = Math.max(str1.length, str2.length);
            return Math.max(0, 100 - (distance / maxLength) * 100);
        }

        function levenshteinDistance(a, b) {
            const matrix = [];
            for (let i = 0; i <= b.length; i++) matrix[i] = [i];
            for (let j = 0; j <= a.length; j++) matrix[0][j] = j;
            for (let i = 1; i <= b.length; i++) {
                for (let j = 1; j <= a.length; j++) {
                    if (b.charAt(i - 1) === a.charAt(j - 1)) {
                        matrix[i][j] = matrix[i - 1][j - 1];
                    } else {
                        matrix[i][j] = Math.min(
                            matrix[i - 1][j - 1] + 1,
                            matrix[i][j - 1] + 1,
                            matrix[i - 1][j] + 1
                        );
                    }
                }
            }
            return matrix[b.length][a.length];
        }

        function resetPronunciationResult() {
            pronunciationResult.classList.add('hidden');
            pronunciationScore.textContent = '';
            scoreBar.style.width = '0%';
            pronunciationFeedback.textContent = '';
        }

        // 听写练习函数（不变）
        function startDictation(count) {
            currentState.dictationWords = getRandomWords(count);
            currentState.currentDictationIndex = 0;
            currentState.dictationCorrectCount = 0;
            dictationArea.classList.remove('hidden');
            dictationResult.classList.add('hidden');
            dictationSummary.classList.add('hidden');
            checkDictation.classList.remove('hidden');
            nextDictation.classList.add('hidden');
            updateDictationProgress();
            playCurrentDictationWord();
            dictationInput.value = '';
            showAnimalMessage(`听写练习开始！我们将练习${count}个单词。点击喇叭图标听发音！`);
        }

        function getRandomWords(count) {
            const shuffled = [...englishWords].sort(() => 0.5 - Math.random());
            return shuffled.slice(0, count);
        }

        function updateDictationProgress() {
            dictationProgress.textContent = `${currentState.currentDictationIndex + 1}/${currentState.dictationWords.length}`;
        }

        function playCurrentDictationWord() {
            if (currentState.dictationWords.length > 0 &&
                currentState.currentDictationIndex < currentState.dictationWords.length) {
                speakText(currentState.dictationWords[currentState.currentDictationIndex]);
            }
        }

        function checkDictationAnswer() {
            const userAnswer = dictationInput.value.trim().toLowerCase();
            const correctAnswer = currentState.dictationWords[currentState.currentDictationIndex].toLowerCase();
            dictationResult.classList.remove('hidden');
            checkDictation.classList.add('hidden');
            nextDictation.classList.remove('hidden');
            if (userAnswer === correctAnswer) {
                dictationCorrect.classList.remove('hidden');
                dictationWrong.classList.add('hidden');
                currentState.dictationCorrectCount++;
            } else {
                dictationCorrect.classList.add('hidden');
                dictationWrong.classList.remove('hidden');
                dictationCorrectAnswer.textContent = correctAnswer;
            }
        }

        function nextDictationWord() {
            currentState.currentDictationIndex++;
            dictationResult.classList.add('hidden');
            checkDictation.classList.remove('hidden');
            nextDictation.classList.add('hidden');
            dictationInput.value = '';
            if (currentState.currentDictationIndex >= currentState.dictationWords.length) {
                showDictationSummary();
            } else {
                updateDictationProgress();
                playCurrentDictationWord();
                showAnimalMessage("下一个单词！点击喇叭图标听发音！");
            }
        }

        function showDictationSummary() {
            const accuracy = Math.round((currentState.dictationCorrectCount / currentState.dictationWords.length) * 100);
            dictationAccuracy.textContent = `${accuracy}% (${currentState.dictationCorrectCount}/${currentState.dictationWords.length})`;
            dictationSummary.classList.remove('hidden');
            checkDictation.classList.add('hidden');
            nextDictation.classList.add('hidden');
        }

        function resetDictationArea() {
            dictationArea.classList.add('hidden');
            dictationResult.classList.add('hidden');
            dictationSummary.classList.add('hidden');
            checkDictation.classList.remove('hidden');
            nextDictation.classList.add('hidden');
            dictationInput.value = '';
        }

        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
