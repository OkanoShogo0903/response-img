<template>
  <v-btn
    icon
    class="common"
    :class="is_fav ? 'front' : 'back' "
    v-on:click.stop="$emit('fav-click');"
    >
    <v-icon>mdi-heart</v-icon>
  </v-btn>
</template>

<script lang="ts">
  import {Component, Prop, Vue} from "vue-property-decorator";

  @Component
  export default class ImageFrame extends Vue {
    @Prop()
    public is_fav?: Boolean; // 手軽に使えるように?にした。undefinedのときの色はback_colorになる。
    // TODO: Favが付いても色が黒い
  }
</script>

<style scoped>
.common{
  position:absolute;
  top: -4px;
  right:-4px;
}
.front{
  color:E03B5E;
}
.back{
  color:BDBDBD;
  opacity: 0.4;
}
</style>
