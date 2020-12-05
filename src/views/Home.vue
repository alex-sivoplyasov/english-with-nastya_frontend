<template>
    <div class="home">
        <ul>
            <li v-for="student in students" :key="student._id">
                <span>{{ student.name}}, {{student.age}}</span>
            </li>
        </ul>
    </div>
</template>

<script>
    // @ is an alias to /src
    // import HelloWorld from '@/components/HelloWorld.vue'
    import axios from 'axios'

    export default {
        name: 'Home',
        data: () => ({
            students: null
        }),
        async mounted() {
            // console.log('mounted');
            // axios.get('http://localhost:3000/students/').then( res => {
            //     this.students = res.data
            // })
            const test = await axios.get('http://localhost:3000/students/');
            console.log(test);
        },
        components: {
            // HelloWorld
        }
    }
</script>
