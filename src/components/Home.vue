<script setup>
import Search from '../components/Search.vue'
import items from '../home.json'
</script>

<template>
  <Search/>
  <div class="container">
    <!--第一行-->

    <div v-for="item in items" class="box">
      <a :target="item.target" :href="item.href">
        <div class="img">
          <img :src="item.icon" />
        </div>
      </a>
      <p>{{ item.title }}</p>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 700px;
  height: 600px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  align-items: center;
}
.container .box {
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  align-items: center;
  align-content: center;
  width: 100px;
  height: 140px;
  margin: 20px;
}
.container .box .img {
  width: 100px;
  height: 100px;
  box-shadow: 18px 18px 30px rgba(0, 0, 0, 0.1),
    -18px -18px 30px rgba(255, 255, 255, 1);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #efeeee;
  transition: box-shadow 0.2s ease-out;
  position: relative;
  cursor: pointer;
}

.container .box .img img {
  width: 60px;
  transition: width 0.2s ease-out;
}
.container .box p {
  color: slategrey;
}
.container .box .img:hover {
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.2),
    0px 0px 0px rgba(255, 255, 255, 0.8),
    inset 18px 18px 30px rgba(0, 0, 0, 0.1),
    inset -18px -18px 30px rgba(255, 255, 255, 1);
  transition: box-shadow 0.2s ease-out;
}
.container .box .img:hover img {
  width: 58px;
  transition: width 0.2s ease-out;
}
</style>
