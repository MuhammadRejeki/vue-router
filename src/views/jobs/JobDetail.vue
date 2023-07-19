<template>

    <div v-if="pekerjaan">
        <h1>Job: {{ pekerjaan.title }}</h1>
        <p>[ {{ id }} ] {{ pekerjaan.desc }}</p>
    </div>
    <div v-else>
        Loading....
    </div>
    
</template>


<script>
export default {
    props:['id'],
    data() {
        return {
            pekerjaan:null
            // id: this.$route.params.id
        }
    },
    mounted(){
        fetch('http://localhost:3000/pekerjaan/' + this.id)
            .then(res => res.json())
            .then(result => this.pekerjaan = result)
    }
}
</script>

<style >

</style>