<template>
    <h2>{{test}} {{theme}} {{user}}</h2>
</template>

<script>
export default {
    setup()
    {
        //let theme = window.Telegram.WebApp.colorScheme;
        //let user = window.Telegram.WebApp.initParams;
        let test = "тест"
        let user = "user"
        let theme = "theme"
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