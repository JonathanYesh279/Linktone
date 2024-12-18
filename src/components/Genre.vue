<template>
    <div class="genre-list-container">
        <ul class="genre-list">
            <li class="genre">היפ הופ</li>
            <li class="genre">רוק</li>
            <li class="genre">פופ</li>
            <li class="genre">ים תיכוני</li>
            <li class="genre">אלטרניטיב אינדסטריאל</li>
            <li class="genre">ראפ</li>
            <li class="genre">פלוק רוק קאנטרי</li>
            <li class="genre">היפ הופ</li>
            <li class="genre">רוק</li>
            <li class="genre">פופ</li>
            <li class="genre">ים תיכוני</li>
            <li class="genre">אלטרנטיב אינדסטריאל</li>
        </ul>
        <div class="icon-container">
            <span class="bg"></span>
            <i class="fa-solid fa-chevron-up"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Genre',
    data() {
        return {genre: false}
    },
    methods: {
        isGenreOpen() {
            this.genre 
        }
    }
}
</script>

<style scoped lang="scss">
    .genre-list-container {
        display: flex;
        justify-content: flex-start;
        padding-right: 50px;
        background-color: #fff;
        width:90%;

        .genre-list {
            display: flex;
            justify-content: flex-start;
            gap: 20px;
            flex-wrap: wrap;
            width: 100%;
        }

        .icon-container {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            cursor: pointer;

            .bg { display: flex; background-color:#dfdfdf; height: 20px; width: 20px; align-items: center; justify-content: center; padding: 35px; border-radius: 50%;opacity: 0.3; }
            svg {position: absolute; }
        }

        .genre {
            list-style: none;
            padding: 10px;
            border: 1px solid gray;
            color: gray;
            border-radius: 15px;
            padding: 20px 30px 20px 30px;
            cursor: pointer;
        }
    }
</style>