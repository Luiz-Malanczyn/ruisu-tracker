<template>
    <header>
        <h1>
            <img class = "logo" src="../assets/logo2.png" alt="logo">
        </h1>
        <button class="button" @click="alterarTema">
            {{ textoBotao }}
        </button>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'BarraLateral',
        emits: ['aoTemaAlterado'],
        data () {
            return {
                modoEscuroAtivo: false
            }
        },
        computed: {
            textoBotao () {
                if (this.modoEscuroAtivo) {
                    return 'Desativar modo escuro'
                }
                return 'Ativar modo escuro'
            }
        },
        methods: {
            alterarTema () {
                this.modoEscuroAtivo = !this.modoEscuroAtivo
                this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
            }
        }
    })
</script>

<style scoped>
    header {
        padding: 1rem;
        background-color: var(--bg-barralateral);
        width: 100%;
        height: 100vh;
        text-align: center;
    }

    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }

    .logo {
        width: 30vh;
        margin-bottom: 1rem;
    }
</style>