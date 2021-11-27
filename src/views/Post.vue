<template lang="ja">
<div>
    <div id="post-wrapper">
    <header id="header">
        <h1 id="title">
        Learning  records
        </h1>
        <ul id="header-list">
            <li><a href="">login</a></li>
            <li><a href="">post</a></li>
            <li><a href="">graph</a></li>
        </ul>
    </header>
        <section class="result">
            <h2 class="result-title">学習の成果</h2>
            <div class="comment">
                <h3 class="comment-title">本日の学習コメント</h3>
                <textarea v-model="posted_text" placeholder="ここに記入"></textarea>
            </div>
            <div class="result-box">
                <div class="study-hours">
                    <h3 class="study-hours-title">学習時間</h3>
                        <select v-model="selected">
                            <option v-for="hour in hours" :key="hour">{{hour}}時間</option>
                        </select>
                </div>
                
                    <button class="post-btn" v-on:click="post">投稿する</button>
                    <div class="post-result">{{posted}}</div>
                    <button class="tweet-btn" v-on:click="tweet">ツイートする</button>
                    

            </div>
        </section>
        <section class="past">
            <h2 class="past-title">過去の投稿</h2>
            <ul class="log-list">
                <li v-for="post in posts">
                    {{ post.text }}{{ now }}
                </li>
            </ul>
        </section>
        
    </div>
</div>
</template>
<script>
export default {
    data() {
        return {
            selected:"1時間",
            hours:[1,2,3,4,5,6,7,8,9,10],
            posted:"",
            posts:[],
            posted_text:"",
            // today:"00:00:00"
        };
    },
    methods:{
        post: function(){
            this.posted = "投稿しました"
            // console.log("テスト");
            this.posts.push({text:this.posted_text})
            let date = new Date();  //new演算子でオブジェクトのインスタンスを生成
            //現在時刻の取得 **ここからはjavascript**
            this.now = date.getHours() + ":"
            + date.getMinutes() + ":" +
            date.getSeconds();
        },
        // create: function(){
        //     const hour = 1
        //     for(let i = 0; i < 5; i++){
        //         this.hours.push(hour + i)
        //     }
        //     console.log("テスト２");
        // },
        tweet: function(){
            this.posted = "ツイートしました"
            console.log("テスト３");
        },
    },
    
}
</script>
<style lang="">

</style>