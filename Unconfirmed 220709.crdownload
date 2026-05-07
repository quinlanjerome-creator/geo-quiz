/* ========================================
   GEOGRAPHY QUEST - PREMIUM EDITION
   Main Application JavaScript
   ======================================== */

// ============================================
// CONFIGURATION & CONSTANTS
// ============================================

const CONFIG = {
    questionsPerLevel: 5,
    totalLevels: 5,
    basePoints: 10,
    streakBonus: 5,
    timeBonusMultiplier: 0.5,
    difficulties: {
        easy: { time: 90, lives: 5 },
        medium: { time: 60, lives: 3 },
        hard: { time: 45, lives: 2 }
    },
    // Replace with your Google Apps Script Web App URL
    googleScriptURL: 'YOUR_GOOGLE_APPS_SCRIPT_URL_HERE'
};

// ============================================
// QUESTION DATABASE
// ============================================

const QUESTIONS = {
    // Level 1 - Easy
    1: [
        {
            category: "Capitals",
            question: "What is the capital of France?",
            answers: ["Paris", "London", "Berlin", "Madrid"],
            correct: 0,
            points: 10
        },
        {
            category: "Capitals",
            question: "What is the capital of Japan?",
            answers: ["Seoul", "Beijing", "Tokyo", "Bangkok"],
            correct: 2,
            points: 10
        },
        {
            category: "Continents",
            question: "Which continent is Brazil located in?",
            answers: ["Africa", "South America", "Europe", "Asia"],
            correct: 1,
            points: 10
        },
        {
            category: "Countries",
            question: "Which country is known as the Land of the Rising Sun?",
            answers: ["China", "South Korea", "Japan", "Thailand"],
            correct: 2,
            points: 10
        },
        {
            category: "Landmarks",
            question: "In which country is the Eiffel Tower located?",
            answers: ["Italy", "Spain", "France", "Germany"],
            correct: 2,
            points: 10
        },
        {
            category: "Capitals",
            question: "What is the capital of Australia?",
            answers: ["Sydney", "Melbourne", "Canberra", "Perth"],
            correct: 2,
            points: 10
        },
        {
            category: "Oceans",
            question: "Which is the largest ocean on Earth?",
            answers: ["Atlantic", "Indian", "Arctic", "Pacific"],
            correct: 3,
            points: 10
        },
        {
            category: "Countries",
            question: "Which country has the largest population?",
            answers: ["USA", "India", "China", "Indonesia"],
            correct: 2,
            points: 10
        }
    ],
    // Level 2 - Medium Easy
    2: [
        {
            category: "Rivers",
            question: "Which is the longest river in the world?",
            answers: ["Amazon", "Nile", "Yangtze", "Mississippi"],
            correct: 1,
            points: 15
        },
        {
            category: "Mountains",
            question: "What is the highest mountain in the world?",
            answers: ["K2", "Kangchenjunga", "Mount Everest", "Lhotse"],
            correct: 2,
            points: 15
        },
        {
            category: "Capitals",
            question: "What is the capital of Canada?",
            answers: ["Toronto", "Vancouver", "Montreal", "Ottawa"],
            correct: 3,
            points: 15
        },
        {
            category: "Countries",
            question: "Which country is both in Europe and Asia?",
            answers: ["Russia", "Turkey", "Kazakhstan", "All of these"],
            correct: 3,
            points: 15
        },
        {
            category: "Islands",
            question: "Which is the largest island in the world?",
            answers: ["Borneo", "Madagascar", "Greenland", "New Guinea"],
            correct: 2,
            points: 15
        },
        {
            category: "Deserts",
            question: "Which is the largest hot desert in the world?",
            answers: ["Gobi", "Kalahari", "Sahara", "Arabian"],
            correct: 2,
            points: 15
        },
        {
            category: "Lakes",
            question: "Which is the deepest lake in the world?",
            answers: ["Lake Superior", "Lake Baikal", "Lake Victoria", "Caspian Sea"],
            correct: 1,
            points: 15
        },
        {
            category: "Countries",
            question: "Which country has the most time zones?",
            answers: ["Russia", "USA", "China", "France"],
            correct: 3,
            points: 15
        }
    ],
    // Level 3 - Medium
    3: [
        {
            category: "Capitals",
            question: "What is the capital of New Zealand?",
            answers: ["Auckland", "Wellington", "Christchurch", "Hamilton"],
            correct: 1,
            points: 20
        },
        {
            category: "Geography",
            question: "Which strait separates Europe from Africa?",
            answers: ["Bering Strait", "Strait of Gibraltar", "Strait of Hormuz", "Malacca Strait"],
            correct: 1,
            points: 20
        },
        {
            category: "Countries",
            question: "Which landlocked country is surrounded by only one country?",
            answers: ["Vatican City", "San Marino", "Lesotho", "Both B and C"],
            correct: 3,
            points: 20
        },
        {
            category: "Mountains",
            question: "In which mountain range is Mount Everest located?",
            answers: ["Alps", "Andes", "Himalayas", "Rocky Mountains"],
            correct: 2,
            points: 20
        },
        {
            category: "Countries",
            question: "Which country has the longest coastline?",
            answers: ["Russia", "Indonesia", "Canada", "Australia"],
            correct: 2,
            points: 20
        },
        {
            category: "Cities",
            question: "Which city is located on two continents?",
            answers: ["Cairo", "Istanbul", "Moscow", "Dubai"],
            correct: 1,
            points: 20
        },
        {
            category: "Rivers",
            question: "Through how many countries does the Danube River flow?",
            answers: ["5", "7", "10", "12"],
            correct: 2,
            points: 20
        },
        {
            category: "Flags",
            question: "Which country's flag has a dragon on it?",
            answers: ["China", "Wales", "Bhutan", "Both B and C"],
            correct: 3,
            points: 20
        }
    ],
    // Level 4 - Medium Hard
    4: [
        {
            category: "Capitals",
            question: "What is the capital of Myanmar?",
            answers: ["Yangon", "Mandalay", "Naypyidaw", "Bago"],
            correct: 2,
            points: 25
        },
        {
            category: "Geography",
            question: "Which African country was formerly known as Abyssinia?",
            answers: ["Sudan", "Ethiopia", "Somalia", "Eritrea"],
            correct: 1,
            points: 25
        },
        {
            category: "Islands",
            question: "Which country owns the Galápagos Islands?",
            answers: ["Peru", "Colombia", "Ecuador", "Chile"],
            correct: 2,
            points: 25
        },
        {
            category: "Mountains",
            question: "What is the highest mountain in Africa?",
            answers: ["Mount Kenya", "Mount Kilimanjaro", "Atlas Mountains", "Simien Mountains"],
            correct: 1,
            points: 25
        },
        {
            category: "Countries",
            question: "Which is the smallest country in Asia by area?",
            answers: ["Bahrain", "Singapore", "Maldives", "Brunei"],
            correct: 2,
            points: 25
        },
        {
            category: "Rivers",
            question: "Which river flows through the Grand Canyon?",
            answers: ["Missouri River", "Colorado River", "Rio Grande", "Columbia River"],
            correct: 1,
            points: 25
        },
        {
            category: "Seas",
            question: "Which sea is the saltiest in the world?",
            answers: ["Red Sea", "Mediterranean Sea", "Dead Sea", "Caspian Sea"],
            correct: 2,
            points: 25
        },
        {
            category: "Borders",
            question: "Which two countries share the longest international border?",
            answers: ["USA & Mexico", "Russia & China", "USA & Canada", "Argentina & Chile"],
            correct: 2,
            points: 25
        }
    ],
    // Level 5 - Hard
    5: [
        {
            category: "Capitals",
            question: "What is the capital of Liechtenstein?",
            answers: ["Schaan", "Vaduz", "Triesen", "Balzers"],
            correct: 1,
            points: 30
        },
        {
            category: "Geography",
            question: "Which country has the most islands?",
            answers: ["Indonesia", "Philippines", "Sweden", "Finland"],
            correct: 2,
            points: 30
        },
        {
            category: "Mountains",
            question: "What is the highest mountain in South America?",
            answers: ["Mount Chimborazo", "Aconcagua", "Cotopaxi", "Huascarán"],
            correct: 1,
            points: 30
        },
        {
            category: "Countries",
            question: "Which country is the newest UN member state?",
            answers: ["Montenegro", "South Sudan", "Kosovo", "East Timor"],
            correct: 1,
            points: 30
        },
        {
            category: "Lakes",
            question: "Lake Titicaca is on the border of which two countries?",
            answers: ["Chile & Argentina", "Peru & Bolivia", "Ecuador & Colombia", "Brazil & Paraguay"],
            correct: 1,
            points: 30
        },
        {
            category: "Geography",
            question: "What is the driest place on Earth?",
            answers: ["Sahara Desert", "Atacama Desert", "Death Valley", "McMurdo Dry Valleys"],
            correct: 3,
            points: 30
        },
        {
            category: "Volcanoes",
            question: "Which volcano destroyed the city of Pompeii?",
            answers: ["Mount Etna", "Mount Vesuvius", "Stromboli", "Mount Vulcano"],
            correct: 1,
            points: 30
        },
        {
            category: "Countries",
            question: "Which country is completely surrounded by South Africa?",
            answers: ["Swaziland", "Lesotho", "Botswana", "Zimbabwe"],
            correct: 1,
            points: 30
        }
    ]
};

