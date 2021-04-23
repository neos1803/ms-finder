<template>
    <div>
        <h1>Searched Item</h1>
        <div class="my-8 grid grid-cols-3 gap-4">
            <div class="filtered-list" v-for="l in filteredList" :key="l">
                <div class="max-w-sm rounded overflow-hidden shadow-lg">
                    <button v-on:click="addItems(l)">
                        <img class="w-full" v-bind:src="l.thumbnailUrl" alt="Sunset in the mountains">
                        <div class="px-6 py-4">
                            <div class="font-bold text-xl mb-2">Title of image id {{l.id}}</div>
                            <p class="text-gray-700 text-base">
                            {{l.title}}
                            </p>
                        </div>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "FilteredList",
    props: ["filteredList", "search", "selectedList"],
    methods: {
        checkSearch() {
            console.log(this.search)
        },

        addItems(e) {
            this.$emit("click", e)
        }
    }
}
</script>