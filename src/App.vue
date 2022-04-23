<template>
    <h2>{{test}} {{theme}} {{user}}</h2>
</template>

<script>
export default {
    setup()
    {
        let theme = window.Telegram.WebApp.colorScheme;
        let user = window.Telegram.WebApp.initData;
        let test = "тест"
        //let user = "юзер"
        //let theme = "тема"
        return {test, user, theme}
    },
    mounted() {
        let telegramScript = document.createElement('script')
      telegramScript.setAttribute('src', 'https://telegram.org/js/telegram-web-app.js')
      document.head.appendChild(telegramScript)
    }
}
</script>

<style>

</style>