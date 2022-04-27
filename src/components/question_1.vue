<template>
    <div class="question-1">
        <h2>Test Nawadata Mohammad Wildan Rizkiyadi</h2>
        <h3>Question No.1</h3>
        <label for="question1">
            Masukan Kalimat
        </label>
        <input type="text" name="question1" v-model="question1" />
        <h3>Output</h3>
        <div v-if="question1.length > 0">
            <p>Vowel Characters: {{ countVowel }}</p>
            <p>Consonant Characters: {{ countConsonant }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            question1: '',
        }
    },
    computed: {
        countVowel() {
            return this.question1.toLowerCase().replace(/[^aeiou]/gi, '');
        },
        countConsonant() {
            return this.question1.toLowerCase().replace(/[^bcdfghjklmnpqrstvwxyz]/gi, '');
        }
    },
    methods: {
        question1_remove_space() {
            return this.question1.replace(/\s/g, '')
        },
    }
}
</script> 