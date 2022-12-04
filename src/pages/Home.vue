<template>
    <div>
        <Navbar />
        <section class="home">

            <div class="image">
                <img src="images\1.jpg" alt="">
            </div>
        
            <div class="content">
                <h3>Hello {{name}}</h3>
                <span>{{motto}}</span>
                <p>{{content}} Monlaya Kunpratum </p>
            </div>
        
        </section>
        
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
export default {
    components: { Navbar },
    data() {
        return {
            name: 'Monlaya Kunpratum'
        }
    }

}
</script>

<style>

</style>