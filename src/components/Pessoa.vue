<template>
    <div>
        <h2>Esta é a descrição da pessoa: {{ nome }}</h2>
        <div>
            <Info :email="email" :esta_trabalhando="true" />
        </div>
        <div>
            <Form />
        </div>
    </div>
</template>

<script>
import Info from './Info.vue'
import Form from './Form.vue'

export default {
    name: "Pessoa",
    components: {
        Info,
        Form
    },
    data(){
        return {
            nome: "Jhonata",
            email: "jhonata.galante@gmail.com"
        }
    }
}
</script>