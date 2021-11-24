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
                <!-- <form action="">
                    <textarea name="" id="" cols="50" rows="3" placeholder="今日はテキスト第二章まで進めた！">
                    
                    </textarea>
                </form> -->
                <!-- <p style="white-space: pre-line;">{{ message }}あ</p> -->
                <textarea v-model="comment" placeholder="ここに記入">{{message}}</textarea>
            </div>
            <div class="result-box">
                <div class="study-hours">
                    <h3 class="study-hours-title">学習時間</h3>
                        <select name="hours">
                            <option value="1">1時間</option>
                            <option value="2">2時間</option>
                            <option value="3">3時間</option>
                            <option value="4">4時間</option>
                            <option value="5">5時間</option>
                            <option value="6">6時間</option>
                            <option value="7">7時間</option>
                            <option value="8">8時間</option>
                            <option value="9">9時間</option>
                            <option value="10">10時間</option>
                            <option value="11">11時間</option>
                            <option value="12">12時間</option>
                        </select>
                </div>
                    <button class="post-btn" v-on:click="post">投稿する</button>
                    <div class="post-result">{{posted}}</div>
                    <button class="tweet-btn">ツイートする</button>
            </div>
        </section>
        <section class="past">
            <h2 class="past-title">過去の投稿</h2>
            <ul class="log-list">
                <li v-for="post in posts">
                    <div class="log">
                        <p class="date"><span>{{date}}</span></p>
                        <p class="past-comment"><span>{{comment}}</span></p>
                        <div class="past-hours">
                            <h3 class="hours-title"><span>{{hours}}</span></h3>
                            <p>6時間</p>
                        </div>
                    </div>
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
            comment: "",
            hours:"hour",
            message:"",
            comments:[],
            posted:"",
            posts:[],
        };
    },
    methods:{
        post: function(){
            this.posted = "投稿しました"
            console.log("テスト");
        }
        
    },
    
}
</script>
<style lang="">

</style>