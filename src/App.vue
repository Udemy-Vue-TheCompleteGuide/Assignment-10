<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Directives Exercise</h1>
        <!-- Exercise -->
        <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
        <button class="btn btn-success" v-my-on:click="onClick" v-my-on:leave="onMouseLeave">Click Me</button>
        <button class="btn btn-success" v-my-on:dblclick="onDblClick">Double Click Me</button>
      </div>
    </div>
  </div>
</template>

<script>
import MyOnDirective from "@/directives/MyOn.directive.js";

export default {
  name: 'App',
  directives: {
    'MyOn': MyOnDirective,
    // 'MyOn1': {
    //   bind: (el: HTMLBaseElement, binding: any, vnode) => { /* Implementation...*/ }
    // }
  },
  methods: {
    onClick(ev) {
      alert(`The button ${ev.target.outerText} was clicked!`);
    },

    onDblClick(ev) {
      alert(`The button ${ev.target.outerText} was double clicked!`);
    },

    onMouseLeave(ev) {
      alert(`The cursor just leave the button ${ev.target.outerText}`);
    },
  }
}
</script>

<style>
button {
  margin-right: 10px;
}
</style>
