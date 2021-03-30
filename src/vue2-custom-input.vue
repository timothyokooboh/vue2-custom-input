<template>
  <div class="input-container">
    <label 
      :for="id" 
      class="label"
      :class="{'sr-only': srOnly}"
      >
        {{label}}
    </label>

    <input
      v-if="required"
      :key="'value is required'"
      required
      :value='value'
      @input='$emit("input", $event.target.value)'
      :type="type"
      :id="id"
      :placeholder="placeholder"
      class="input"
      :style="borderColor(color)"
    />

    <input
      v-else
      :key="'value is not required'"
      :value='value'
      @input='$emit("input", $event.target.value)'
      :type="type"
      :id="id"
      :placeholder="placeholder"
      class="input"
      :style="borderColor(color)"
    />
    <slot name="error-message" />
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: '#23b38a'
    },
    id: String,
    label: String,
    value: null,
    placeholder: String,
    required: {
      type: Boolean,
      default: true
    },
    srOnly: {
      type: Boolean,
      default: false
    },
    type: {
      type: String,
      default: 'text'
    }
  },

  computed: {
    borderColor: () => (color) => ({
      'border-color': color
    })
  }
}
</script>

<style scoped>
  .input-container {
    margin-bottom: 16px;
    width: 100%;
  }

  .label {
    display: block;
    padding-bottom: 8px
  }

  .input {
    border-width: 1px;
    border-style: solid;
    padding: 8px 16px; 
    outline: none; 
    border-radius: 10px;
    width: 100%;
  }

  .input:focus {
    border-width: 2px;
  }

  .sr-only {
    position: absolute;
    left: -10000px;
    top: auto;
    width: 1px;
    height: 1px;
    overflow: hidden
  }
</style>