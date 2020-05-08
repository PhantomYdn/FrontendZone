<template>
  <div class="ceditable">
    <div class="text" v-show="!edit" @click="editValue">
      <vue-markdown :source="localValue"></vue-markdown>
    </div>
    <textarea
      v-show="edit"
      v-model="localValue"
      v-click-outside="viewValue"
      @keydown.enter="handleCtrlEnter"
      v-focus
    ></textarea>
    <div class="drag"></div>
  </div>
</template>

<script>
import Vue from "vue";
import VueMarkdown from "vue-markdown";
export default {
  name: "CEditable",
  components: {
    VueMarkdown
  },
  props: {
    value: String,
    index: Number
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
      this.$emit("changeValue", this.index, this.localValue);
    },
    handleCtrlEnter(e) {
      if (e.ctrlKey) return this.viewValue();
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
<style>
div.ceditable {
  border-top: solid 1px rgb(177, 143, 185);
  display: flex;
  width: 100%;
  height: 100%;
  position: relative;
}

div.ceditable.dragging {
  background: rgb(208, 169, 218);
  border: solid 1px rgb(177, 143, 185);
}

div.ceditable div.text,
div.ceditable div.text > div > p,
div.ceditable > textarea {
  word-break: break-word;
  width: 100%;
  text-align: left;
  font-size: 14px;
  font-family: "Times New Roman", Times, serif;
  margin: 0;
}

div.ceditable div.text {
  padding: 0 15px;
  min-height: 2em;
}

div.ceditable > textarea {
  margin-left: 15px;
}

div.ceditable div.drag {
  background: rgb(177, 143, 185) url("../assets/handle.png");
  cursor: move;
  position: absolute;
  top: 0;
  left: 0;
  width: 13px;
  height: 100%;
}

div.ceditable div.drag > span {
  content: "....";
}
</style>
