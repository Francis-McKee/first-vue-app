<template>
    <h2> This is a popup. </h2>
    <button @click="$emit('close')"> Close </button>
</template>

<script>
export default {
    name: 'Popup',
    emits: ['close']
}

</script>