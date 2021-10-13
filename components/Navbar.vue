<template>
  <div class="d-flex flex-column align-items-center">
    <b-button class="px-0 mt-5 mb-2 button-search">
        <b-icon icon="search"></b-icon>
    </b-button>
    <b-button :class="index == 3 ? 'mt-5' : ''" class="button-select px-0 my-2" :style="`${index == 0 ? 'background:#1C2833' : 'background:#1B2631 '}; width:40px`" :variant="'dark'" v-for="(icon, index) in icons" :key="index">
        <b-icon :icon="icon.icon"></b-icon>
    </b-button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            icons:[
                {icon:'house-door'},
                {icon:'collection-play'},
                {icon:'bullseye'},
                {icon:'clock'},
                {icon:'soundwave'},
                {icon:'heart-fill'},
                {icon:'plus-circle-fill'}
            ]
        }
    },
}
</script>
<style>
    .button-search{
        width: 45px;
        border-radius: 15px;
        height: 45px;
        background:#17202A;
    }
    .button-select{
        border-radius: 10px;
    }
</style>