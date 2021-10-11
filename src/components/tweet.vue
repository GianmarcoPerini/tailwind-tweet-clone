<template>
    <div class="w-2/4 overflow-auto">
        <!-- New tweet -->
        <div class="flex justify-between items-center p-5 border-b">
            <p class="font-bold text-lg">Home</p>
            <i class="text-blue-400 text-3xl fas fa-hand-sparkles"></i>
        </div>

        <div class="flex items-center px-5 pt-3">
            <img class="rounded-full h-14 w-14 object-cover" src="https://images.unsplash.com/photo-1633889976599-bce479729bd1?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=764&q=80" alt="">
            <input type="text" v-model.trim="myTweet" @keyup.enter="newTweet(myTweet)"
            placeholder="What's appening?" class="w-10/12 ml-5">
        </div>

        <div class="flex justify-between items-center pb-3 border-b-8">
            <div class="text-blue-400 pl-20">
                <i class="text-xl p-3 far fa-image"></i>
                <i class="text-xl p-3 fas fa-photo-video"></i>
                <i class="text-xl p-3 fas fa-chart-bar"></i>
                <i class="text-xl p-3 far fa-smile"></i>
            </div>
            <div>
                <button class="hover:bg-blue-400 text-white font-semibold px-5 py-2 bg-blue-500 rounded-full mr-10"
                @click="newTweet(myTweet)">Tweet</button>
            </div>
        </div>

        <!-- Display tweets -->
        <div class="flex border-b p-3" v-for="(el, i) in tweets" :key="i">
            <!-- <div class=" bg-red-500" style="width:100px; height:100px;"> -->
                <img class="w-14 h-14 object-cover inline-block rounded-full" :src="el.userUrl" alt="">
            <!-- </div> -->
            <div class="w-full ml-8">
                <p class="inline font-semibold pr-2">{{el.name}}</p>
                <p class="inline text-gray-300">{{el.twName}}</p>
                <i class="inline text-gray-300 fas fa-circle px-2" style="font-size: 3px; vertical-align: middle"></i>
                <p class="inline text-gray-300">{{el.time}}</p>
                <p>{{el.message}}</p>
                <img v-show="el.img.length != 0" class="mt-3 object-cover h-96 w-full" :src="el.img" alt="">
                
                <div class="flex justify-between text-gray-300 text-lg mt-8 w-10/12">
                    <i class="far fa-comment"> {{el.comments}}</i>
                    <i class="fas fa-code-branch"></i>
                    <i class="far fa-heart" @click="el.love += 1"> {{el.love}}</i>
                    <i class="fas fa-upload"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Tweet',
    
    data(){
        return{
            myTweet: '',
            tweets: [
                {userUrl: 'https://images.unsplash.com/photo-1633113087607-bbd9d4b6449a?ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1170&q=80',
                name: 'Brie', twName: '@Sktch_CommedyFan', time: '3m', message: 'Giving stand up commedy a go. Open mic starts at 7.', comments: 12, love: 2, img: '',},
                {userUrl: 'https://images.unsplash.com/photo-1633883686704-c45a1d3005e4?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=687&q=80',
                name: 'Harold', twName: '@H_Wang88', time: '10m', message: 'Vacation is going great', comments: 4, love: 33, img: 'https://images.unsplash.com/photo-1633842691897-ae1b42507252?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=687&q=80'}
            ]
        }
    },

    methods: {
        newTweet(input){
            this.tweets.push({userUrl: 'https://images.unsplash.com/photo-1633889976599-bce479729bd1?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=764&q=80',
                name: 'Brie', twName: '@Sktch_CommedyFan', time: '3m', message: input, comments: 0, love: 0, img: ''})
            if (this.myTweet != '') this.myTweet = ''
        }
    }

}
</script>

<style>

</style>