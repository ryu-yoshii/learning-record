<template lang="ja">
<div>
    <div id="sign-up-wrapper">
    <header id="header">
        <h1 id="title">
        Learning  records
        </h1>
        <ul id="header-list">
            <li><router-link to="/">login</router-link></li>
            <li><router-link to="/Post">post</router-link></li>
            <li><router-link to="/graph">graph</router-link></li>
        </ul>
    </header>
        <div id="sign-up">
        <h2 class="sign-up-title">新規登録</h2>
        <form class="mail-form form">
            <label for="email">メールアドレス</label>
            <input type="email" id="email" >
        </form>
        <form class="pass-form form">
            <label for="password">パスワード</label>
            <input type="password"  id="password" >
        </form>
        <button id="sign-up-btn">登録</button>
        </div>
    </div> 
    <footer>
    <p>
        <small>&copy;2021</small>
    </p>
    </footer>
</div>
</template> 
<script>
export default {
    // layout: 'default'
}
</script>
<style lang="">
    
</style>