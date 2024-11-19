<script>
import BookItem from '@/components/Home/BookItem.vue';
import { useBookStore } from '@/stores/book';
import { mapStores } from 'pinia';

export default {
    name: 'BookList',
    setup() {
        // const store = useBookStore().books;
        return {
            // store,
        };
    },
    computed: {
        ...mapStores(useBookStore),
    },
    components: {
        BookItem,
    },
    methods: {},

    data() {
        return {};
    },
};
</script>

<template>
    <div class="container ">
        <div class="grid grid-cols-4 gap-8 border-1 border-Purple-700">
            <BookItem v-for="book in bookStore.getBooksFromTitle(bookStore.searchTitle)" :key="book._id" :data="book">
            </BookItem>
        </div>
    </div>
</template>
