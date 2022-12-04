<template>
    <div>
        <Navbar />

        <section class="about">

            <h1 class="heading"> about <span>me</span> </h1>

            <div class="row">

                <div class="info-container">

                    <h1>personal info</h1>

                    <div class="box-container">
                        <div class="box">
                            <h3> <span>name : </span> Monlaya Kunpratum </h3>
                            <h3> <span>age : </span> 19 </h3>
                            <h3> <span>email : </span> Monlaya.kunp@bumail.net </h3>
                            <h3> <span>address : </span> Pathumthani, Thailand 12150 </h3>
                        </div>
    
                        <div class="box">
                            <h3> <span>study : </span> Bangkok University </h3>
                            <h3> <span>skill : </span> draw a picture </h3>
                            <h3> <span>hobby : </span> listen to music </h3>
                            <h3> <span>language : </span> thai </h3>
                        </div>
    
                    </div>
                </div>
            </div>
    
        </section>
    
        <section class="education">
    
            <h1 class="heading"> <span>my</span> experience </h1>
    
            <div class="box-container">
                <div class="box" v-for="e in experiences" :key="e.years">
                    <i class="fas fa-briefcase"></i>
                    <span>{{e.years}}</span>
                    <h3>{{e.location}}</h3>
                    <p>{{e.level}}</p>
                </div>
            </div>    
        </section>
    </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import axios from 'axios'
export default {
    components: { Navbar },
    methods: {
        async fetchExperience() {
            try {
                let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/experiences ")
                this.experiences = res.data
            } catch (error) {

            }
        }
    },
    data() {
        return {
            experiences: []
        }
    },
    beforeMount() {
        this.fetchExperience()
    }
}
</script>

<style>

</style>