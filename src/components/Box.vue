<template>
    <div class="box has-text-weight-bold">
        <slot></slot>
    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue'

export default defineComponent ({
    name: 'BoxTarefa'
})

</script>

<style scoped>
.box {
    background: #12208b;
    color: white;
}
</style>