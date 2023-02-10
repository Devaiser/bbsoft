<template>
  <header class="header">
    <div class="container header__container">
      <div class="menu">
        <div
          class="menu__icon"
          @click="toggleMenu"
          :class="{ active: isMenuVisible }"
        >
          <span></span>
        </div>
        <nav class="menu__body" :class="{ active: isMenuVisible }">
          <ul class="menu__list">
            <li>
              <a class="menu__link disabled" target="_blank" href="/"
                >BBAPP (Coming Soon)</a
              >
            </li>
            <li>
              <a
                class="menu__link"
                target="_blank"
                href="https://bbsoft-io.gitbook.io/bbsoft-ecosystem/bbecosystem/endorsed-by-bbsoft"
                >ENDORSED BY BBSOFT</a
              >
            </li>
            <li>
              <a
                href="https://bbsoft-io.gitbook.io/bbsoft-ecosystem/intro/introduction"
                target="_blank"
                class="menu__link"
                >DOCUMENTATION</a
              >
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>
<script setup>
  import { ref } from 'vue';

  const isMenuVisible = ref(false);

  const toggleMenu = () => {
    isMenuVisible.value = !isMenuVisible.value;
    if (isMenuVisible.value) {
      document.body.classList.add('lock');
    } else {
      document.body.classList.remove('lock');
    }
  };
</script>
<style scoped>
  .header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    box-sizing: border-box;
    padding: 25px 46px;
    z-index: 5;
  }
  .header__container {
    display: flex;
    justify-content: flex-end;
  }
  .menu__list > li {
    text-transform: uppercase;
    color: #888686;
    font-weight: 600;
    font-size: 12px;
    line-height: 1.25;
    font-family: 'Inter', sans-serif;
  }
  .menu__list > li:not(:last-child) {
    margin-right: 30px;
  }
  .menu__list > li a {
    color: inherit;
  }
  .header__social {
    display: flex;
    align-items: center;
  }
  .menu__icon {
    display: none;
  }
  .disabled {
    pointer-events: none;
  }
  @media (min-width: 767px) {
    .menu__body {
      display: flex;
    }
    .menu__list {
      display: flex;
      align-items: center;
    }
  }
  @media (max-width: 1200px) {
    .menu__list li:not(:last-child) {
      margin-right: 60px;
    }
  }
  @media (max-width: 992px) {
    .menu__list li:not(:last-child) {
      margin-right: 40px;
    }
  }
  @media (max-width: 768px) {
    .header {
      padding: 25px 0;
    }
    .header__container {
      padding: 0 20px;
    }
    .header {
      height: 78px;
    }
    .menu__icon {
      z-index: 15;
      display: block;
      position: relative;
      width: 37px;
      height: 26px;
      cursor: pointer;
    }
    .menu__icon::before,
    .menu__icon::after,
    .menu__icon span {
      left: 0;
      position: absolute;
      width: 100%;
      height: 3px;
      transition: all 0.3s ease-in-out 0s;
      background-color: #fff;
    }
    .menu__icon::before,
    .menu__icon::after {
      content: '';
    }
    .menu__icon::before {
      top: 0;
    }
    .menu__icon::after {
      bottom: 0;
    }
    .menu__icon span {
      top: 50%;
      transform: scale(1) translate(0, -50%);
    }

    .menu__icon.active span {
      transform: scale(0) translate(0, -50%);
    }
    .menu__icon.active::before {
      top: 50%;
      transform: rotate(-45deg) translate(0, -50%);
    }
    .menu__icon.active::after {
      bottom: 50%;
      transform: rotate(45deg) translate(0, 50%);
    }
    .menu__body {
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      position: fixed;
      top: 0;
      left: 100%;
      width: 100%;
      height: 100vh;
      background: rgba(0, 0, 0, 0.5);
      padding: 100px 74px 160px 55px;
      box-sizing: border-box;
      transition: left 0.5s ease-in-out 0s;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      overflow: auto;
    }
    .menu__body.active {
      left: 0;
    }
    .menu__list {
      margin-right: 0;
    }
    .menu__list li:not(:last-child) {
      margin-right: 0;
    }
    .menu__list li {
      margin-bottom: 32px;
      text-align: end;
      font-size: 20px;
    }
    .header__social {
      justify-content: flex-end;
    }
  }
  @media (max-width: 556px) {
    .menu__list li {
      font-size: 18px;
    }
  }
  @media (max-width: 360px) {
    .menu__list li {
      font-size: 16px;
    }
    .menu__body {
      padding: 100px 44px 160px 55px;
    }
  }
</style>