<script setup>
    import { reactive } from 'vue';
    import { Inertia } from '@inertiajs/inertia';

    defineProps({
        errors: Object,
    })

    const form = reactive({
        title: null,
        content: '',
    });

    const submit = () => {
        Inertia.post('/inertia', form)
    }
</script>

<template>
    <form @submit.prevent="submit">
        <input type="text" v-model="form.title">{{ form.title }}<br>
        <div v-if="errors.title">{{ errors.title }}</div>
        <input type="text" name="content" v-model="form.content">{{ form.content }}<br>
        <div v-if="errors.content">{{ errors.content }}</div>
        <button>お送信</button>
    </form>
</template>
