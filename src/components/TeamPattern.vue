<template>
  <svg
    width="1920"
    height="1080"
    viewBox="0 0 1920 1080"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <g
      @mouseover="onMouseOver('Boris')"
      @mouseleave="onMouseLeave"
      @click="onClick('Boris')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="595"
        y="-20"
      >
        <Transition>
          <TeamAbout :data="BorisData" v-if="activeItem === 'Boris'" />
        </Transition>
      </foreignObject>
      <rect
        x="611.921"
        y="197"
        width="196.995"
        height="707"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Egor')"
      @mouseleave="onMouseLeave"
      @click="onClick('Egor')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="1205"
        y="320"
      >
        <Transition>
          <TeamAbout :data="EgorData" v-if="activeItem === 'Egor'" />
        </Transition>
      </foreignObject>
      <rect
        x="1215.28"
        y="539"
        width="257.902"
        height="419"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Kirill')"
      @mouseleave="onMouseLeave"
      @click="onClick('Kirill')"
      v-if="isKirillVisible"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="1255"
        y="0"
      >
        <Transition>
          <TeamAbout :data="KirillData" v-if="activeItem === 'Kirill'" />
        </Transition>
      </foreignObject>
      <rect
        x="1294.27"
        y="210"
        width="200.802"
        height="317"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Dima')"
      @mouseleave="onMouseLeave"
      @click="onClick('Dima')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="1475"
        y="-30"
      >
        <Transition>
          <TeamAbout :data="DimaData" v-if="activeItem === 'Dima'" />
        </Transition>
      </foreignObject>
      <rect
        x="1511.25"
        y="197"
        width="180.817"
        height="659"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Max')"
      @mouseleave="onMouseLeave"
      @click="onClick('Max')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="1080"
        y="-20"
      >
        <Transition>
          <TeamAbout :data="MaxData" v-if="activeItem === 'Max'" />
        </Transition>
      </foreignObject>
      <rect
        x="1080.14"
        y="210"
        width="204.608"
        height="317"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Victor')"
      @mouseleave="onMouseLeave"
      @click="onClick('Victor')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="135"
        y="-30"
      >
        <Transition>
          <TeamAbout :data="VictorData" v-if="activeItem === 'Victor'" />
        </Transition>
      </foreignObject>
      <path
        d="M146.557 177H355.923V658H146.557V177Z"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Olya')"
      @mouseleave="onMouseLeave"
      @click="onClick('Olya')"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="373"
        y="-40"
      >
        <Transition>
          <TeamAbout :data="OlyaData" v-if="activeItem === 'Olya'" />
        </Transition>
      </foreignObject>
      <rect
        x="373.053"
        y="156"
        width="222.69"
        height="320"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
    <g
      @mouseover="onMouseOver('Roman')"
      @mouseleave="onMouseLeave"
      @click="onClick('Roman')"
      v-if="isRomanVisible"
    >
      <foreignObject
        v-if="!isTouchScreen && browserName !== 'safari'"
        width="250"
        height="250"
        x="755"
        y="-20"
      >
        <Transition>
          <TeamAbout :data="RomanData" v-if="activeItem === 'Roman'" />
        </Transition>
      </foreignObject>
      <rect
        x="829.853"
        y="197"
        width="146.557"
        height="673"
        fill="black"
        fill-opacity="0.01"
      />
    </g>
  </svg>
