<script>
    export default {
        props: {
            message: {
                type: String,
                required: true
            }
        }
    }
</script>

<template>
    <div>
        {{ message }}
    </div>
</template>
