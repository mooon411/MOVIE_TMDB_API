<template>
    <div class="slide_area">
        <div class="slide_item container">
            <div class="slide_poster">
                <img :src="getImageUrl(movieInfo.poster_path)" :alt="movieInfo.title">
            </div>
            <div class="slide_info">
            <h2 class="title">{{ movieBasic.title }}</h2>
            <p class="desc">{{ movieBasic.overview }}</p>
            <div class="date">
                <h4>개봉일</h4>
                🚀 {{ movieBasic.release_date }}
            </div>
            <div class="vote_average">
                <h4>평점</h4>
                ⭐ {{ movieBasic.vote_average }}
            </div>
            <ul class="credit">
                <h4>출연진</h4>
                <!-- <li v-for="actor in movieBasic.cast" :key="actor.id" :style="{ backgroundImage: `url(${getImageUrl(actor.profile_path)})` }"></li> -->
            </ul>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
        props: {
            movieBasic: {
                type: Object,
                required: true,
            },
        },
    }
</script>

<style lang="scss">
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
                li:nth-child(n+8) {
                    display: none;
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