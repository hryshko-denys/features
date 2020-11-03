<template>
<div>
  <div class="control-panel">
    <div class="control-panel__buttons">
      <button class="control-panel__btn btn">
        <svg
          width="19"
          height="18"
          viewBox="0 0 19 18"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M17.6941 2.78696C18.1071 3.19985 18.1071 3.86682 17.6941 4.2797L15.6189 6.35472L11.6484 2.38466L13.7237 0.309649C13.9215 0.111408 14.19 0 14.4701 0C14.7502 0 15.0187 0.111408 15.2166 0.309649L17.6941 2.78696ZM10.5879 3.44383L0 14.0306V18.0007H3.97046L14.5584 7.41388L10.5879 3.44383ZM3.09167 15.8844H2.11758V14.9104L10.5879 6.44098L11.562 7.41496L3.09167 15.8844Z"
            fill="#274D70"
          />
        </svg>
      </button>
      <button class="control-panel__btn btn">
        <svg
          width="22"
          height="11"
          viewBox="0 0 22 11"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M5 1.5L16.5 1.5C18.71 1.5 20.5 3.29 20.5 5.5C20.5 7.71 18.71 9.5 16.5 9.5L4 9.5C2.62 9.5 1.5 8.38 1.5 7C1.5 5.62 2.62 4.5 4 4.5L14.5 4.5C15.05 4.5 15.5 4.95 15.5 5.5C15.5 6.05 15.05 6.5 14.5 6.5L5 6.5L5 8L14.5 8C15.88 8 17 6.88 17 5.5C17 4.12 15.88 3 14.5 3L4 3C1.79 3 0 4.79 0 7C0 9.21 1.79 11 4 11L16.5 11C19.54 11 22 8.54 22 5.5C22 2.46 19.54 3.57628e-07 16.5 3.57628e-07L5 3.57628e-07V1.5Z"
            fill="#274D70"
          />
        </svg>
      </button>
      <button class="control-panel__btn btn">
        <svg
          width="18"
          height="18"
          viewBox="0 0 18 18"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M8.991 0C4.023 0 0 4.032 0 9C0 13.968 4.023 18 8.991 18C13.968 18 18 13.968 18 9C18 4.032 13.968 0 8.991 0ZM5.85 5.4C5.10442 5.4 4.5 6.00442 4.5 6.75C4.5 7.49559 5.10442 8.1 5.85 8.1C6.59559 8.1 7.2 7.49558 7.2 6.75C7.2 6.00442 6.59559 5.4 5.85 5.4ZM12.15 5.4C11.4044 5.4 10.8 6.00442 10.8 6.75C10.8 7.49559 11.4044 8.1 12.15 8.1C12.8956 8.1 13.5 7.49558 13.5 6.75C13.5 6.00442 12.8956 5.4 12.15 5.4ZM5.89519 10.8C6.52519 11.871 7.66819 12.6 9.00019 12.6C10.3322 12.6 11.4752 11.871 12.1052 10.8H13.6082C12.8882 12.645 11.0972 13.95 9.00019 13.95C6.90319 13.95 5.11219 12.645 4.39219 10.8H5.89519ZM1.8 9C1.8 12.978 5.022 16.2 9 16.2C12.978 16.2 16.2 12.978 16.2 9C16.2 5.022 12.978 1.8 9 1.8C5.022 1.8 1.8 5.022 1.8 9Z"
            fill="#274D70"
          />
        </svg>
      </button>
    </div>
    <button class="control-panel__submit btn">
      <svg
        width="22"
        height="20"
        viewBox="0 0 22 20"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M0.387021 0.000244141L0.37903 6.09053C0.377751 7.06523 1.07929 7.8989 2.03987 8.06419L13.2913 10.0002L2.03987 11.9363C1.07929 12.1016 0.377751 12.9353 0.37903 13.91L0.387021 20.0002L21.8062 10.0002L0.387021 0.000244141Z"
          fill="#376289"
        />
      </svg>
    </button>
  </div>
</div>

</template>

<script></script>

<style lang="scss" scoped>
.control-panel {
  display: flex;
  justify-content: space-between;
  padding: 10px 5px;

  &__buttons {
    display: flex;
    align-items: center;
  }

  &__btn:not(:last-child) {
    margin-right: 20px;
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
