<template>
    <div>
        <h2>Result</h2>
        <p>Reaction-Time: {{resulttime}}ms</p>
        <h1 v-if="resulttime<300">You are senku!</h1>
        <h1 v-else-if="resulttime<550">may be dekisuke!</h1>
        <h1 v-else>You are sakura in naruto!</h1>
    </div>
</template>

<script>
export default {
    name: 'Result',
    
    props:['resulttime'],
}
</script>

<style></style>