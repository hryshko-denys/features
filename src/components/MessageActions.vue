<template>
  <ul class="actions">
    <li class="actions__item">
      <button>Add</button>
    </li>
    <li class="actions__item">
      <button>Leave group</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    isReactionPanelShown: Boolean,
  },
}
</script>

<style lang="scss" scoped>
.actions {
  position: absolute;
  bottom: -95px;
  right: 0;

  box-sizing: border-box;
  margin: 0;
  padding: 5px 0;

  border: 1px solid grey;
  background-color: #fff;
  list-style: none;

  &__item {
    position: relative;
    padding: 10px 15px 10px 50px;
    margin: 0;

    cursor: pointer;
  }

  &__item:not(:last-child) {
    margin-bottom: 5px;
  }

  &__item::after {
    content: '';
    position: absolute;
    top: calc(50% - 12px);
    left: 5px;
    display: block;
  }

  &__item:first-child::after {
    width: 30px;
    height: 24px;

    background-image: url('../assets/smiles/add.svg');
  }

  &__item:nth-child(2)::after {
    width: 24px;
    height: 24px;

    background-image: url('../assets/smiles/leave.svg');
  }
}
</style>
