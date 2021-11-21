<script setup>
import searchItems from '../search.json'
const currentItem = searchItems?.shift();
console.log(currentItem)
</script>
  
<template>
  <div class="content">
    <div class="con">
      <!-- <div class="shlogo" style="background: url(icon/logo3.svg) no-repeat center/cover;"></div> -->
      <div class="sou">
        <form action method="post" target="_self">
          <div class="lg" :style="{background: 'url(' + currentItem.icon + ') no-repeat center/cover;'}"></div>
          <!--input class="t" type="text" value="" name="t" hidden-->
          <input
            class="wd"
            type="text"
            placeholder="请输入搜索内容"
            name="q"
            x-webkit-speech
            lang="zh-CN"
            autocomplete="off"
          />
          <button>
            <svg class="icon" style=" width: 21px; height: 21px; opacity: 0.5;" aria-hidden="true">
            </svg>
          </button>
        </form>
        <div id="word"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.con {
    width: 100%;
    transition: 1s all;
    margin: auto;
    min-width: 320px;
    height: 50px;
    position: fixed;
    top: 50px;
    left: 0px;
    right: 0px;
    z-index: 1000;
}

.con .shlogo {
    position: relative;
    width: 480px;
    height: 120px;
    margin: 20px auto;
    background: url(icon/logo.svg) no-repeat center/cover;
}

.con .shlogo a {
    width: 100%;
    display: block;
    width: 100%;
    height: 100%;
}

.con .sou {
    max-width: 680px;
    position: relative;
    width: calc(100% - 60px);
    min-width: 320px;
    margin: 0 auto;
}

.con .sou form {
    width: 100%;
    /*border: 1px solid #ddd;*/
    height: 50px;
    display: block;
    margin: 10px auto 30px;
    position: relative;
}

.con .sou form .wd {
    width: 100%;
    height: 100%;
    display: block;
    border: 1px solid #ddd;
    border-radius: 25px;
    line-height: 100%;
    font-size: 18px;
    text-indent: 50px;
    transition: 0.3s all;
}
.con .sou form .lg {
        display: block;
        width: 30px;
        height: 30px;
        position: absolute;
        left: 13px;
        top: 10px;
       /* background: url(icon/lg.svg) no-repeat center/cover;*/
        border-radius: 50%;
        overflow: hidden;
        cursor: pointer;
}


.con .sou form .wd:focus {
    background: #fff;
    box-shadow: 0 0px 15px 0 rgba(32, 33, 36, 0.2);
    border-color: #fff
}

.con .sou form button {
    width: 40px;
    height: 40px;
    display: block;
    position: absolute;
    z-index: 10;
    right: 6px;
    top: 6px;
    cursor: pointer;
    font-size: 22px;
    line-height: 40px;
    border-radius: 50%;
    color: #777;
}

.con .sou #word{
    width: calc(100% - 70px);
    border: 15px solid #f1f1f1;
    border-radius: 10px;
    left:20px;
    position: absolute;z-index: 500; top:65px;
    background: #f1f1f1;
    line-height: 30px; font-style: 16px;overflow: hidden;
    display: none; 
}
.con .sou #word .li{
    cursor: pointer;
    color: #555;
}
.con .sou #word .li:hover{
    color: #29f;
}
</style>
