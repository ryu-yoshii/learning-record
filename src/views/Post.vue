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
                            <option v-for="hour in hours" :key="hour.hour_id">{{hour}}時間</option>
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
                    {{ post.text }}{{ post.hour }}
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
            times:[],
        };
    },
    methods:{
        post: function(){
            this.posted = "投稿しました"
            // console.log("テスト");
            let date = new Date();  //new演算子でオブジェクトのインスタンスを生成
            //現在時刻の取得 **ここからはjavascript**
            this.now = date.getFullYear() + "年"
            + (Number(date.getMonth()) + 1) + "月" +
            date.getDate() + "日" 
            +date.getHours() + "時"
            +date.getMinutes() + "分";

            const  post_object = {
                text:this.posted_text,
                hour:this.now
            }
            this.posts.push(post_object)
            console.log(this.posts)
            // 勉強時間の取得
            // this.hours.push({hour:this.hour})
            // 更新時刻の取得
            
        },
        tweet: function(){
            this.posted = "ツイートしました"
            console.log("テスト３");
        },
    },
    
}
</script>
<style lang="">

</style>