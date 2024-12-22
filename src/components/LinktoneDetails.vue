<template>
    <div class="linktone-details">

        <div class="details-header">
            <div class="actions-container">
                <div class="icon">
                    <i class="fa-solid fa-download fa-lg"></i>
                </div>
                <div class="icon">
                    <i class="fa-solid fa-plus lg"></i></div>
                <div class="icon">
                    <i class="fa-solid fa-share-nodes lg"></i>
                </div>
                <div class="icon">
                    <i class="fa-regular fa-heart lg"></i>
                </div>
            </div>
            <div class="linktone-display">הצג לינקטון</div>
        </div>

        <nav class="nav-details">
            <ul class="list-details">
                 <li class="list-item" :key="activeLink.name" @click="activeLink.active =! activeLink.active"             v-for="activeLink in activeLinks" v-text="activeLink.name" :class="{ active: activeLink.active }" >
        </li>
            </ul>
        </nav>

        <div class="details-content">
            <div class="details-content-header">
                <h1>{{ linktone.linktone_title }}</h1>
                <p>{{ linktone.linktone_song_title }}</p>
            </div>
            <div class="social-container">
                <div class="social">
                    <div class="icon"><i class="fa-brands fa-youtube"></i></div>
                    <div class="icon"><i class="fa-brands fa-twitter"></i></div>
                    <div class="icon"><i class="fa-brands fa-facebook-f"></i></div>
                    <div class="icon"><i class="fa-brands fa-wikipedia-w"></i></div>
                </div>
                <div class="duration">
                    <div>04:32</div>
                </div>
            </div>
        </div>

        <div class="image-container">
            <img :src="linktone.img" />
        </div>
        <div class="description">
            <p>
              {{ linktone.description || 'לירן דנינו אחד מהזמרים הכי פחות אהובים ומהיוצרים הפחות פוריים בישראל. בשיר חדש עם קליפ רגיל מינוס בכיכובה של אלינה מארץ הפלאות בת זוגו החדשה של לירן.' }} 
            </p>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LinktoneDetails',
    props: {
        linktone: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            activeLinks: [
                {name: 'ראשי', active: false},
                {name: 'מילים', active: false},
                {name: 'קרדיטים', active: false},
                {name: 'הורדות', active: false},
                {name: 'עיתונות', active: false},
                {name: 'לינקטונים נוספים', active: false}
            ]
        }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .linktone-details {padding: 20px; width: 100%; height: 100vh; background-color: #313030; z-index: 10; border-top-right-radius: 30px;
    .details-header {display: flex; width: 100%; justify-content: space-between;
        .actions-container {display: flex; gap: 10px;
            .icon {width: 20px; height: 20px; display: flex; align-items: center; justify-content: center; padding: 15px; border-radius: 50%; border: 1px solid #fff; color: #fff;}
        }
        .linktone-display {padding-inline: 30px; border: 2px solid #fff; border-radius: 20px; color: #fff; font-weight: 700;}
    }
    .nav-details {
        display: flex; color: #fff; width: 100%; padding: 20px; justify-content: center;
        .list-details { display: flex; list-style: none; border-bottom: 1px solid #fff; padding-bottom: 10px; gap: 5px;
            .list-item { padding-left: 30px; font-size: 14px; cursor: pointer;
                &.active {border-bottom: 2px solid #fff;}
            }

        }
    }

    .details-content {display: flex; justify-content: space-between; align-items: center; padding-inline: 20px;
        .details-content-header {display: flex; flex-direction: column; color: #fff;
            h1 {line-height: 1; font-size: 26px;}
            p {font-size: 14px;}
        }
        .social-container {
            .social {display: flex; gap: 10px; color: #fff;}
             .duration {display:flex; justify-content: flex-end; color: #fff; padding-top: 5px;}
        }
    }

    .image-container {display:flex; justify-content: center; padding: 10px; width: 100%;
        img {width: 100%; aspect-ratio: 16/9; object-fit: cover; border-radius: 20px;} 
    }
    
    .description {padding: 20px; color: #fff; border-bottom: 1px solid #fff;}
  }
  </style>