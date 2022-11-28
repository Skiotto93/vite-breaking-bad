<script>
export default {
    name: 'AppHeader',
}
</script>

<template>
    <header>
        <img src="/logo breaking bad.png" alt="logo">
        <h1>Breaking Bad Api</h1>
    </header>
</template>

<style lang="scss" scoped>
header {
    display: flex;
    align-items: center;
    padding: 20px;
    img {
        width: 50px;
        height: 50px;
        margin-right: 10px;
    }
    h1 {
        color: white;
        font-size: 50px;
    }
}
</style>
