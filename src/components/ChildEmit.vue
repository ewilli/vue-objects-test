<template>
  <div class="child-emit">
    <h4>Child with emit</h4>
    <p>Initial value:</p>
    {{ initialValue }}
    <p>Value of child:</p>
    {{ valueEmit }}
    <br />
    <br />
    Value cat:
    <input
      type="text"
      @input="$emit('update', valueEmit)"
      v-model="valueEmit.cat"
    />
    <br />
    Value dog:<input
      type="text"
      @input="$emit('update', valueEmit)"
      v-model="valueEmit.dog"
    />
    <!-- <button @click="$emit('update', valueEmit)">Save</button> -->
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({ name: "ChildEmit" })
export default class HelloWorld extends Vue {
  @Prop() initialValue!: object;

  valueEmit = { ...this.initialValue };
}
</script>

<style scoped>
.child-emit {
  color: #b99d42;
}
</style>
