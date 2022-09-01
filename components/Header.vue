<template>
    <header :style="[BG.blue, color.grey]" class="padding">
        <div class="perfil">
            <img src="/img/perfil.jpg" />
        </div>
        <div class="basic-info">
            <h1>Cristiano Oliveira Morales</h1>
            <div>
                <div class="contact">
                    <HeaderItem icon="home">Rua 20 de Setembro, 69, apartamento 105 - Azenha, RS - Brasil</HeaderItem>
                    <HeaderItem icon="phone">(51) 98546-3537</HeaderItem>
                    <HeaderItem icon="email">cristianooliveiramorales@gmail.com</HeaderItem>
                </div>
                <div class="social-midias" :style="[BG.black]">
                    <HeaderItem icon="github">github.com/Cristiano7988</HeaderItem>
                    <HeaderItem icon="linkedin">linkedin.com/in/cristiano-morales</HeaderItem>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
import { color, BG } from "@/assets/styles/paleta.json";

export default {
    data() {
        return { color, BG };
    }
}
</script>

<style scoped>
    header {
        padding: 20px 40px;
        display: flex;
        align-items: center;
    }
    
    .perfil img {
        min-width: 200px;
        height: 200px;
        border-radius: 50%;
        border: 1px solid black;
    }
    
    .basic-info {
        text-align: left;
        margin: 20px;
    }

    .contact {
        padding-right: 20px;
    }

    .social-midias {
        padding: 20px;
        border-radius: 5px;
    }
</style>