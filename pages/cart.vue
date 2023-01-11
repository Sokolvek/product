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
                    <span class="current">{{ this.current+1 }}</span>
                    <div class="next"></div>
                </div>
                   <span class="count-line"></span>
                   <span class="total">{{ this.total }}</span>
               </div>
               <div class="slide-title">
                   <span>
                   <span class="current">
                    <p class="desc1">
                        J018
                    </p>
                   </span> 
                   </span>
                   Chair
               </div>
               <div class="slide-descriptions" >
                   <p class="desc">With the comfort of a lounge chair and the functionality of a dining chair, HAY’s reproduction of Poul M. Voulter’s J110 offers equal measures of strong aesthetics and practicality. Long rods at the back and curved armrests create an inviting expression. Made in lacquered solid beech and available in a variety of colours. </p>
               </div>
               <a href="#" class="btn">FIND A DEALER</a>
               <div class="dots">
                   <span class="dot dot-active"></span>
                   <span class="dot"></span>
                   <span class="dot"></span>
               </div>
               <div class="side-nav">
                   <button class="btn-prev"  @click="prev()">
                   <img src="../assets/imgs/right-arrow.svg" alt="">
                   </button>
                   <button class="btn-next" @click="next()">
                   <img src="../assets/imgs/right-arrow.svg" alt="">
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
            current:1,
            descs: ["first desc", "second desc", "third desc"],
            titles:["j213","j018","j017"],
            total: 3,
        }
    },
    methods:{
        prev(){
            if(this.current <= 0){
                this.current = 2;
            }else{
                this.current--;
            }
           
            const gsap = this.$gsap
            const   container = document.querySelectorAll(".desc")[this.current]
           
            gsap.fromTo(container,
            { y:0, opacity:1 },
            { y:-20, opacity:0, duration:1 }
            )
           
            if(cur == -1){
                cur = 2;
               }
               const   container2 = document.querySelectorAll(".desc")[cur]
            
             gsap.fromTo(container2,
             { y:20, opacity:0 },
             { y:0, opacity:1, duration:1 }
             )
           
        
        },
        next(){
            
           
            

            if(this.current >= 2){
                this.current = 0;
            }else{
                this.current++;      
            }
            const gsap = this.$gsap
            const   container = document.querySelectorAll(".desc")[this.current]
            const title = document.querySelectorAll(".desc1")[cur]
            let cur = this.current+1
            gsap.fromTo(container,
            { y:0, opacity:1 },
            { y:-20, opacity:0, duration:1 }
            )
            gsap.fromTo(title,
            { y:0, opacity:1 },
            { y:-40, opacity:0, duration:1 }
            )
            if(cur == 3){
                cur = 0;
               }
             const   container2 = document.querySelectorAll(".desc")[cur]
             const title2 = document.querySelectorAll(".desc1")[this.current]
             gsap.fromTo(container2,
             { y:20, opacity:0 },
             { y:0, opacity:1, duration:1 }
             )
             gsap.fromTo(title2,
             { y:40, opacity:0 },
             { y:0, opacity:1, duration:1 }
             )




           
           

        },


    }
}
</script>

<style scoped lang="scss">
@import '../assets/styles/cart.scss';
</style>