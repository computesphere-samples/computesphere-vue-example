<template>
    <div class="counter-container">
        <h3>
            Countdown Timer Example
        </h3>
        <p class="description text">This tool allows you to set a countdown timer using the form.</p>
        <div>
            <form @submit.prevent="startCountdown">
                <label for="time">Enter time in seconds:</label>
                <input type="number" v-model="timeInput" min="1" id="time" required />
                <button type="submit">Start</button>
            </form>
            <div v-if="countdown !== null">
                <p>Time remaining: {{ countdown }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const timeInput = ref(5);
const countdown = ref(null);
let timer = null;

const playSound = () => {
    const context = new (window.AudioContext || window.webkitAudioContext)();
    const oscillator = context.createOscillator();
    oscillator.type = 'sine';
    oscillator.frequency.setValueAtTime(440, context.currentTime);
    oscillator.connect(context.destination);
    oscillator.start();
    oscillator.stop(context.currentTime + 1);
}

const startCountdown = () => {
    clearInterval(timer);
    countdown.value = timeInput.value;

    timer = setInterval(() => {
        if (countdown.value > 0) {
            countdown.value--;
        } else {
            clearInterval(timer);
            playSound()
        }
    }, 1000);
};
</script>

<style lang="scss" scoped></style>
