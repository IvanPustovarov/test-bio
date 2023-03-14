<script setup>
import {ref, reactive} from 'vue';

const selectedLanguages = ref([]);
const userData = reactive({ name: '', date: null, email: '', tel: '', city: '' });


</script>

<template>
    <div class="personal-data-container">
        <input type="text" class="input-item" v-model="userData.name" placeholder="Имя">

        <input type="date" name="" id="" class="input-item" v-model="userData.date">
        <input type="email" name="" id="" class="input-item" v-model="userData.email" placeholder="Email">
        <input type="text" class="input-item" v-model="userData.city" placeholder="Город">
        <input type="tel" name="" id="" class="input-item" v-model="userData.tel" placeholder="Телефон">
        <div class="langues">
            <div class="langue-item">
                <input type="checkbox" id="english" value="English" v-model="selectedLanguages">
                <label for="english">English</label>
            </div>
            <div class="langue-item">
                <input type="checkbox" id="russian" value="Russian" v-model="selectedLanguages">
                <label for="russian">Russian</label>
            </div>
            <div class="langue-item">
                <input type="checkbox" id="japanese" value="Japanese" v-model="selectedLanguages">
                <label for="japanese">Japanese</label>
            </div>
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

    & .langues{
        display: flex;
        flex-direction: column;
        & .langue-item{
            display: flex;
            input[type=checkbox] {
                position: relative;
	            cursor: pointer;
                margin-right: 10px;
            }
            input[type=checkbox]:before {
                content: "";
                display: block;
                position: absolute;
                width: 20px;
                height: 20px;
                top: 0;
                left: 0;
                border: 2px solid #555555;
                border-radius: 3px;
                background-color: white;
            }
            input[type=checkbox]:checked:after {
                content: "";
                display: block;
                width: 7px;
                height: 12px;
                border: solid black;
                border-width: 0 2px 2px 0;
                -webkit-transform: rotate(45deg);
                -ms-transform: rotate(45deg);
                transform: rotate(45deg);
                position: absolute;
                top: 2px;
                left: 6px;
            }
        }
    }
}
</style>