// ============================================
// GAME STATE
// ============================================

let gameState = {
    playerName: '',
    difficulty: 'medium',
    currentLevel: 1,
    currentQuestion: 0,
    score: 0,
    lives: 3,
    timeLeft: 60,
    streak: 0,
    maxStreak: 0,
    correctAnswers: 0,
    totalQuestions: 0,
    totalPossibleScore: 0,
    timerInterval: null,
    isPaused: false,
    levelQuestions: [],
    powerups: {
        fiftyFifty: 2,
        skip: 1,
        extraTime: 1
    },
    levelStartTime: 0,
    answered: false
};

// ============================================
// DOM ELEMENTS
// ============================================

const DOM = {
    // Screens
    startScreen: document.getElementById('start-screen'),
    gameScreen: document.getElementById('game-screen'),
    levelCompleteScreen: document.getElementById('level-complete-screen'),
    gameoverScreen: document.getElementById('gameover-screen'),
    
    // Start Screen
    playerNameInput: document.getElementById('player-name'),
    startBtn: document.getElementById('start-btn'),
    difficultyBtns: document.querySelectorAll('.diff-btn'),
    
    // Game Screen
    displayName: document.getElementById('display-name'),
    currentLevel: document.getElementById('current-level'),
    score: document.getElementById('score'),
    lives: document.getElementById('lives'),
    timer: document.getElementById('timer'),
    streak: document.getElementById('streak'),
    progressFill: document.getElementById('progress-fill'),
    progressText: document.getElementById('progress-text'),
    questionCategory: document.getElementById('question-category'),
    questionPoints: document.getElementById('question-points'),
    questionText: document.getElementById('question-text'),
    questionImageContainer: document.getElementById('question-image-container'),
    questionImage: document.getElementById('question-image'),
    answersContainer: document.getElementById('answers-container'),
    feedback: document.getElementById('feedback'),
    pauseBtn: document.getElementById('pause-btn'),
    
    // Power-ups
    powerup5050: document.getElementById('powerup-5050'),
    powerupSkip: document.getElementById('powerup-skip'),
    powerupTime: document.getElementById('powerup-time'),
    
    // Level Complete
    completedLevel: document.getElementById('completed-level'),
    levelScore: document.getElementById('level-score'),
    levelAccuracy: document.getElementById('level-accuracy'),
    levelTime: document.getElementById('level-time'),
    timeBonus: document.getElementById('time-bonus'),
    nextLevelBtn: document.getElementById('next-level-btn'),
    
    // Game Over
    resultsEmoji: document.getElementById('results-emoji'),
    resultsTitle: document.getElementById('results-title'),
    finalScore: document.getElementById('final-score'),
    scoreBreakdown: document.getElementById('score-breakdown'),
    finalPercentage: document.getElementById('final-percentage'),
    correctAnswersEl: document.getElementById('correct-answers'),
    maxStreakEl: document.getElementById('max-streak'),
    levelReached: document.getElementById('level-reached'),
    grade: document.getElementById('grade'),
    retryBtn: document.getElementById('retry-btn'),
    homeBtn: document.getElementById('home-btn'),
    
    // Modal
    pauseModal: document.getElementById('pause-modal'),
    pauseScore: document.getElementById('pause-score'),
    pauseLevel: document.getElementById('pause-level'),
    resumeBtn: document.getElementById('resume-btn'),
    quitBtn: document.getElementById('quit-btn'),
    
    // Toast
    toastContainer: document.getElementById('toast-container')
};

