<template>
    <div>
        <p>{{ email }}</p>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades!</p>
        <p>Utilizo as seguintes tecnologias para back-end:</p>
        <ul>
            <li v-for="(tech, index) in backend_tech" v-bind:key="index">{{ tech }}</li>
        </ul>
        <p>Utilizo as seguintes tecnologias para front-end:</p>
        <ul>
        <li v-for="tech in frontend_tech" :key="tech.id">{{ tech.linguagem }}</li>
        </ul>
        <div>''
            <button @click="showEmail">{{textoBotao}}</button>
        </div>
        <p v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>
        <p class="teste">Para acessar meu portfólio <a :href="meu_link" target="_blank">basta clicar aqui!</a></p>
        <Picture />
    </div>
</template>

<script>
import Picture from './Picture.vue';
export default {
    name: "Info",
    components: {
        Picture
    },
    props: {
        email: String,
        esta_trabalhando: Boolean
    },
    data(){
        return{
            mostrar_email: false,
            meu_link: "https://www.google.com.br",
            textoBotao: 'Mostrar e-mail',
            backend_tech: ["PHP", "Javascript", ".NET"],
            frontend_tech: [
                {id: 1, linguagem: 'HTML'},
                {id: 2, linguagem: 'CSS'},
                {id: 3, linguagem: 'Vue'}
            ]
        }
    },
    methods: {
        showEmail(){
            this.mostrar_email = !this.mostrar_email;
            if(!this.mostrar_email) {
                this.textoBotao = "Mostrar e-mail";
            }else{
                this.textoBotao = "Esconder e-mail";
            }
        }
    }
}
</script>

<style>
    .paragrafo-pai{
        color: red;
    }
</style>