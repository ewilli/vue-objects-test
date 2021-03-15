<template>
  <div class="child-reference">
    <h4>Child with reference as prop</h4>
    <p>Value of child:</p>
    {{ valueReference }}
    <br />
    <br />
    Value cat: <input type="text" v-model="valueReference.cat" />
    <br />
    Value dog:<input type="text" v-model="valueReference.dog" />
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({ name: "ChildReference" })
export default class HelloWorld extends Vue {
  @Prop() private valueReference!: object;

}
</script>

<style scoped>
.child-reference {
  color: #42b983;
}
</style>