// ============================================
// UTILITY FUNCTIONS
// ============================================

/**
 * Shuffle array using Fisher-Yates algorithm
 */
function shuffleArray(array) {
    const shuffled = [...array];
    for (let i = shuffled.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
    }
    return shuffled;
}

/**
 * Show a specific screen and hide others
 */
function showScreen(screenId) {
    document.querySelectorAll('.screen').forEach(screen => {
        screen.classList.remove('active');
    });
    document.getElementById(screenId).classList.add('active');
}

/**
 * Display a toast notification
 */
function showToast(message, type = 'info') {
    const toast = document.createElement('div');
    toast.className = `toast ${type}`;
    toast.innerHTML = `<span>${message}</span>`;
    DOM.toastContainer.appendChild(toast);
    
    setTimeout(() => {
        toast.style.animation = 'slideInRight 0.3s ease reverse';
        setTimeout(() => toast.remove(), 300);
    }, 3000);
}

/**
 * Calculate grade based on percentage
 */
function calculateGrade(percentage) {
    if (percentage >= 90) return 'A+';
    if (percentage >= 80) return 'A';
    if (percentage >= 70) return 'B';
    if (percentage >= 60) return 'C';
    if (percentage >= 50) return 'D';
    return 'F';
}

/**
 * Get results title and emoji based on performance
 */
