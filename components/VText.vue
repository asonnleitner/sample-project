<template>
  <component :is="tag" v-on="$listeners" v-bind="$attrs"
     :class="{
    ['color-' + color]: color,
    ['size-' + size]: size
  }">
    <slot/>
  </component>
</template>

<script>
export default {
  name: 'VText',

  props: {
    tag: {
      type: String,
      default: 'p',
      validator(value) {
        return ['p', 'span', 'h1', 'h2', 'h3', 'h4', 'h5', 'h6', 'h7'].includes(value)
      }
    },

    color: {
      type: String,
      default: 'black',
      validator(value) {
        return ['black', 'white', 'red', 'green', 'blue'].includes(value)
      }
    },

    size: {
      type: String,
      default: 'md',
      validator(value) {
        return ['sm', 'md', 'lg', 'xl'].includes(value)
      }
    }
  }
}
</script>

<style>
.color-black {
  color: black;
}

.color-white {
  color: white;
}

.color-red {
  color: red;
}

.color-green {
  color: green;
}

.color-blue {
  color: blue;
}

.size-sm {
  font-size: 0.75rem;
}

.size-md {
  font-size: 0.875rem;
}

.size-lg {
  font-size: 1rem;
}

.size-xl {
  font-size: 1.125rem
}
</style>
