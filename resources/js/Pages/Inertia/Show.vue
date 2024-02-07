<script setup>
    import { Inertia } from '@inertiajs/inertia';

    defineProps({
        id: String,
        blog: Object
    })

    const deleteConfirm = (id) => {
        Inertia.delete(`/inertia/${id}`, {
            onBefore: () => {
                confirm('消すにゃ？');
            }
        })
    }
</script>

<template>
    {{ blog.content }} <br>
    {{ id }} <br>
    <button @click="deleteConfirm(blog.id)">消す</button>
</template>
