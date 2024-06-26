<template>
  <component
    :is="tag"
    :class="[
      'alcor-button',
      {
        flat,
        alternative,
        access,
        orange,
        danger,
        outline,
        bordered,
        transparent,
        iconOnly,
        iconOnlyAlt,
        round,
        big,
        compact,
      },
    ]"
    @click="$emit('click')"
    v-bind="$attrs"
  >
    <div class="inner">
      <slot />
    </div>
  </component>
</template>

<script>
export default {
  name: 'AlcorButton',
  props: {
    flat: {
      default: false,
      type: Boolean,
    },
    alternative: {
      default: false,
      type: Boolean,
    },
    access: {
      default: false,
      type: Boolean,
    },
    danger: {
      default: false,
      type: Boolean,
    },
    orange: {
      default: false,
      type: Boolean,
    },
    outline: {
      default: false,
      type: Boolean,
    },
    transparent: {
      default: false,
      type: Boolean,
    },
    round: {
      default: false,
      type: Boolean,
    },
    bordered: {
      default: false,
      type: Boolean,
    },
    compact: {
      default: false,
      type: Boolean,
    },
    big: {
      default: false,
      type: Boolean,
    },
    iconOnly: {
      default: false,
      type: Boolean,
    },
    iconOnlyAlt: {
      default: false,
      type: Boolean,
    },
    tag: {
      default: 'button',
    },
  },
}
</script>

<style scoped lang="scss">
button {
  border: none;
  font-family: 'Roboto', sans-serif;
  color: inherit;
  font-size: 1rem;
  cursor: pointer;
}

.alcor-button {
  padding: 6px 10px;
  border-radius: var(--radius);
  color: var(--text-default);
  background: var(--btn-default);
  transition: all 0.3s;
  display: inline-block;

  &.alternative {
    background: var(--btn-alternative);
  }

  &.active {
    background: var(--hover);
  }
  &:disabled {
    cursor: not-allowed;
    pointer-events: none;
  }
}

.alcor-button .vs-icon {
  margin: 0 2px;
}

.alcor-button.flat {
  background: transparent;
}

.alcor-button:hover:not([disabled]) {
  background: var(--hover);
}

.alcor-button.flat:hover {
  box-shadow: none;
}

.alcor-button.round {
  border-radius: 40px;
  padding: 6px 14px;
}

.alcor-button.outline {
  background: transparent;
  border: 1px solid var(--main-action-green);
  color: var(--main-action-green);
}

.alcor-button.outline:hover {
  box-shadow: 0px 0px 30px 0px #54a05466 inset;
  background: var(--btn-outline);
}

.alcor-button.bordered {
  background: transparent !important;
  border: 1px solid var(--border-color);
  border-radius: 6px;
  &:hover {
    border: 1px solid var(--border-2-color);
  }
}

.alcor-button.orange {
  background: linear-gradient(90deg, #854000 0%, #ff8a00 100%);
  border: 1px solid #854000;
}

.alcor-button.orange:hover {
  background: transparent;
  border: 1px solid #ff8a00;
  color: #ff8a00;
}

.alcor-button.orange:disabled {
  background: transparent;
  border: 1px solid #854000;
  color: #854000;
}

.alcor-button.danger {
  background: var(--main-action-red);
  border: 1px solid var(--main-action-red);
}

.alcor-button.danger:hover {
  background: transparent;
  color: var(--main-action-red);
  border: 1px solid var(--main-action-red);
}

.alcor-button.danger:disabled {
  background: var(--main-action-red);
  border: 1px solid var(--main-action-red);
  color: var(--text-theme);
  filter: brightness(50%);
  cursor: not-allowed;
}

.alcor-button.access {
  background: var(--main-action-green);
  border: 1px solid var(--main-action-green);
  color: var(--text-theme);
}

.alcor-button.access:hover {
  background: transparent;
  color: var(--main-action-green);
  border: 1px solid var(--main-action-green);
}

.alcor-button.access:disabled {
  background: var(--main-action-green);
  border: 1px solid var(--main-action-green);
  color: var(--text-theme);
  filter: brightness(50%);
  cursor: not-allowed;
}

.alcor-button.compact {
  padding: 4px 12px;
}

.alcor-button.big {
  padding: 12px;
  width: 135px;
  border-radius: var(--radius-2);
}

.inner {
  display: flex;
  gap: 10px;
  justify-content: center;
  align-items: center;
  font-size: 14px;

  width: 100%;
  white-space: nowrap;
  overflow: hidden;
  text-align: center;
  text-overflow: ellipsis;
}

.iconOnly {
  width: 32px;
  height: 32px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.alcor-button.iconOnlyAlt {
  width: 36px;
  height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
