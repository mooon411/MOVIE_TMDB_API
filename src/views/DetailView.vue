
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
    </header>
    <main id="main">
        <DetailIntro v-if="movieBasic" :movieBasic="movieBasic" />
    </main>
</template>

<script>
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import axios from 'axios';

import DetailIntro from "../components/detail/DetailIntro.vue"

export default {
    name: "MovieDetailPage",
    
    components: {
        DetailIntro,
    },
    
    setup() {
        // const getImageUrl = (path) => { return path ? `https://image.tmdb.org/t/p/w500/${path}` : '';};
        const movieBasic = ref(null);

        const route = useRoute();

        onMounted(async () => {
            const movieId = route.params.movieId;
            const apiKey = import.meta.env.VITE_API_KEY;
            const language = "ko-KR";

            try {
                const resMovieBasic = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}?language=${language}&api_key=${apiKey}`);
                movieBasic.value = resMovieBasic.data;
            } catch (err) {
                console.log(err)
            }
        });

        return { movieBasic }
    }
}

</script>

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
</style>