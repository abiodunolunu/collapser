<script setup lang='ts'>
import { computed, ref } from 'vue';
import useCollapser from '../composables/collapser';

interface Props { modelValue: boolean }
const props = defineProps<Props>();
const collapserRef = ref<HTMLElement>()
useCollapser(computed(() => collapserRef.value), computed(() => props.modelValue))
</script>

<template>
    <div ref="collapserRef" style="overflow: hidden; transition: all 200ms linear;">
        <div>
            <slot />
        </div>
    </div>
</template>

<style>

</style>