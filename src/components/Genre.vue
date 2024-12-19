<template>
    <div class="genre-list-container">
        <ul class="genre-list" :class="{ 'collapsed': !isExpanded }">
            <li class="genre" :key="filter.name" @click="filter.active =! filter.active" v-for="filter in filteredGenres" v-text="filter.name" :class="{ active: filter.active }" ></li>
        </ul>
        <div class="icon-container" @click="toggleGenre()" :class="{rotated: isExpanded }">
            <span class="bg"></span>
            <i class="fa-solid fa-chevron-up" ></i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Genre',
    data() {
        return {
            isExpanded: false,
            filteredGenres: [
                { name: 'היפ הופ', active: false },
                { name: 'רוק', active: false },
                { name: 'פופ', active: false },
                { name: 'ראפ', active: false },
                { name: 'אלטרנטיב אינדסטריאל', active: false },
                { name: 'ים תיכוני', active: false },
                {name: 'ראפ', active: false },
                { name: 'אלטרנטיב אינדסטריאל', active: false },
                { name: 'היפ הופ', active: false },

            ]
        }
    },
    methods: {
        toggleGenre() {
            this.isExpanded = !this.isExpanded
        }
    }
}
</script>

<style scoped lang="scss">

    .genre-list-container {
        display: flex;
        justify-content: flex-start;
        padding: 30px;
        background-color: #fff;
        width:60%;

        .genre-list { display: flex; justify-content: flex-start; gap: 20px; flex-wrap: wrap; width: 100%; height: 100%;  
            &.collapsed { height: 80px; overflow: hidden; }
            @media (max-width: 600px) {
                .genre {padding: 10px;}
                &.collapsed { height: 60px; }
            }
            
        }

        .icon-container {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            cursor: pointer;
            &.rotated {
                .fa-chevron-up{transform: rotate(180deg);}
            }

            .bg { display: flex; background-color:#dfdfdf; height: 20px; width: 20px; align-items: center; justify-content: center; padding: 35px; border-radius: 50%;opacity: 0.3; 
                @media (max-width: 600px) {
                    padding: 20px;
            }
            }
            .fa-chevron-up {
                &{position: absolute; }
            }
        }

        .genre {
            list-style: none;
            border: 1px solid #212530;
            font-size: 18px;
            color: #212530;
            border-radius: 15px;
            padding: 20px 45px 20px 45px;
            cursor: pointer;
            &.active {
                background-color: #ff256e;
                color: #fff;
                border: none;
            }

            &:after {
                content: '';
            }

        }
    }
</style>