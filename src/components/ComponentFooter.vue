<template>
    <footer class="footerContainer">

        <article>

            <address class="copyDescricao">© Copyrigth 2023 <a href="https://github.com/elielm14" target="_blank" rel="noopener noreferrer">Eliel Maia - Developer</a>.</address>

            <address class="copyDescricao">
                <p>Web Site idealizado e estruturado por Elida Lopes Maia.</p>
                <p>Todos os direitos reservados.</p>
            </address>

        </article>

    </footer>
</template>

<script>
export default {
    name: 'ComponentFooter'
}
</script>

<style scoped>
.footerContainer {
    padding: 3em 4em;
    background-color: #1a202c;
    width: 100%;
    margin-top: 2em;
}

.copyDescricao {
    padding: .5em 0;
    text-align: center;
    margin: 0;
}
</style>
