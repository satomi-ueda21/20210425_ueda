<template>
  <footer class="top-footer">
    <div class="flex">
      <h1 class="footer-logo">estra inc.</h1>
      <nav class="footer-nav">
        <ul>
          <li><a href="#">home</a></li>
          <li><a href="#">about</a></li>
          <li><a href="#">service</a></li>
          <li><a href="#">works</a></li>
          <li><a href="#">price</a></li>
          <li><a href="#">contact</a></li>
        </ul>
      </nav>
    </div>
    <div id="footer-hamburger" @click="footer_hamburger()" :class="{'active':isClass}"> 
      <span></span>
      <span></span>
      <span></span>
    </div>
    <nav class="menu-content" :class="{'open':isClass}" v-if="show">
      <p class="menu-title">estra inc.</p>
      <ul class="menu-content_inner">
        <li><a href="#">home</a></li>
        <li><a href="#">about</a></li>
        <li><a href="#">service</a></li>
        <li><a href="#">works</a></li>
        <li><a href="#">price</a></li>
        <li><a href="#">contact</a></li>
      </ul>
    </nav>
 
    <div class="footer-bar"></div>
    <small>Copyright 2019 estra inc. All Rights Reserved.</small>
  </footer>
</template>

<script>
export default {
  data(){
    return{
      isClass:false,
      show:false
    };
  },
  methods:{
    footer_hamburger(){
      this.isClass=!this.isClass;
      this.show=!this.show;
    }
  } 
}
</script>

<style scoped>
  .footer-bar {
    height: auto;
    line-height: 60px;
  }

  .top-footer {
    background: #000;
    text-align: center;
    position:relative;
  }

  .top-footer small {
    text-align: center;
    color: #fff;
  }

  .footer-logo {
    font-size: 20px;
    font-weight: bold;
    margin-left: 35px;
    color: #fff;
    line-height: 60px;
  }

  .footer-nav li {
    display: inline-block;
    margin-right: 35px;
    font-size: 16px;
  }

  .footer-nav a {
    color: #fff;
  }

  @media screen and (max-width: 768px) {

  #footer-hamburger {
    width: 40px;
    height: 40px;
    position: absolute;
    cursor: pointer;
    z-index: 100;
    bottom: 30px;
    right: 20px;
    transition: 0.4s;
  }
  #footer-hamburger span {
    position: absolute;
    left: 2px;
    display: block;
    width: 35px;
    height: 2px;
    background-color: #fff;
    transition: 0.8s;
  }
  #footer-hamburger span:nth-of-type(1) {
    top: 10px;
  }
  #footer-hamburger span:nth-of-type(2) {
    top: 20px;
  }
  #footer-hamburger span:nth-of-type(3) {
    top: 30px;
  }
  .footer-nav {
    display: none;
  }

  #footer-hamburger.active span:nth-of-type(1) {
    top: 20px;
    transform: rotate(45deg);
  }

  #footer-hamburger.active span:nth-of-type(2) {
    opacity: 0;
  }
  #footer-hamburger.active span:nth-of-type(3) {
    top: 20px;
    transform: rotate(-45deg);
  }
  .menu-content {
    display: block;
    width: calc(100% - 80px);
    height: 100%;
    text-align: center;
    transition: 0.2s;
    position: fixed;
    top: 0;
    left: calc(-100% - 80px);
    background: #fff;
    color: #333333;
    box-shadow: 80px 0 rgba(38, 98, 213, 0.3);
    z-index: 999;
  }
  .menu-content .menu-title {
    margin: 10px 20px;
    font-size: 2.2rem;
    color: #333333;
    text-align: left;
    font-weight: bold;
  }
  .menu-content li a {
    color: #333333;
    margin: 0px 5px;
    border-bottom: 0.5px solid #2662d5;
    text-decoration: none;
    display: block;
  }
  .menu-content li {
    width: 100%;
    text-align: left;
  } 
  .menu-content.open {
    left: 0; 
  }
  }
</style>