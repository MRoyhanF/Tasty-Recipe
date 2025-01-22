import { default } from '../pages/HomePage.vue';
<template>
    <div>
        <label :for="identity" class="fw-semibold">
            First Name <span style="color: #cb3a31">*</span>
        </label>
        <input 
            class="form-control" 
            :type="text" 
            :id="identity" 
            :placeholder="placeholder" 
            :value="modelValue"
            :readonly="readonly === '1'"
        />
    </div>
</template>

<script setup>
 defineProps({
    type: {
        type: String,
        required: true,
    },
    label: {
        type: String,
        required: true,
    },
    identity: {
        type: String,
        required: true,
    },
    placeholder: {
        type: String,
        required: false,
    },
    readonly: {
        type: String,
        required: true,
        default: '0',
    },
 })
</script>