</template>
<script setup>
  import { ref, onMounted } from 'vue';
  import { TeamAbout } from '@/components';
  import { useWindowSize } from '@vueuse/core';

  const emit = defineEmits(['hover', 'safari', 'click']);

  const { width, height } = useWindowSize();

  const browserName = ref(null);

  function fnBrowserDetect() {
    let userAgent = navigator.userAgent;

    if (userAgent.match(/chrome|chromium|crios/i)) {
      browserName.value = 'chrome';
    } else if (userAgent.match(/firefox|fxios/i)) {
      browserName.value = 'firefox';
    } else if (userAgent.match(/safari/i)) {
      browserName.value = 'safari';
    } else if (userAgent.match(/opr\//i)) {
      browserName.value = 'opera';
    } else if (userAgent.match(/edg/i)) {
      browserName.value = 'edge';
    } else {
      browserName.value = 'No browser detection';
    }
  }

  onMounted(() => {
    fnBrowserDetect();
  });

  const isTouchScreen = ref(null);

  const CheckTouchScreen = () => {
    isTouchScreen.value =
      'ontouchstart' in window ||
      navigator.maxTouchPoints > 0 ||
      navigator.msMaxTouchPoints > 0;
  };
  CheckTouchScreen();

  const activeItem = ref(null);

  const isKirillVisible = ref(true);
  const isRomanVisible = ref(true);

  const onClick = (item) => {
    if (isTouchScreen.value || browserName.value === 'safari') {
      // тач ИЛИ сафари
      activeItem.value = item;
      emit('click', item);
      emit('safari');
    }
  };

  const onMouseOver = (item) => {
    activeItem.value = item;
    if (!isTouchScreen.value) {
      activeItem.value === 'Egor'
        ? (isKirillVisible.value = false)
        : (isKirillVisible.value = true);
      activeItem.value === 'Boris'
        ? (isRomanVisible.value = false)
        : (isRomanVisible.value = true);
    }
    if (browserName.value === 'safari') {
      // === safari
      emit('safari');
      emit('hover', item);
    } else {
      emit('hover', item);
      emit('click', item);
    }
  };
  const onMouseLeave = () => {
    if (browserName.value !== 'safari') {
      // НЕ сафари
      emit('hover', null);
      activeItem.value = null;
      isKirillVisible.value = true;
      isRomanVisible.value = true;
    }
  };

  const BorisData = {
    name: 'Bogatiy Borya',
    role: 'CEO',
    twitter: 'https://twitter.com/bogatiy_borya',
    linkedin: 'https://www.linkedin.com/mwlite/in/bogatiy-borya',
    instagram: 'https://www.instagram.com/bogatiy_borya/',
  };
  const EgorData = {
    name: 'Egor Vasilev',
    role: 'IOS Dev',
    twitter: 'https://twitter.com/leofriskey',
    linkedin: 'https://linkedin.com/in/leofriskey',
  };
  const KirillData = {
    name: 'Kirill Drozdov',
    role: 'IOS Dev',
    twitter: 'https://twitter.com/kirikikoki',
    linkedin:
      'https://www.linkedin.com/in/%D0%BA%D0%B8%D1%80%D0%B8%D0%BB%D0%BB-%D0%B4%D1%80%D0%BE%D0%B7%D0%B4%D0%BE%D0%B2-7ba685227',
  };
  const DimaData = {
    name: 'Dmitriy Spichakov',
    role: 'Head of IOS Dev',
    linkedin: 'https://www.linkedin.com/in/dmitrii-spichakov-7761b623b/',
  };
  const MaxData = {
    name: 'Maxim Khlestkin',
    role: 'CTO',
    twitter: 'https://twitter.com/rendering___/',
    linkedin: 'https://www.linkedin.com/in/max-pavlovich-670874195',
  };
  const VictorData = {
    name: 'Victor Pirozhenko',
    role: 'Head of Design',
    twitter: 'https://twitter.com/pirzhnk',
    linkedin: 'https://www.linkedin.com/in/victor-pirozhenko-158054265/',
  };
  const OlyaData = {
    name: 'Panina Olga',
    role: 'UX/UI Designer',
    linkedin: 'https://www.linkedin.com/in/olga-panina-099073265/',
  };
  const RomanData = {
    name: 'Roman Shramko ',
    role: 'COO',
    twitter: 'https://twitter.com/xlsrio',
    linkedin: 'https://www.linkedin.com/in/roman-shramko-0711a0237/',
  };
</script>
<style scoped>
  g {
    display: block;
    position: relative;
    z-index: 2;
  }
</style>