<template>
    <div v-if="type === 'p'">
        <p>{{ title }}</p>
    </div>
    <div v-else-if="type==='h'">
        <h1>{{ title }}</h1>
    </div>
    <div v-else>
        <img :src="title">
    </div>
</template>

<script>

export default {
    name: 'MainBox',
    components: {
    },
    props: {
        title: {
            type: String,
            default: 'defaultText'
        },
        type: {
            type: String,
            default: 'p'
        },
    },

    data: () => ({
        //
    }),
};

</script>