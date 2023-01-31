<script setup>
import PhotoIcon from './icons/PhotoIcon.vue';
</script>

<template>
    <div class="container-photo">
        <label for="fileUpload" class="upload"><PhotoIcon /></label>
        <input type="file" name="" id="fileUpload" accept=".jpg, .jpeg, .png">
    </div>
</template>

<style lang="scss" scoped>
.container-photo{
    input[type=file] {
    display: none;
    }

    .upload{
        height: 100px;
        width: 100px;
        display: flex;
        border-radius: 50%;
        background-color: rgb(60, 86, 173);
        color: black;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        &:hover{
            background-color: azure;
        }
    }
}

</style>
