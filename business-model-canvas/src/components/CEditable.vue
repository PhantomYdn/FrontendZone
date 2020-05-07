<template>
  <div class="ceditable">
    <div class="text" v-show="!edit" @click="editValue">{{localValue}}</div>
    <textarea v-show="edit" v-model="localValue" v-click-outside="viewValue" v-focus></textarea>
  </div>
</template>

<script>
import Vue from "vue";
export default {
  name: "CEditable",
  props: {
    value: String
  },
  data() {
    return {
      edit: false,
      localValue: this.value
    };
  },
  watch: {
    value: function() {
      this.localValue = this.value;
    }
  },
  methods: {
    editValue() {
      this.edit = true;
    },

    viewValue() {
      this.edit = false;
    }
  },
  directives: {
    "click-outside": {
      bind(el, binding, vnode) {
        vnode.event = function(event) {
          if (!vnode.context.$el.contains(event.target)) binding.value();
        };
        document.body.addEventListener("click", vnode.event);
      },

      unbind(el, binding, vnode) {
        document.body.removeEventListener("click", vnode.event);
      }
    },
    focus: {
      inserted: function(el) {
        el.focus();
      },
      update: function(el) {
        Vue.nextTick(function() {
          el.focus();
        });
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.ceditable {
  border: solid 1px #00ff22;
  display: flex;
  width: 100%;
  height: 100%;
}

div.text {
  word-break: break-word;
}

textarea {
  width: 100%;
}
</style>
