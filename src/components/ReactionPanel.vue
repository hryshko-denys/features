<template>
  <div
    v-if="isReactionPanelShown"
    class="reaction-panel"
    :class="{ 'reaction-panel_hover': isPanelOpen }"
    @mouseover="isPanelOpen = true"
    @mouseleave="isPanelOpen = false"
  >
    <div class="reaction-panel__smiles">
      <smile
        v-for="smile in smiles"
        :key="smile.id"
        :id="smile.id"
        :isPanelOpen="isPanelOpen"
      />
    </div>
    <button type="button" class="reaction-panel__btn btn" @click="isActionsShown = !isActionsShown">
      <svg width="16" height="4" viewBox="0 0 16 4" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M14 4C15.1 4 16 3.1 16 2C16 0.9 15.1 -7.86805e-08 14 -1.74846e-07C12.9 -2.71011e-07 12 0.9 12 2C12 3.1 12.9 4 14 4ZM2 4C3.1 4 4 3.1 4 2C4 0.899999 3.1 -1.12775e-06 2 -1.22392e-06C0.9 -1.32008e-06 2.71011e-07 0.899999 1.74846e-07 2C7.86805e-08 3.1 0.9 4 2 4ZM10 2C10 3.1 9.1 4 8 4C6.9 4 6 3.1 6 2C6 0.899999 6.9 -7.95547e-07 8 -6.99382e-07C9.1 -6.03217e-07 10 0.9 10 2Z" fill="#274D70"/>
      </svg>
    </button>
    <message-actions v-if="isActionsShown && isReactionPanelShown"/>
  </div>
</template>

<script>
import Smile from '@/components/Smile.vue'
import MessageActions from '@/components/MessageActions.vue'

export default {
  components: {
    Smile,
    MessageActions,
  },
  props: {
    isReactionPanelShown: Boolean,
  },
  data: () => ({
    isPanelOpen: false,
    isActionsShown: false,
    opacity: 1,
    smiles: [
      {
        id: 1,
        opacity: '1',
      },
      {
        id: 2,
        opacity: '1',
      },
      {
        id: 3,
        opacity: '1',
      },
      {
        id: 4,
        opacity: '1',
      },
      {
        id: 5,
        opacity: '1',
      },
    ],
  }),
  methods: {
    onEnterSmile(id) {
      const currentSmile = this.smiles.find(smile => smile.id === id)
      console.log(currentSmile.opacity)
      currentSmile.opacity = '1'
      console.log(currentSmile.opacity)
    },
  },
}
</script>

<style lang="scss" scoped>
.reaction-panel {
  position: absolute;
  top: -20px;
  right: 5px;

  display: flex;
  justify-content: space-between;
  width: 200px;
  padding: 3px;

  background-color: rgba(256, 256, 256, 1);
  border: 1px solid grey;
  border-radius: 6px;

  &__smiles {
    display: flex;
    justify-items: center;
  }

  &__btn {
    position: relative;
    display: flex;
    align-items: center;
  }

  &__btn::after {
    content: "";
    position: absolute;
    top: calc(50% - 8.5px);
    left: -10px;
    display: block;

    width: 1px;
    height: 17px;

    background-color: #a6bacd;
  }
}

.btn {
  margin: 0;
  padding: 0;
  background: transparent;
  border: none;
  cursor: pointer;
}
</style>