function getResultsFeedback(percentage) {
    if (percentage >= 90) return { emoji: '🏆', title: 'Geography Master!' };
    if (percentage >= 80) return { emoji: '🌟', title: 'Excellent Work!' };
    if (percentage >= 70) return { emoji: '👏', title: 'Great Job!' };
    if (percentage >= 60) return { emoji: '👍', title: 'Good Effort!' };
    if (percentage >= 50) return { emoji: '📚', title: 'Keep Learning!' };
    return { emoji: '💪', title: 'Don\'t Give Up!' };
}

// ============================================
// GAME LOGIC
// ============================================

/**
 * Initialize the game
 */
function initGame() {
    setupEventListeners();
}

/**
 * Set up all event listeners
 */
function setupEventListeners() {
    // Start button
    DOM.startBtn.addEventListener('click', startGame);
    
    // Enter key on name input
    DOM.playerNameInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') startGame();
    });
    
    // Difficulty buttons
    DOM.difficultyBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            DOM.difficultyBtns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            gameState.difficulty = btn.dataset.difficulty;
        });
    });
    
    // Pause button
    DOM.pauseBtn.addEventListener('click', pauseGame);
    
    // Modal buttons
    DOM.resumeBtn.addEventListener('click', resumeGame);
    DOM.quitBtn.addEventListener('click', quitGame);
    
    // Power-up buttons
    DOM.powerup5050.addEventListener('click', useFiftyFifty);
    DOM.powerupSkip.addEventListener('click', useSkip);
    DOM.powerupTime.addEventListener('click', useExtraTime);
    
    // Next level button
    DOM.nextLevelBtn.addEventListener('click', startNextLevel);
    
    // Game over buttons
    DOM.retryBtn.addEventListener('click', restartGame);
    DOM.homeBtn.addEventListener('click', goHome);
    
    // Close modal on overlay click
    document.querySelector('.modal-overlay')?.addEventListener('click', resumeGame);
}

/**
 * Start the game
 */
function startGame() {
    const name = DOM.playerNameInput.value.trim();
    
    if (!name) {
        showToast('Please enter your name to start!', 'error');
        DOM.playerNameInput.focus();
        return;
    }
    
    // Reset game state
    const diffSettings = CONFIG.difficulties[gameState.difficulty];
    gameState = {
        ...gameState,
        playerName: name,
        currentLevel: 1,
        currentQuestion: 0,
        score: 0,
        lives: diffSettings.lives,
        timeLeft: diffSettings.time,
        streak: 0,
        maxStreak: 0,
        correctAnswers: 0,
        totalQuestions: 0,
        totalPossibleScore: 0,
        timerInterval: null,
        isPaused: false,
        levelQuestions: [],
        powerups: {
            fiftyFifty: 2,
            skip: 1,
            extraTime: 1
        },
        answered: false
    };
    
    // Update UI
    DOM.displayName.textContent = name;
    updatePowerupUI();
    
    // Start first level
    startLevel();
    showScreen('game-screen');
}

