<template>
    <div class="prompt">
        <input type="text" v-model="input">
        <button @click="fire"> {{ text }}</button>
    </div>
</template>

<script>

export default {
    props: ['text'],
    data : () => ({
        input: ""
    }),

    methods:{
        fire(){
            this.$emit('action', this.input)
        }
    }
}
</script>

<style>

</style>


