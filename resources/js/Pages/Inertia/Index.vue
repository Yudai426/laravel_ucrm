<script setup>
    import { Link } from '@inertiajs/inertia-vue3';

    defineProps({
        blogs: Array,
    });
</script>

<template>
    <div v-if="$page.props.flash.message" class="text-red-800">{{ $page.props.flash.message }}</div>
    aaaaaaaaaaaaaaa
    <h2 class="my-4">登録済みのやつらにゃ</h2>
    <table class="table-auto">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
            <th>
                <td>
                    タイトル
                </td>
                <td>
                    コンテント
                </td>
                <td>
                    登録日時
                </td>
                <td>
                    詳細
                </td>
            </th>
        </thead>
        <tbody>
            <tr v-for="blog in blogs" key="blog.id">
                <td>
                    {{ blog.title }}
                </td>
                <td>
                    {{ blog.content }}
                </td>
                <td>
                    {{ blog.created_at }}
                </td>
                <td>
                    <Link :href="route('inertia.show', {id: blog.id})">詳細</Link>
                </td>
            </tr>
        </tbody>
    </table>
</template>
