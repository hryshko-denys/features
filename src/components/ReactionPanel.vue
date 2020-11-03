<template>
  <div
    v-if="isReactionPanelShown"
    class="reaction-panel"
    :class="{ 'reaction-panel_hover': isOnPanel }"
    @mouseover="onEnterBlock"
    @mouseleave="isOnPanel = false"
  >
    <div class="reaction-panel__smiles">
      <smile
        v-for="smile in smiles"
        :key="smile.id"
        :id="smile.id"
        :opacity="smile.opacity"
        @mouseover="onEnterSmile(smile.id)"
        @mouseleave="isOnPanel = false"
      />
    </div>
  </div>
</template>

<script>
import Smile from '@/components/Smile.vue'

export default {
  components: {
    Smile,
  },
  props: {
    isReactionPanelShown: Boolean,
  },
  data: () => ({
    isOnPanel: false,
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
  mounted() {
    console.log(this.smiles)
  },
  methods: {
    onEnterBlock() {
      this.isOnPanel = true
      this.smiles.forEach(smile => (smile.opacity = '0.1'))
    },
    onEnterSmile(id) {
      const currentSmile = this.smiles.find(smile => smile.id === id)
      console.log(currentSmile, this.smiles, id)
      currentSmile.opacity = '1'
    },
  },
}
</script>

<style lang="scss" scoped>
.reaction-panel {
  position: absolute;
  top: -20px;
  right: 5px;
  width: 200px;
  padding: 3px;

  background-color: rgba(51, 170, 51, 1);
  border-radius: 6px;

  &_hover {
    background-color: rgba(51, 170, 51, 0.7);
  }

  &__smiles {
    display: flex;
  }
}
</style>
