<template>
  <Portal to="popup">
    <PopupBase :label="label" @close="$emit('close')">
      <PopupOverlay slot="backdrop"/>
      <div class="article-pop-up-content">
        <slot/>
        <div class="article-pop-up-button">
        </div>
      </div>
    </PopupBase>
  </Portal>
</template>

<script>
import PopupBase from './PopupBase.vue';
import PopupOverlay from './PopupOverlay.vue';

export default {
  name: 'PopupModalDialog',
  props: {
    label: {
      required: true,
      type: String
    },
  },
  components: {
    PopupBase,
    PopupOverlay,
  },
}
</script>

<style>
.article-pop-up-content {
  background-color: #fff;
  padding: 2em;
  max-width: 80%;
  max-height: 80%;
}

.article-pop-up-button {
  margin-top: 1em;
  text-align: right;
}
</style>
