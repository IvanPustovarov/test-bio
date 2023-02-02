<script setup>
import {ref} from 'vue';

const selectedLanguages = ref([]);
</script>

<template>
    <div class="personal-data-container">
        <input type="text" class="input-item">
        <input type="date" name="" id="" class="input-item">
        <input type="email" name="" id="" class="input-item">
        <input type="text" class="input-item">
        <input type="tel" name="" id="" class="input-item">
        <div>
            <input type="checkbox" id="english" value="English" v-model="selectedLanguages">
            <label for="english">English</label>

            <input type="checkbox" id="russian" value="Russian" v-model="selectedLanguages">
            <label for="russian">Russian</label>

            <input type="checkbox" id="japanese" value="Japanese" v-model="selectedLanguages">
            <label for="japanese">Japanese</label>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.personal-data-container{
    display: flex;
    flex-direction: column;
    margin: 20px;
    min-width: 350px;
    gap: 8px;

    & .input-item{
        height: 30px;
        font-size: 18px;
        border: none;
        border-radius: 3px;
        padding: 2px;
        &:focus{
            outline: none;
        }
    }
}
</style>
