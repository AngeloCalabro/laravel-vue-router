<template>
    <section id="top">
        <!-- <img src="https://aryan-tayal.github.io/Mountains-Parallax/bg.jpg" id="big">
        <h2 id="text" ref="text">MySiTe</h2>
        <img src="https://aryan-tayal.github.io/Mountains-Parallax/man.png" id="man" ref="man">
        <img src="https://aryan-tayal.github.io/Mountains-Parallax/clouds_1.png" id="clouds_1" ref="clouds_1">
        <img src="https://aryan-tayal.github.io/Mountains-Parallax/clouds_2.png" id="clouds_2" ref="clouds_2">
        <img src="https://aryan-tayal.github.io/Mountains-Parallax/mountain_left.png" id="mountain_left" ref="mountain_left">
        <img src="https://aryan-tayal.github.io/Mountains-Parallax/mountain_right.png" id="mountain_right" ref="mountain_right"> -->
    </section>
    <section id="sec">
        <h2>Welcome to the MySiTe</h2>
        <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sint aspernatur nostrum vero magnam consequuntur deserunt placeat tenetur quaerat incidunt. Corrupti quod recusandae eius incidunt voluptatem explicabo totam tempora autem nulla quae ut alias eum officiis laudantium, doloremque unde ea saepe sint. Consectetur perferendis iste dolores illum magni. Et, reiciendis similique necessitatibus exercitationem quam amet nisi, debitis rem, dolor vitae accusamus asperiores minus ad labore libero laudantium eum culpa inventore ducimus aspernatur esse dignissimos? Minima tenetur nesciunt facere neque aperiam perferendis dolorum odio mollitia ipsa iure, temporibus voluptatum fugit libero consectetur at animi id ullam exercitationem accusantium placeat ratione fuga illum. Ut commodi placeat neque officia voluptates assumenda totam, laboriosam quidem, provident consequuntur, mollitia perferendis quod accusamus voluptas nemo consectetur cumque. Veniam assumenda alias voluptates eveniet similique perspiciatis officia ex, ad sequi repellat voluptatibus incidunt harum eum culpa a libero ratione accusantium perferendis ullam amet totam mollitia consequatur obcaecati. Velit cumque ipsa libero voluptate sequi architecto nihil deserunt ex, aliquid distinctio numquam veritatis quod ab enim inventore unde voluptas et quibusdam rem illo, earum quasi totam nobis accusantium. Fugit temporibus sapiente ab iure cumque exercitationem omnis quas voluptate inventore ipsa autem praesentium qui repellat in laboriosam dignissimos sunt cupiditate, et iusto tenetur rem. Quos dicta adipisci, nostrum doloremque optio esse distinctio impedit vitae expedita eaque eveniet delectus aliquam quod dolorum beatae! Sit, vero? Quos laudantium quia nam nihil consequuntur explicabo sapiente officiis facilis, aliquid sed optio expedita voluptatum itaque ut consectetur labore quasi autem veritatis libero.
        </p>
    </section>
</template>

<script>
export default {
    name: 'HomePage',
    data(){
        return{
            // $refs.mountainLeft,
            // $refs.mountainRight,
            // $refs.cloud1,
            // $refs.cloud2,
            // $refs.text,
            // $refs.man
        }
    },
    methods: {
        getScroll(){
            // const mountainLeft = document.querySelector('#mountain_left');
            // const mountainRight = document.querySelector('#mountain_right');
            // const cloud1 = document.querySelector('#cloud_1');
            // const cloud2 = document.querySelector('#cloud_2');
            // const text = document.querySelector('#text');
            // const man = document.querySelector('#man');

            // this.window.addEventListener('scroll',()=>{
            //     let value = scrolly;
            //     this.$refs.mountainLeft.style.left = `-${value/0.7}px`
            //     this.$refs.cloud2.style.left = `-${value*2}px`
            //     this.$refs.mountainRight.style.left = `${value / 0.7}px`
            //     this.$refs.cloud1.style.left = `${value * 2}px`
            //     this.$refs.text.style.bottom = `-${value}px`
            //     this.$refs.man.style.heigth = `${window.innerHeight - value}px`})
        }
    },
    mounted(){
        // this.$refs.mountainLeft;
        // this.$refs.mountainRight;
        // this.$refs.cloud1;
        // this.$refs.cloud2;
        // this.$refs.text;
        // this.$refs.man;
        // this.getScroll();
    }
}
</script>

<style lang="scss" scoped>
// *{
//     margin: 0;
//     padding: 0;
//     box-sizing: border-box;
//     font-family: 'Montserrat', serif;
// }

// body{
//     height: 100vh;
//     width: 100vw;
// }

#top{
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    &:before{
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        height: 200px;
        width: 100%;
        background: linear-gradient(to top, #fff, trasparent);
        z-index: 1000;
    }
}
#man{
    top: inherit;
    bottom: 0;
}

section img{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    pointer-events: none;
}

#text{
    position: relative;
    color: white;
    font-size: 10rem;
}

#sec{
    padding: 100px;
    padding-bottom: 20px;

    h2 {
        text-align: center;
        font-size: 4rem;
        margin-bottom: 30px;
        color: #20496a;
    }

    p {
        font-size: 1.2rem;
        line-height: 2rem;
        padding: 20px;
        justify-content: space-evenly;
        align-items: center;
        background-color: #80DFEA;
    }
}
</style>