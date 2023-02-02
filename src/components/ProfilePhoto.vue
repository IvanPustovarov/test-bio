<script setup>
import PhotoIcon from './icons/PhotoIcon.vue';
import PencilIcon from './icons/PencilIcon.vue'
import RecycleBinIcon from './icons/RecycleBinIcon.vue';
import { ref } from 'vue';

const file = ref(null);

function clearFunc (event) {
    URL.revokeObjectURL(event.target);
}

function loadFile (event) {
    if(event){
        const target = URL.createObjectURL(event.target.files[0]);
        file.value = target;
    }
}
</script>

<template>
    <div class="container-photo">
        <label for="fileUpload" class="upload" v-if="!file">
            <PhotoIcon />
        </label>
        <input
          type="file"
          name=""
          id="fileUpload"
          accept="image/*"
          capture
          @change="loadFile($event)"
        >
        <img
          :src="file"
          v-if="file"
          @load="clearFunc"
          alt="photo-profile"
          class="profile-pic"
        />
        <div class="control-panel" v-if="file">
            <div class="item">
                <label for="fileUpload">
                   <PencilIcon />
                </label>
                <input
                type="file"
                name=""
                id="fileUpload"
                accept="image/*"
                capture
                @change="loadFile($event)"
                >
            </div>
            <div class="item" @click="() => {file = null}">
                <RecycleBinIcon />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container-photo{
    display: flex;
    flex-direction: column;
    margin: 100px 0 0 100px;

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
            background-color: rgb(117, 142, 223);
        }
    }
    .profile-pic{
        max-width: 300px;
        max-height: 300px;
    }
    .control-panel{
        background-color: rgb(60, 86, 173);
        max-width: 300px;
        border-radius: 10px;
        justify-content: space-around;
        align-items: center;
        display: flex;

        & .item{
            cursor: pointer;
            padding: 6px;
            margin: 5px 0;
            border-radius: 50%;
            &:hover{
                background-color: rgb(117, 142, 223);;
                 & svg{
                    fill: white;
                }
            }
        }
    }
}

</style>
