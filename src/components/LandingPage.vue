<template>
    <div>
        <div class="bg-[#F8F8FF] py-16">

            <div class="container flex items-center justify-center lg:justify-between mx-auto">
                <div class="max-w-[640px]">
                    <h1 class="text-[#121214] text-[40px] font-semibold">Encontre os <strong class="text-[#846AFF] font-semibold">melhores artigos</strong> de programação em um só lugar</h1>
                    <p class="text-[#121214] text-[24px] pt-6">Explore o topo da programação em um só lugar!
                        Seu destino único para dicas e tendências atuais.</p>
                        <button class="bg-[#846AFF] mt-6 py-4 px-6 text-white font-semibold">BUSCAR ARTIGOS</button>
                </div>

                <div class="hidden lg:block">
                    <img src="/banner.png" alt="">
                </div>
            </div>

        </div>

        <div class="container py-16">
            <h2 class="text-[#121214] text-[32px] font-semibold">Artigos recomendados</h2>

            <div class="mt-20">
                <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                    <li v-for="artigo in artigos" :key="artigo.id" class="border border-[#846AFF] rounded">
                        <img class="w-full" :src="artigo.image" alt="">
                        <div class="py-6 px-2">
                            <h4 class="text-[20px] text-[#121214] font-semibold">{{ artigo.title }}</h4>
                            <p class="text-[18px] text-[#121214] pt-2">{{ artigo.description }}</p>
                        </div>
                    </li>
                </ul>
            </div>
        </div>

        <div class="bg-[#F8F8FF] py-16">
            <div class="container">
                <h2 class="text-[#121214] text-[32px] font-semibold text-center">Entre em contato</h2>

                <form @submit="handleSubmit" class="flex flex-col gap-8 items-center mt-8 max-w-[580px] mx-auto">
                    <input type="text" placeholder="Nome" v-model="nome" class="w-full h-[60px] pl-4 rounded">
                    <input type="text" placeholder="Email" v-model="email" class="w-full h-[60px] pl-4 rounded">
                    <textarea placeholder="Assunto da mensagem" v-model="mensagem" class="w-full h-[150px] p-4 rounded"></textarea>
                    <button type="submit" class="bg-[#846AFF] text-white font-bold w-full p-4">Entrar em contato</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    import artigos from './../services/Api';

    export default {
        name: 'LandingPage',
        data() {
            return {
                artigos: [],
                nome: '',
                email: '',
                mensagem: '',
            }
        },
        methods: {
            handleSubmit() {
                alert('Mensagem enviada! Em breve retornaremos o contato!');
                this.nome = '';
                this.email = '';
                this.mensagem = '';
            }
        },
        mounted() {
            this.artigos = artigos;
            console.log(this.artigos)
        }
    }
</script>