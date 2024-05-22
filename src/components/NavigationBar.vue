<template>
    <header v-if="navContent.headerShow" :class="{'scrolled-nav' : navContent.scrollNav}">
        <!-- need to delete -->
          <!--   <nav class="navbar" >
                <ul v-show="!navContent.mobile" class="navigation">
                    <li> <router-link class="link" :to="{ name: 'home' }">Home</router-link></li>
                    <li> <router-link class="link" :to="{ name: ''}"> About</router-link></li>
                    <li> <router-link class="link" :to="{ name: ''}">Projects</router-link></li>
                    <li> <router-link class="link" :to="{ name: ''}">Contact</router-link></li>
                  
                </ul>
            </nav> -->
        <!-- !!!!!!!!!!!!!!!  -->

            <div class="icon">
                <i  
                @click="toggleMobileNav" 
                v-show="navContent.mobile"
                :class="{'icon-active' : navContent.mobileNav}"
                 class="fa fa-bars" aria-hidden="true"></i>
            </div>

            <transition name="mobile-nav">
                <ul v-show="navContent.mobileNav" class="dropdown-nav">
                    <li> <router-link class="link" :to="{name:'home'}">Home</router-link></li>
                    <li> <router-link class="link" :to="{name:''}">About</router-link></li>
                    <li> <router-link class="link" :to="{name:''}">Projects</router-link></li>
                    <li> <router-link class="link" :to="{name:''}">Contact</router-link></li>
                </ul>
            </transition>
            
    </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

import 'boxicons' 

    const navContent = ref({
        scrollNav:null,
        mobile:null,
        mobileNav:null,
        windowWidth:null,
        headerShow:null
    })


    const toggleMobileNav = ()=>{
        navContent.value.mobileNav = !navContent.value.mobileNav;
    }


    /* Scroll animation setup */
    const updateScroll =() => {
        const scrollPosition = window.scrollY;
        if(scrollPosition > 50){
            navContent.scrollNav = true;
            
            return;
        }
          
            navContent.scrollNav = false;
    }

    onMounted(()=>{
        window.addEventListener('scroll', updateScroll);
    })



    /* SCREEN SIZE CHECKER */
    const checkScreen = ()=>{
        navContent.value.windowWidth = window.innerWidth;
        if(navContent.value.windowWidth <=750){
            navContent.value.mobile = true;
            navContent.value.headerShow = true;
            return
        }
        navContent.value.mobile = false;
        navContent.value.headerShow = false
        navContent.value.mobileNav = false;
    }

    // Add event listener on mounted
    onMounted(() => {
    window.addEventListener('resize', checkScreen);
    checkScreen(); // Initial check when the component is mounted
    });

    // Remove event listener on unmounted
    onUnmounted(() => {
    window.removeEventListener('resize', checkScreen);
    });




</script>

<style lang="scss" scoped>
   

    header{
        padding: 35px;
        z-index: 99;
        width: 100%;
        position: fixed;
        transition:  .5 ease all;
        color: white;
   

        nav{
            position: relative;
            display: flex;
            flex-direction: row;
            padding: 12px 0;
            transition: .5s ease all;
            width: 90%;
            margin: 0 auto;  
        }
        ul, .link{
            font-weight: 500;
            color: #ffff;
            text-decoration: none;
            list-style: none;
        }
        li{
            text-transform: uppercase;
            padding: 10px;
            margin-left: 16px;
        }
        .link{
            font-size: 14px;
            transition: .5 ease all;
            padding-bottom: 4px;
            border-bottom: 1px solid transparent;

            &:hover{
                color: #9f3739;
                border-color: #9f3739 ;
                font-weight: bold;
                
            }
        }

        .icon{
            display:flex;
            align-items: center;
            position: absolute;
            top:10px;
            right: 35px;
            height: 100%;


            i{
                cursor: pointer;
                font-size: 35px;
                height: auto;
                width: 45px;
                transition:0.8s ease all;
                color: white;
            }
        }

        .icon-active{
            transform: rotate(180deg);
        }


        .navigation{
            display: flex;
        }

        .dropdown-nav{
            display: flex;
            flex-direction: column;
            position: fixed;
            max-width: 250px;
            height: 100%;
            width: 100%;
            padding: 35px;
            background-color: #ffffffd9;
            top: 0;
            left: 0;
        }

        li{
            margin-left: 0;
            .link{
                color: #000;
            }
    
        }

        /* using transition template */

        .mobile-nav-enter-active,
        .mobile-nav-leave-active{
            transition: 1s ease all;
        }
       
        .mobile-nav-enter-from,
        .mobile-nav-leave-to{
            transform: translateX(-250px);
        }
        
        .mobile-nav-enter-to{
            transform: translateX(0);
        }

    }

    .scrolled-nav{
        background-color: #000;
        box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba (0,0,0,0.06);
    }


</style>