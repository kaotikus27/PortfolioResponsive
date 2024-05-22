<template>
    <div class="mobile-view">
        <div class="profile">
            <img src="../assets/profile.png" alt="">
        </div>

        <div class="context">
            <div class="content">
            <h1>Hello. I’m a freelance user <br>
                interface developer</h1>
            
            <p>My name  is  Eleomar Halaman, I craft 
            user interface using modern frontend web technologies</p>
            </div>

            <div class="button">
                <img src="../assets/Mail.png" alt="">
                <p>Let’s work together</p>
            </div>

            <div class="social-links">
                <ul>
                    <li>
                        <a href="https://github.com/kaotikus27" target="_blank">
                        <img src="../assets/github.png" alt="" srcset="">
                        </a>
                    </li>
                    <li> 
                        <a href="https://www.linkedin.com/in/eleomar-halaman-439815282/" target="_blank">
                        <img src="../assets/linkedin.png" style="margin-top: 13.5px;" alt="" srcset="">
                        </a>
                    </li>
                </ul>
            </div>

            <div id="profile-bella"></div>

        </div>
        
        
    </div>

</template>

<script setup>

</script>

<style lang="scss" scoped>

.mobile-view{
      background-color: #DEDE7D;
      height: 100vh;
    }

    .mobile-view{
        max-width: 430px;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        padding: 40px;
        padding-top: 90px;

        .profile{
            display: flex;
            justify-content: center;
            padding: 8px;
           img{
            width: 70%;
            
           } 
        }
        .context{
            margin-top: 45px;
        }
        .content{
            margin-top: 10px;
            display: flex;
            gap: 15px;
            flex-direction: column        
            
        }

        .content h1,p{
            color: #661B1C ;
        }

        .content h1{
            font-size: 25px;
        }

        .content p{
            font-size: 15px;
        }
    
        .button{
            margin: 40px 0 40px 0;
            border: 1px solid #661B1C;
            border-radius: 35px;
            display:flex;
            gap: 20px;
            align-items: center;
            padding: 2px 20px 2px 20px;
            max-width: 250px;
        }

        .social-links ul{
            display: flex;
            gap: 2rem;
            align-items: center;
            li{
                list-style: none;
                cursor: pointer;
            }
        }

        #profile-bella{
            background:  url(../assets/bellat.gif) no-repeat center center;
            background-size: 100%;
            height: 20vh;
            z-index: 100;

            margin-left: 100px;
        }
    }

</style>