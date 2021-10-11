<template>
    <div class="w-1/4 px-10 py-5 flex flex-col justify-between border-r-2">
        <div>
            <i class="logo fab fa-twitter text-blue-400 text-5xl mb-10"></i>

            <div @click="goTo(i)" v-for="(el, i) in tabs" :key="i"
            :class="`${(index == i) ? 'text-blue-400' : ''} font-semibold flex items-center p-4 -ml-4 cursor-pointer
            hover:bg-gray-200 rounded-full `">
                <i :class="`${el.icon} text-2xl mr-5`"></i>
                <p class="md:block hidden"> {{ el.tab }} </p>
            </div>

            <button class="md:block hidden px-10 py-5 bg-blue-400 rounded-full w-full mt-4 text-white transition-all duration-100
            hover:bg-blue-600 hover:text-white">
                Tweet
            </button>

            <button class="md:hidden block p-3 bg-blue-400 rounded-full w-auto mt-4 text-white transition-all duration-100
            hover:bg-blue-600 hover:text-white">
                <i class="fas fa-plus"></i>
            </button>
        </div>
        
        <div class="w-full cursor-pointer relative">
            <!-- DropDown -->
            <div v-show="dropDown === true" class="flex flex-wrap w-72 items-center bg-white mb-3 cursor-pointer absolute bottom-full border">
                <div class="w-3/4 pt-2 pb-2 pl-3">
                    <p class=" font-semibold text-base">Gianmarco Perini</p>
                    <p class=" text-sm text-gray-400">@gianPera</p>
                </div>
                <div class="w-full">
                    <p @click="dropDown = false"
                    class="hover:bg-gray-300 pt-3 pb-3 w-full pl-3">Add an existing account</p>
                    <p @click="dropDown = false"
                    class="hover:bg-gray-300 pt-3 pb-3 w-full pl-3">Log out @gianPera</p>
                </div>
            </div>
            <!-- User -->
            <div @click="dropDown = !dropDown" class="flex flex-wrap items-center w-full">
                <p class="w-3/4 md:block hidden font-semibold text-base">Gianmarco Perini</p>
                <p class="w-3/4 md:block hidden text-sm text-gray-400">@gianPera</p>
                <div class="w-1/4 md:text-xl text-2xl text-right"><i class="fas fa-angle-down"></i></div>
            </div>
            
        </div>



    </div>
</template>

<script>
export default {
    name: 'nav',
    data(){
        return{
            tabs: [
                {icon: 'fas fa-home', tab: 'Home'},
                {icon: 'fas fa-hashtag', tab: 'Explore'},
                {icon: 'far fa-bell', tab: 'Notification'},
                {icon: 'far fa-envelope', tab: 'Messages'},
                {icon: 'far fa-bookmark', tab: 'Bookmarks'},
                {icon: 'far fa-address-book', tab: 'List'},
                {icon: 'fas fa-ellipsis-h', tab: 'More'},
            ],
            index: 0,
            dropDown: false
        }
    },

    methods: {
        goTo(i){
            this.index = i
        }
    },
}
</script>

<style>

</style>