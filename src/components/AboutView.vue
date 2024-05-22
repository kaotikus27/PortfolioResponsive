<template>
  <div class="container">
    <div class="about">
      <h1>ABOUT <span>ME</span> </h1>
      <p>I’m currently trying my best to learn more about my self, encouraging
      to work hard in order to achieve what I really want to be and whom I 
      wanted to be with.</p>
    </div>
    <div class="hobbies">
      <h1>Hobbies</h1>
      <p>I have a passion for engaging in outdoor
      pursuits like hiking and trekking.</p>

    </div>

    <div class="content">
      <h1>Language and Tools</h1>
      <div class="language-tools">
      <div class="item"><img src="../assets/tools/8.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/9.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/1.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/2.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/4.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/5.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/10.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/7.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/3.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/6.png" alt="" srcset=""></div>
      <div class="item"><img src="../assets/tools/11.png" alt="" srcset=""></div>
    </div>
    </div>
   

    <div class="quote-container">
      <img  src="../assets/bella.png" alt="" srcset="">
      <p>"No matter how many weapons you have,  
      no matter how great  your technology might be, the world  cannot live without love."</p>
    </div>



  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

  .container{
    background-color: #B1C49E;
    height: 100vh;
    max-width: 430px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    padding: 40px;
    padding-top: 90px;

  .about,.hobbies{
    display: flex;
    gap: 1rem;
    flex-direction: column;
    h1{
      font-weight: 100;
    }
    span{
      color: #661B1C;
      font-weight: bold;
    }
  }

  .hobbies{
    display: flex;
    flex-direction: column;
    margin: 20px 0 20px 0;
   
  }

  .content{
    h1{
    color: #661B1C;
    font-weight: 500;
    }
   
  }

  .language-tools{
    display: grid;
    grid-template-columns: auto auto auto auto;
    grid-gap: 2em;
    padding: 1em;
    height: 20vh;
    margin-top: 10px;
   
    .item{
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  .quote-container{
   
    display: flex;
    flex-direction: row;
   
    align-items: center;
    margin-top: 100px;
    img{
      margin-left: -50px;
    }
    p{
      font-size: 11.5px;
    }
  }
   
  }

</style>