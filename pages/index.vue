<template>
  <div>
    <section class="title-section">
      <h1>Guess The Flag</h1>
      <img :src="homeFlagPath" id="home-flag">
    </section>
    <section class="home-action-buttons main-container" v-if="gameMode == ''">
      <p>Challenge yourself or your friends!</p>
      <button class="button-default-style" @click="gameMode = 'singleplayer'">Singleplayer Challenge</button>
      <button class="button-default-style">Multiplayer Challenge</button>
    </section>
    <section v-if="gameMode == 'singleplayer'">
      <SinglePlayerGame />
    </section>
    <footer>
      <p>Made by Carlos Vaz&copy; 2022</p>
    </footer>
  </div>
</template>

<script>
import SinglePlayerGame from '~/components/SinglePlayerGame.vue';
export default {
  components: {
    SinglePlayerGame
  },
  data(){
    return {
      homeFlagPath: 'https://static.significados.com.br/flags/br.svg',
      flagPaths: [
        'https://static.significados.com.br/flags/kh.svg',
        'https://static.significados.com.br/flags/nc.svg',
        'https://static.significados.com.br/flags/kr.svg',
        'https://static.significados.com.br/flags/lr.svg',
        'https://static.significados.com.br/flags/ca.svg',
      ],
      gameMode: '',
    }
  },
  created(){
    setInterval(() => {
        this.homeFlagPath = this.flagPaths[Math.floor(Math.random() * this.flagPaths.length)];
    }, 3000);
  }
}
</script>

<style scoped>
.title-section {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 2rem;
}

#home-flag {
  width: 6rem;
  height: auto;
  margin-left: 1.5rem;
}

.title-section h1 {
  font-size: 3rem;
  color: #fff;
}

.home-action-buttons {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 25rem;
}

.home-action-buttons p {
  color: #E5E5E5;
  font-size: 1.3rem;
}

footer {
  position: absolute;
  bottom: 0;
  height: 2rem;
  background-color: #0f192e;
  width: 100%;
  color: rgb(77, 77, 77);
  display: flex;
  align-items: center;
  padding-left: 1rem;
}
</style>
