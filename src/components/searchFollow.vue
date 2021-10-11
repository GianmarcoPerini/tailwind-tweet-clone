<template>
    <div class="border-l-2 py-5 w-1/4 overflow-y-auto">
        <input type="text" placeholder="Search Twitter" class="block m-auto w-5/6 bg-gray-300 p-2 mb-3 rounded-full">
        <div class="bg-gray-100 rounded-md p-3 w-11/12 m-auto">
            <div class="flex justify-between items-baseline border-b py-2">
                <p class="font-bold text-lg">Trends for you</p>
                <i class="text-blue-400 fas fa-cog"></i>
            </div>
            <div v-for="( el, i ) in trends" :key="i" class="hover:bg-gray-200 py-2 cursor-pointer border-b flex items-center">
                <div class="w-3/4">
                    <p class="text-xs text-gray-400">{{ el. category }}</p>
                    <p class="text-md text-black">{{ el.name }}</p>
                    <p class="text-sm text-gray-400">{{ el.count }}</p>
                </div>
                <i class="w-1/4 text-right fas fa-angle-down"></i>
            </div>
            <p class="text-blue-400 font-semibold text-lg pt-3">Show more</p>
        </div>

        <div class="bg-gray-100 rounded-md p-3 w-11/12 m-auto mt-5">
            <div class="flex justify-between items-baseline border-b py-2">
                <p class="font-bold text-lg">Who to follow</p>
            </div>
            <div v-for="( el, i ) in follow" :key="i" class="hover:bg-gray-200 py-2 cursor-pointer border-b flex items-center">
                <div class="flex justify-between w-full items-center">
                    <div>
                        <p class="text-md font-semibold text-black">{{ el. name }}</p>
                        <p class="text-sm text-grey-400">{{ el.twName }}</p>
                    </div>
                    <p class="text-sm text-blue-400 text-right rounded-full bg-gray-100 border-2 border-blue-400 py-2 px-4">follow</p>
                </div>
            </div>
            <p class="text-blue-400 font-semibold text-lg pt-3 ">Show more</p>
        </div>


    </div>
</template>

<script>
export default {
    name: 'searcheFollow',
    
    data(){
        return{
            trends: [
                {category: 'Trending in TX', name: 'Gigi', count: 'Trending with: RIP Gigi',},
                {category: 'Music', name: 'We Won', count: '135K Tweets',},
                {category: 'Pop', name: 'Blue Ivy', count: '40K Tweets',},
                {category: 'Trending in USA', name: 'Denim Day', count: '40K Tweets',},
                {category: 'Trending', name: 'When Beyonce', count: '25.4K Tweets',},
            ],
            follow: [
                {name: 'Elon Musk', twName: '@teslaBoy'},
                {name: 'Adrian Monk', twName: '@detective:)'},
                {name: 'Kevin Hart', twName: '@miniRock'},
            ]
        }
    }

}
</script>

<style>

</style>