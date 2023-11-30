<script setup>
// import { onMounted, ref } from 'vue';
// import axios from 'axios';

// const movies = ref([]);

// const fetchPoster = async () => {
//   try {
//     const response = await axios.get('https://api.themoviedb.org/3/movie/popular', {
//       params: {
//         api_key: 'f9f5a04a5733a453e5672b5b6c51d445',
//         language: 'ko-KR',
//         page: '1'
//       }
//     });
//     movies.value = response.data.results;
//     console.log(movies);
//   } catch(err) {
//     console.log(err);
//   }
// };

// onMounted(fetchPoster);
</script>
<template>
    <header id="header" role="banner">
        <nav>
            <div class="logo">
                <a href="/">무비세상</a>
            </div>
            <ul>
                <li><a href="/">인기영화 TOP10</a></li>
                <li><a href="/">떠오르는 영화 TOP10</a></li>
            </ul>
        </nav>
       <div class="slide_area">
        <div class="slide_item container">
            <div class="slide_poster">
                <img src="https://image.tmdb.org/t/p/w500/vFsSluuzqxR46Ils9ib52ItdE9u.jpg" alt="movies[2].title">
            </div>
            <div class="slide_info">
                <h2 class="title">크리에이터</h2>
                <p class="desc">"인류를 지키기 위해 만들어진 AI가 LA에 핵폭탄을 터뜨린 후, 인류와 AI 간의 피할 수 없는 전쟁이 시작된다. 전직 특수부대 요원 ‘조슈아’는 실종된 아내의 단서를 얻을지도 모른다는 생각에 전쟁을 끝내기 위한 인류의 작전에 합류한다. 인류를 위협할 강력한 무기와 이를 창조한 ‘창조자’를 찾아 나서고, 그 무기가 아이 모습의 AI 로봇 '알피'란 사실을 알게 되는데… 인간적인가, 인간의 적인가? 10월, SF 블록버스터의 신세계가 펼쳐진다!"</p>
                <div class="date">
                    <h4>개봉일</h4>
                    2023.10.03
                </div>
                <ul class="credit">
                    <h4>출연진</h4>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                </ul>
            </div>
        </div>
        <div class="slide_bg">
            <img src="https://image.tmdb.org/t/p/w500/kjQBrc00fB2RjHZB3PGR4w9ibpz.jpg" alt="movies[2].title">
        </div>
       </div>
    </header>
</template>

<style lang="scss">
nav{
    position: absolute;
    z-index: 50;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 20px;

    .logo {
        padding: 0 20px;
        font-size: 1.5rem;
        font-family: 'HakgyoansimMalgeunnalB';
    }
    ul {
        display: flex;
        justify-content: space-between;
        li {
            font-size: .95rem;
            padding: 0px 20px;
        }
    }
}
.slide_area {
    width: 100%;
    height: 75vh;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;

    h4{
        width: 100%;
        margin: 5px 0;
        font-size: 0.8;
        color: var(--white300);
    }

    .slide_item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: relative;
        z-index: 100;
        .slide_poster {
            img {
                height: 500px;
            }
        }
        .slide_info {
            width: 60%;
            
            .title {
                font-size: 2vw;
            }
            .desc {
                font-size: 0.85rem;
                overflow: hidden;
                text-overflow: ellipsis;
                display: -webkit-box;
                -webkit-line-clamp: 2;
                -webkit-box-orient: vertical;
                margin-bottom: 20px;
            }
            .credit {
                margin: 20px 0;
                display: flex;
                justify-content: left;
                flex-wrap: wrap;
                li {
                    width: 70px;
                    height: 90px;
                    margin-right: 20px;
                    background-position: center center;
                    background-image: url("https://www.themoviedb.org/t/p/w500/mLKvNuCJSgyK0WdLd4ogO81sOO1.jpg");
                    background-size: cover;
                }
            }
        }
    }
    .slide_bg img {
            display: block;
            width: 100%;
            height: auto;
            filter: blur(3px);
            position: absolute;
            top: 0;
            left: 0;
        }

        &::after {
            content: '';
            display: block;
            width: 100%;
            height: 100%;
            background: #000;
            opacity: 0.5;
            position: absolute;
            top: 0;
            left: 0;    
        }
    }

</style>