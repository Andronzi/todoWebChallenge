<template>
    <li v-for="item in tasks">
        {{item}}
    </li>
</template>

<script>
    export default {
        props: {
            tasks: Array
        },
    }
</script>