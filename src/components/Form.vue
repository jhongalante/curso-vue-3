<template>
    <form action="" @submit="enviarForm($event)">
        <div>
            <input type="text" v-model="name">
        </div>
        <div>
            <input type="text" v-model="email">
        </div>
        <div>
            <Submit />
        </div>
    </form>
    <br><br>
</template>

<script>
import InputText from './form/InputText.vue'
import Submit from './form/Submit.vue'

export default {
    name: 'Form',
    components: {
        InputText,
        Submit
    },
    data(){
        return{
            name: "",
            email: ""
        }
    },
    methods: {
        enviarForm(e){
            e.preventDefault();
            console.log(this.name);
            console.log(this.email);
        }
    }
}
</script>