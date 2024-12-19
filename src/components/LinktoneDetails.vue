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
                <li class="list-item">ראשי</li>
                <li class="list-item">מילים</li>
                <li class="list-item">קרדיטים</li>
                <li class="list-item">הורדות</li>
                <li class="list-item">עיתונות</li>
                <li class="list-item">לינקטונים נוספים</li>
            </ul>
        </nav>

        <div class="details-content">
            <div class="details-content-header">
                <h1>לירן דנינו</h1>
                <p>צמאה לאהבה</p>
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
            <img src="../assets/linktone_image.jpg" />
        </div>
        <div class="description">
            <p>
               לירן דנינו אחד מהזמרים הכי פחות אהובים ומהיוצרים הפחות פוריים בישראל. בשיר חדש עם קליפ רגיל מינוס בכיכובה של אלינה מארץ הפלאות בת זוגו החדשה של לירן. 
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
        required: false
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
            .list-item { padding-left: 30px; font-size: 14px;}
        }
    }

    .details-content {display: flex; justify-content: space-between; align-items: center; padding-inline: 20px;
        .details-content-header {color: #fff;}
        .social-container {
            .social {display: flex; gap: 10px; color: #fff;}
             .duration {display:flex; justify-content: flex-end; color: #fff; padding: 5px;}
        }
    }

    .image-container {display:flex; justify-content: center; padding: 10px; width: 100%;
        img {width: 100%; height: 40vh; border-radius: 30px;}
    }
    
    .description {padding: 20px; color: #fff; border-bottom: 1px solid #fff;}
  }
  </style>