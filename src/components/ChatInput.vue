<template>
  <div>
    <form class="chat">
      <div
        class="chat__message chat__message_left"
        @mouseover="isReactionPanelShown = true"
        @mouseleave="isReactionPanelShown = false"
      >
        left
        <reaction-panel :isReactionPanelShown="isReactionPanelShown" />
      </div>
      <div
        class="chat__message chat__message_right"
        @mouseover="isReactionPanelShown = true"
        @mouseleave="isReactionPanelShown = false"
      >
        right
        <reaction-panel :isReactionPanelShown="isReactionPanelShown" />
      </div>
      <div class="chat__wrapper">
        <VuePerfectScrollbar class="chat__scrollbar">
          <div
            class="chat__input"
            contenteditable="true"
            @input="handleInput"
            ref="chatInput"
            data-placeholder="Write a message"
          ></div>
        </VuePerfectScrollbar>
        <control-panel />
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
      isReactionPanelShown: false,
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

  background-color: lightgrey;
  border: 1px solid orange;

  &__wrapper {
    position: absolute;
    bottom: 0;
    width: 700px;
  }

  &__input {
    padding: 10px;

    background-color: #fff;
    outline: none;
  }

  &__scrollbar {
    max-height: 300px;
    border-radius: 6px;
    box-shadow: 0px 7px 20px rgba(86, 134, 179, 0.28);
  }

  //Reaction panel
  &__message {
    position: relative;
    width: 200px;
    height: 50px;
    padding: 5px;

    background-color: #fff;
    border: 1px solid grey;
    border-radius: 10px;
  }

  &__message_left {
    margin-top: 50px;
  }

  &__message_right {
    margin: 150px 0 0 500px;
  }
}

[contentEditable='true']:empty::before {
  content: attr(data-placeholder);
  color: grey;
  pointer-events: none;
  display: block;
}
</style>
