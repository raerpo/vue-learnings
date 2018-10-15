<template>
    <div>
        <input type="text" @input="makeSearch" placeholder="What do you want to see?" />
        <button>Search</button>
    </div>
</template>

<script>
export default {
    name: 'SearchInput',
    methods: {
        makeSearch: function(ev) {
            this.$emit('onSearch', ev.target.value);
        }
    }
}
</script>

<style scoped>
    div {
        display: flex;
        justify-content: center;
    }
    input {
        width: 75%;
        padding-left: 1rem;
    }
    button {
        outline: none;
        cursor: pointer;
    }
</style>