/**
 * Start a new level
 */
function startLevel() {
    // Get and shuffle questions for this level
    const levelQuestions = QUESTIONS[gameState.currentLevel] || QUESTIONS[1];
    gameState.levelQuestions = shuffleArray(levelQuestions).slice(0, CONFIG.questionsPerLevel);
    gameState.currentQuestion = 0;
    gameState.answered = false;
    gameState.levelStartTime = Date.now();
    
    // Calculate total possible score for this level
    gameState.levelQuestions.forEach(q => {
        gameState.totalPossibleScore += q.points;
    });
    
    // Update UI
    DOM.currentLevel.textContent = gameState.currentLevel;
    DOM.score.textContent = gameState.score;
    DOM.lives.textContent = gameState.lives;
    
    // Reset timer based on difficulty
    const diffSettings = CONFIG.difficulties[gameState.difficulty];
    gameState.timeLeft = diffSettings.time;
    DOM.timer.textContent = gameState.timeLeft;
    
    // Start timer
    startTimer();
    
    // Load first question
    loadQuestion();
}

/**
 * Load the current question
 */
function loadQuestion() {
    const question = gameState.levelQuestions[gameState.currentQuestion];
    if (!question) {
        levelComplete();
        return;
    }
    
    gameState.answered = false;
    gameState.totalQuestions++;
    
    // Update question UI
    DOM.questionCategory.textContent = question.category;
    DOM.questionPoints.textContent = `+${question.points} pts`;
    DOM.questionText.textContent = question.question;
    
    // Hide image container (extend this for image-based questions)
    DOM.questionImageContainer.classList.add('hidden');
    
    // Update progress
    const progress = ((gameState.currentQuestion) / CONFIG.questionsPerLevel) * 100;
    DOM.progressFill.style.width = `${progress}%`;
    DOM.progressText.textContent = `Question ${gameState.currentQuestion + 1} of ${CONFIG.questionsPerLevel}`;
    
    // Generate answer buttons
    generateAnswerButtons(question);
    
    // Hide feedback
    DOM.feedback.classList.add('hidden');
}

/**
 * Generate answer buttons with shuffled order
 */
function generateAnswerButtons(question) {
    // Create answer objects with original indices
    const answerObjects = question.answers.map((text, index) => ({
        text,
        originalIndex: index,
        isCorrect: index === question.correct
    }));
    
    // Shuffle answers
    const shuffledAnswers = shuffleArray(answerObjects);
    
    // Store the new correct index
    const newCorrectIndex = shuffledAnswers.findIndex(a => a.isCorrect);
    
    // Generate HTML
    const letters = ['A', 'B', 'C', 'D'];
    DOM.answersContainer.innerHTML = shuffledAnswers.map((answer, index) => `
        <button class="answer-btn" data-index="${index}" data-correct="${answer.isCorrect}">
            <span class="answer-letter">${letters[index]}</span>
            <span class="answer-text">${answer.text}</span>
        </button>
    `).join('');
    
    // Add click listeners
    DOM.answersContainer.querySelectorAll('.answer-btn').forEach(btn => {
        btn.addEventListener('click', () => handleAnswer(btn));
    });
}

/**
 * Handle answer selection
 */
