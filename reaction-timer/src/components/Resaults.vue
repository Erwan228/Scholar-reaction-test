<template>
<p>Reaction time: {{ score }}ms</p>
<p class="rank">{{ rank }}</p>
</template>

<script>
export default{
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 250){
            this.rank = 'Scholar fingers'
        }
        else if(this.score < 400){
            this.rank = 'Rapid reflexes'
        }
        else {
            this.rank = "Don't do savage"
        }
    }
}
</script>

<style scoped>
.rank{
    font-size: 1.em;
    color: #0faf87;
    font-weight: bold;
}
</style>