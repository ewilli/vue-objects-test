<template>
  <div class="hello">
    <p>ParentRef: {{ parentref }}</p>
    <child-reference :valueReference="parentref" />
    <hr />
    <p>ParentVal: {{ parentval }}</p>
    <child-emit :initialValue="initval" @update="updateVal" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

import ChildEmit from "../components/ChildEmit.vue";
import ChildReference from "../components/ChildReference.vue";

@Component({ components: { ChildReference, ChildEmit } })
export default class Home extends Vue {
  initval = { cat: "Mitzi", dog: "Doggy", other: "Mr. Bear" };

  parentref = { ...this.initval };
  parentval = {};

  updateVal(val: object) {
    console.log(val);
    this.parentval = val;
  }
}
</script>

//https://stackoverflow.com/questions/40408096/whats-the-correct-way-to-pass-props-as-initial-data-in-vue-js-2
