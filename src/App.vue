<script setup lang="ts">
    import InstantSearch from 'vue-instantsearch/vue3/es/src/components/InstantSearch';
    import Hits from 'vue-instantsearch/vue3/es/src/components/Hits';
    import SearchBox from 'vue-instantsearch/vue3/es/src/components/SearchBox.vue';
    import { instantMeiliSearch } from '@meilisearch/instant-meilisearch';

    const { searchClient } = instantMeiliSearch(
        'https://edge.meilisearch.com',
        '6287312fd043d3fca95136cd40483a26154d37dc99aa2e79417f88794a80cd1c',
    );
</script>

<template>
    <InstantSearch index-name="movies-en-US" :search-client="searchClient">
        <SearchBox />
        <!-- Widgets -->
        <Hits>
            <template v-slot="{ items }">
                <ul class="my-4 flex flex-col gap-2">
                    <li v-for="item in items">
                        <p class="text-lg font-semibold">{{ item.title }}</p>
                        <p class="text-sm text-gray-500">
                            {{ item.overview }}
                        </p>
                    </li>
                </ul>
            </template>
        </Hits>
    </InstantSearch>
</template>
