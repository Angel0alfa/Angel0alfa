let timer;
let isRunning = false;
let time = 0;

const display = document.getElementById('display');
const startButton = document.getElementById('start');
const pauseButton = document.getElementById('pause');
const stopButton = document.getElementById('stop');
const resetButton = document.getElementById('reset');

startButton.addEventListener('click', () => {
    if (!isRunning) {
        isRunning = true;
        timer = setInterval(() => {
            time++;
            display.textContent = new Date(time * 1000).toISOString().substr(11, 8);
        }, 1000);
    }
});

pauseButton.addEventListener('click', () => {
    if (isRunning) {
        clearInterval(timer);
        isRunning = false;
    }
});

stopButton.addEventListener('click', () => {
    clearInterval(timer);
    isRunning = false;
    time = 0;
    display.textContent = '00:00:00';
});

resetButton.addEventListener('click', () => {
    clearInterval(timer);
    isRunning = false;
    time = 0;
    display.textContent = '00:00:00';
});
