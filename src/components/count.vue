<template>
  <div>
    <h2>{{msg}}</h2>
    {{count}}
    <hr/>
    <h3>{{$store.state.a.count}}</h3>
    <button @click="add(10)">+</button>
    <button @click="reduce">-</button>
    <button @click="addAction">+</button>
    <button @click="reduceAction">-</button>
  </div>

</template>
<script>
import store from "@/vuex/store";
import { mapState, mapMutations, mapGetters, mapActions } from "vuex";
export default {
    data() {
        return {
            msg: "Hello Vuex"
        };
    },
    store,
    computed: {
        ...mapGetters(["count"])
    },
    methods: {
        ...mapMutations(["add", "reduce"]),
        ...mapActions(["addAction", "reduceAction"])
    }
};
</script>
