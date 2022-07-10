<template>
  <div class="main-container">
    <div class="top-labels">
    <span>Home</span>
    <span>Challenge: 1/10</span>
    </div>
    <div class="challenge-flag-wrapper">
      <img id="challenge-flag" :src="challengeFlagPath" alt="">
    </div>
    <div class="challenge-options">
      <button class="button-default-style" @click="challengeFlag = 'kh'">Khmer</button>
      <button class="button-default-style" @click="challengeFlag = 'nc'">Nepali</button>
      <button class="button-default-style" @click="challengeFlag = 'kr'">Korean</button>
      <button class="button-default-style" @click="challengeFlag = 'lr'">Lurkish</button>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      challengeFlagPath: 'https://static.significados.com.br/flags/br.svg',
    }
  }
}
</script>

<style scoped>
  .challenge-flag-wrapper{
    padding-top: 3rem;
    width: 100%;
    display: flex;
    justify-content: center;
  }

  #challenge-flag {
    width: 20rem;
    height: auto;
  }

  .challenge-options{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .top-labels{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .top-labels span{
    font-size: 1.5rem;
    color: #E5E5E5;
  }
</style>
