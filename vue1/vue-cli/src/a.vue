<template>
    <div>{{ num }}
        <button v-on:click="addNum">add</button>
    </div>
    
</template>

<script>
export default {
    data: {
        num: 10
    },
    methods: {
        addNum: function() {
            this.num++;
        }
    }
}
</script>

<style>

</style>