function handleAnswer(button) {
    if (gameState.answered || gameState.isPaused) return;
    
    gameState.answered = true;
    const isCorrect = button.dataset.correct === 'true';
    const question = gameState.levelQuestions[gameState.currentQuestion];
    
    // Disable all buttons
    DOM.answersContainer.querySelectorAll('.answer-btn').forEach(btn => {
        btn.disabled = true;
        if (btn.dataset.correct === 'true') {
            btn.classList.add('correct');
        }
    });
    
    if (isCorrect) {
        // Correct answer
        button.classList.add('correct');
        gameState.score += question.points + (gameState.streak * CONFIG.streakBonus);
        gameState.streak++;
        gameState.maxStreak = Math.max(gameState.maxStreak, gameState.streak);
        gameState.correctAnswers++;
        
        showFeedback(true, `Correct! +${question.points + ((gameState.streak - 1) * CONFIG.streakBonus)} points`);
    } else {
        // Incorrect answer
        button.classList.add('incorrect');
        gameState.streak = 0;
        gameState.lives--;
        
        const correctAnswer = question.answers[question.correct];
        showFeedback(false, `Wrong! The answer was: ${correctAnswer}`);
    }
    
    // Update UI
    DOM.score.textContent = gameState.score;
    DOM.lives.textContent = gameState.lives;
    DOM.streak.textContent = gameState.streak;
    
    // Check for game over
    if (gameState.lives <= 0) {
        setTimeout(() => endGame(), 1500);
        return;
    }
    
    // Move to next question after delay
    setTimeout(() => {
        gameState.currentQuestion++;
        if (gameState.currentQuestion >= CONFIG.questionsPerLevel) {
            levelComplete();
        } else {
            loadQuestion();
        }
    }, 1500);
}

/**
 * Show feedback message
 */
function showFeedback(isCorrect, message) {
    DOM.feedback.classList.remove('hidden', 'correct', 'incorrect');
    DOM.feedback.classList.add(isCorrect ? 'correct' : 'incorrect');
    DOM.feedback.innerHTML = `
        <div class="feedback-content">
            <span class="feedback-icon">${isCorrect ? '✅' : '❌'}</span>
            <span class="feedback-text">${message}</span>
        </div>
    `;
}

/**
 * Timer functions
 */
function startTimer() {
    clearInterval(gameState.timerInterval);
    gameState.timerInterval = setInterval(() => {
        if (gameState.isPaused) return;
        
        gameState.timeLeft--;
        DOM.timer.textContent = gameState.timeLeft;
        
        // Warning state when time is low
        const timerStat = document.querySelector('.stat-timer');
        if (gameState.timeLeft <= 10) {
            timerStat.classList.add('warning');
        } else {
            timerStat.classList.remove('warning');
        }
        
        // Time's up
        if (gameState.timeLeft <= 0) {
            clearInterval(gameState.timerInterval);
            endGame();
        }
    }, 1000);
}

function stopTimer() {
    clearInterval(gameState.timerInterval);
}

/**
 * Level complete
 */
function levelComplete() {
    stopTimer();
    
    // Calculate level stats
    const levelScore = gameState.score;
    const accuracy = Math.round((gameState.correctAnswers / gameState.totalQuestions) * 100);
    const timeBonus = Math.round(gameState.timeLeft * CONFIG.timeBonusMultiplier);
    
    // Add time bonus
    gameState.score += timeBonus;
    
    // Update level complete screen
    DOM.completedLevel.textContent = gameState.currentLevel;
    DOM.levelScore.textContent = levelScore;
    DOM.levelAccuracy.textContent = `${accuracy}%`;
    DOM.levelTime.textContent = `${gameState.timeLeft}s`;
    DOM.timeBonus.textContent = `+${timeBonus}`;
    
    // Check if this is the final level
    if (gameState.currentLevel >= CONFIG.totalLevels) {
        DOM.nextLevelBtn.innerHTML = '<span>View Results</span>';
    } else {
        DOM.nextLevelBtn.innerHTML = `
            <span>Next Level</span>
            <svg class="btn-arrow" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
        `;
    }
    
    showScreen('level-complete-screen');
}

/**
 * Start the next level
 */
function startNextLevel() {
    if (gameState.currentLevel >= CONFIG.totalLevels) {
        endGame();
        return;
    }
    
    gameState.currentLevel++;
    gameState.correctAnswers = 0;
    
    showScreen('game-screen');
    startLevel();
}

/**
 * End the game
 */
