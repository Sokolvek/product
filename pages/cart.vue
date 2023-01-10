<template>
    <div id="cart">

        <header>
           <ul class="nav-list">
               <li class="nav-item">
                   <div class="burger-menu"></div>
               </li>
               <li class="nav-item">
                   <h1>MADE</h1>
               </li>
               <li class="nav-item">
                   <p>BASKET 2</p>
               </li>
           </ul>
       </header>
       <main>
           <section class="slider">
           <img class="img" src="../assets/imgs/cream-img.png" alt="">
               <article>
               <div class="slide-count">
                <div class="index">
                    <span class="current">{{ this.current }}</span>
                    <div class="next"></div>
                </div>
                   <span class="count-line"></span>
                   <span class="total">{{ this.total }}</span>
               </div>
               <div class="slide-title">
                   <span>
                   <span class="current">J014</span> 
                   </span>
                   Chair
               </div>
               <div class="slide-descriptions">
                    <p class="curret">With the comfort of a lounge chair and the functionality of a dining chair, HAY’s reproduction of Poul M. Voulter’s J110 offers equal measures of strong aesthetics and practicality. Long rods at the back and curved armrests create an inviting expression. Made in lacquered solid beech and available in a variety of colours.</p>
                    <p class="next">next</p>
               </div>
               <a href="#" class="btn">FIND A DEALER</a>
               <div class="dots">
                   <span class="dot dot-active"></span>
                   <span class="dot"></span>
                   <span class="dot"></span>
               </div>
               <div class="side-nav">
                   <button class="btn-prev"  @click="prev()">
                   <!-- <img src="../assets/imgs/up-arrow.png" alt=""> -->
                   </button>
                   <button class="btn-next">
                   <!-- <img src="../assets/imgs/up-arrow.png" alt=""> -->
                   </button>
   
               </div>
               <div class="category">SEATING</div>
               </article>
           </section>
       </main>
    </div>
</template>

<script>

import "../assets/styles/cart.scss"
export default{
    name:'cart',
    data(){
        return{
            current:0,
            total:3,
            
            currentDesc:'With the comfort of a lounge chair and the functionality of a dining chair, HAY’s reproduction of Poul M. Voulter’s J110 offers equal measures of strong aesthetics and practicality. Long rods at the back and curved armrests create an inviting expression. Made in lacquered solid beech and available in a variety of colours.'
        }
    },
    methods:{
        prev(){
            let tl = this.$gsap.timeline();
            tl.fromTo(
                ".next",
                { y:0 },
                { y: -20 }
            )
            .fromTo(
                ".next",
                { opacity: 0 },
                { opacity: 1 }
            )
            .fromTo(
                ".next",
                { y:-20 },
                { y:0, duration:2 }
            )
        }
    }

}
</script>

<style scoped lang="scss">
@import '../assets/styles/cart.scss';
</style>