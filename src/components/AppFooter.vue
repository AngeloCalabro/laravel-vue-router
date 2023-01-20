<template>
    <footer class="d-flex justify-content-around">
        <a href=""><i class="fa-solid fa-house"></i></a>
        <a href=""><i class="fa-solid fa-mountain-sun"></i></a>
        <a href=""><i class="fa-solid fa-person-hiking"></i></a>
        <a href=""><i class="fa-solid fa-people-group"></i></a>
        <a href=""><i class="fa-solid fa-gears"></i></a>
    </footer>
</template>

<script>
    export default {
    name: 'AppFooter',

    }
</script>

<style lang="scss" scoped>
footer{
    
    footer a {
            color: #20496a;
    
            i {
                transition: 0.2s;
    
                &:hover {
                    transform: translateY(-10px);
                }
            }
    
        }
    
        footer a:nth-of-type(3),
        footer a:nth-last-of-type(4),
        footer a:nth-last-of-type(5) {
            font-size: 1.3rem;
        }

}
</style>