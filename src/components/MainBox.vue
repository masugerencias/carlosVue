<template #nombre>
   <div>
    <header>
        <slot name ="primero"></slot>
    </header>
<slot name ="segundo"></slot>
<slot name ="tercero"></slot>
<DataIterator 
:items="items">
</DataIterator>




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
        items: {
            type: Array,
            default: null
        }
    },

    data: () => ({
        
    }),
};

</script>