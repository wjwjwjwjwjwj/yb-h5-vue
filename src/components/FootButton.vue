<template>
  <div class="foot-button-container" @click="onClick">
    {{btnText}}
  </div>
</template>

<script lang="ts">
import { Prop, Component, Vue } from 'vue-property-decorator';

@Component
export default class FootButton extends Vue {
  @Prop({ default: '提交' }) private btnText!: string;

  private onClick() {
    this.$emit('onClick');
  }
}
</script>

<style lang="scss" scoped>
  @import "../assets/css/common";
  .foot-button-container {
    @include  font-dpr(30px);
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    line-height: px2rem(88px);
    height: px2rem(88px);
    background: $bgblue;
    color: $fontfff;
    text-align: center;
  }
</style>
