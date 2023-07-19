<template>
<h1>Daftar Pekerjaan</h1>
<div v-if="pekerjaan.length">
    <div v-for="list in pekerjaan" :key="list.id" class="job">
        <router-link :to="{ name:'jobdetail',params:{id:list.id} }">
            <h2>{{ list.title }}</h2>
        </router-link>
    </div>
</div>
<div v-else>
    Loading....
</div>
</template>

<script>
export default {
    data() {
        return {
            pekerjaan: [],
        };
    },
    mounted() {
        fetch('http://localhost:3000/pekerjaan')
            .then(res => res.json())
            .then(result => {
                this.pekerjaan = result;
            })
            .catch(err => console.log(err.message))
    }
}
</script>

<style scoped>
h1 {
    margin-bottom: 20px;
    padding-bottom: 12px;
    border-bottom: 2px solid #000;
}

.job h2 {
    background: #c7c0c0;
    padding: 20px;
    border-radius: 10px;
    margin: 10px auto;
    max-width: 600px;
    cursor: pointer;
    color: #444;
}

.job h2:hover {
    background: #ddd;
}

.job a {
    text-decoration: none;
}
</style>
