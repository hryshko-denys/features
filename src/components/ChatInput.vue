<template>
<div>
  <form class="chat">
    <div class="chat__wrapper">
      <VuePerfectScrollbar class="chat__scrollbar">
        <div
          class="chat__input"
          contenteditable="true"
          @input="handleInput"
          @mouseover="isReactionPanelShown = true"
          ref="chatInput"
          data-placeholder="Write a message"
        ></div>
      </VuePerfectScrollbar>
      <control-panel />
      <reaction-panel :isReactionPanelShown="isReactionPanelShown" />
    </div>
  </form>

  <div v-html="message"></div>
</div>

</template>

<script>
import VuePerfectScrollbar from 'vue-perfect-scrollbar'
import ControlPanel from '@/components/ControlPanel.vue'
import ReactionPanel from '@/components/ReactionPanel.vue'

export default {
  components: {
    ControlPanel,
    VuePerfectScrollbar,
    ReactionPanel,
  },
  data() {
    return {
      message: null,
      isReactionPanelShown: true,
    }
  },
  methods: {
    handleInput() {
      // this.$refs.chatInput.innerText
      this.message = this.$refs.chatInput.innerHTML

      if (this.message === '<div><br></div>' || this.message === '<br>') {
        this.$refs.chatInput.innerHTML = ''
        this.message = ''
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.chat {
  position: relative;
  width: 100%;
  height: 700px;
  padding: 0 20px;
  border: 1px solid orange;

  &__wrapper {
    position: absolute;
    bottom: 0;
    width: 700px;
  }

  &__input {
    padding: 10px;
    outline: none;
  }

  &__scrollbar {
    max-height: 300px;
    border-radius: 6px;
    box-shadow: 0px 7px 20px rgba(86, 134, 179, 0.28);
  }
}

[contentEditable='true']:empty::before {
  content: attr(data-placeholder);
  color: grey;
  pointer-events: none;
  display: block;
}
</style>