function endGame() {
    stopTimer();
    
    // Calculate final stats
    const percentage = Math.round((gameState.score / gameState.totalPossibleScore) * 100) || 0;
    const { emoji, title } = getResultsFeedback(percentage);
    const grade = calculateGrade(percentage);
    
    // Update UI
    DOM.resultsEmoji.textContent = emoji;
    DOM.resultsTitle.textContent = title;
    DOM.finalScore.textContent = gameState.score;
    DOM.scoreBreakdown.textContent = `out of ${gameState.totalPossibleScore} possible`;
    DOM.finalPercentage.textContent = `${percentage}%`;
    DOM.correctAnswersEl.textContent = gameState.correctAnswers;
    DOM.maxStreakEl.textContent = gameState.maxStreak;
    DOM.levelReached.textContent = gameState.currentLevel;
    DOM.grade.textContent = grade;
    
    // Submit results to Google Sheets
    submitResults(percentage);
    
    showScreen('gameover-screen');
}

/**
 * Submit results to Google Sheets
 */
async function submitResults(percentage) {
    const data = {
        name: gameState.playerName,
        score: gameState.score,
        total: gameState.totalPossibleScore,
        percentage: percentage,
        timestamp: new Date().toISOString()
    };
    
    // Only submit if URL is configured
    if (CONFIG.googleScriptURL === 'YOUR_GOOGLE_APPS_SCRIPT_URL_HERE') {
        console.log('Results would be submitted:', data);
        return;
    }
    
    try {
        await fetch(CONFIG.googleScriptURL, {
            method: 'POST',
            mode: 'no-cors',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(data)
        });
        showToast('Results saved successfully!', 'success');
    } catch (error) {
        console.error('Failed to submit results:', error);
        showToast('Could not save results. Please try again.', 'error');
    }
}

/**
 * Pause/Resume game
 */
function pauseGame() {
    gameState.isPaused = true;
    DOM.pauseScore.textContent = gameState.score;
    DOM.pauseLevel.textContent = gameState.currentLevel;
    DOM.pauseModal.classList.remove('hidden');
}

function resumeGame() {
    gameState.isPaused = false;
    DOM.pauseModal.classList.add('hidden');
}

function quitGame() {
    stopTimer();
    DOM.pauseModal.classList.add('hidden');
    endGame();
}

/**
 * Power-up functions
 */
function useFiftyFifty() {
    if (gameState.powerups.fiftyFifty <= 0 || gameState.answered) return;
    
    gameState.powerups.fiftyFifty--;
    updatePowerupUI();
    
    const buttons = DOM.answersContainer.querySelectorAll('.answer-btn:not(.eliminated)');
    const wrongButtons = Array.from(buttons).filter(btn => btn.dataset.correct !== 'true');
    
    // Eliminate 2 wrong answers
    shuffleArray(wrongButtons).slice(0, 2).forEach(btn => {
        btn.classList.add('eliminated');
    });
    
    showToast('50/50 used! Two wrong answers removed.', 'success');
}

function useSkip() {
    if (gameState.powerups.skip <= 0 || gameState.answered) return;
    
    gameState.powerups.skip--;
    updatePowerupUI();
    
    gameState.currentQuestion++;
    if (gameState.currentQuestion >= CONFIG.questionsPerLevel) {
        levelComplete();
    } else {
        loadQuestion();
    }
    
    showToast('Question skipped!', 'success');
}

function useExtraTime() {
    if (gameState.powerups.extraTime <= 0) return;
    
    gameState.powerups.extraTime--;
    updatePowerupUI();
    
    gameState.timeLeft += 15;
    DOM.timer.textContent = gameState.timeLeft;
    
    showToast('+15 seconds added!', 'success');
}

function updatePowerupUI() {
    DOM.powerup5050.querySelector('.powerup-count').textContent = gameState.powerups.fiftyFifty;
    DOM.powerupSkip.querySelector('.powerup-count').textContent = gameState.powerups.skip;
    DOM.powerupTime.querySelector('.powerup-count').textContent = gameState.powerups.extraTime;
    
    DOM.powerup5050.disabled = gameState.powerups.fiftyFifty <= 0;
    DOM.powerupSkip.disabled = gameState.powerups.skip <= 0;
    DOM.powerupTime.disabled = gameState.powerups.extraTime <= 0;
}

/**
 * Restart and navigation
 */
function restartGame() {
    DOM.playerNameInput.value = gameState.playerName;
    startGame();
}

function goHome() {
    stopTimer();
    showScreen('start-screen');
}

// ============================================
// INITIALIZE
// ============================================

document.addEventListener('DOMContentLoaded', initGame);
