<template>
<div class="d-flex flex flex-column align-items-center justify justify-content-between app ">

<!--top bar-->
<nav class="container-fluid py-3 bg-primary">
<h3>Valentine Generator</h3>
</nav>

<!--app-->

<div class="zenku-container card text-center shadow-lg">

  <div class="card-body p-5">
      <h2 class="card-title">Enter a name now!</h2>

      <div class="mt-5">
        <input type="search" v-model="msg" class="form-control text-center input" placeholder="I love ...">
      </div>

      <button  class="btn btn-lg mt-5 bg-primary text-light" @click="submitResult()">Try It Now</button>

  </div>
</div>

<!--footer-->
<footer class="py-3">
<a href="#" class="footer-link mx-0.5 mx-2-md">
<svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-instagram" width="39" height="39" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
  <rect x="4" y="4" width="16" height="16" rx="4" />
  <circle cx="12" cy="12" r="3" />
  <line x1="16.5" y1="7.5" x2="16.5" y2="7.501" />
</svg>
_zenku__
</a>
<a href="#" class="footer-link mx-0.5 mx-2-md">
<svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-github" width="39" height="39" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
  <path d="M9 19c-4.3 1.4 -4.3 -2.5 -6 -3m12 5v-3.5c0 -1 .1 -1.4 -.5 -2c2.8 -.3 5.5 -1.4 5.5 -6a4.6 4.6 0 0 0 -1.3 -3.2a4.2 4.2 0 0 0 -.1 -3.2s-1.1 -.3 -3.5 1.3a12.3 12.3 0 0 0 -6.2 0c-2.4 -1.6 -3.5 -1.3 -3.5 -1.3a4.2 4.2 0 0 0 -.1 3.2a4.6 4.6 0 0 0 -1.3 3.2c0 4.6 2.7 5.7 5.5 6c-.6 .6 -.6 1.2 -.5 2v3.5" />
</svg>
YA-GA-HI
</a>
<a href="#" class="footer-link mx-0.5 mx-2-md">
<svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-twitter" width="39" height="39" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
  <path d="M22 4.01c-1 .49 -1.98 .689 -3 .99c-1.121 -1.265 -2.783 -1.335 -4.38 -.737s-2.643 2.06 -2.62 3.737v1c-3.245 .083 -6.135 -1.395 -8 -4c0 0 -4.182 7.433 4 11c-1.872 1.247 -3.739 2.088 -6 2c3.308 1.803 6.913 2.423 10.034 1.517c3.58 -1.04 6.522 -3.723 7.651 -7.742a13.84 13.84 0 0 0 .497 -3.753c-.002 -.249 1.51 -2.772 1.818 -4.013z" />
</svg>

_zenku__
</a>
</footer>


<!--msg table-->
<div v-if="started" @click="this.started = false" class="msg-filter"></div>

<div v-if="started" @click="this.started = false" class="msg-section zenku-container card text-center shadow-lg">

  <div class="card-body p-5">
      <h2 class="card-title">{{ this.result }}</h2>
  </div>
</div>

</div>
</template>

<script>
import sound from './assets/baka.mp3'
export default {
  name: 'App',
  data()
  {

    return{
      started :false,
      msg:"",
      result:""
    }
  },
  methods: {
    submitResult(){
      let msg = this.msg,
          messages = [
            'Love Your Sister Better',
            'I love you too',
            'Never Try This Again',
            'Love is hard, isnt\'it?',
            "this melt my heart",
            "that is a cute thing that i've been waiting for",
            "thank you so much",
            "sorry but i have a crush"
          ];

      if( msg.length > 0 && this.msg.trim().slice(0,6).toLowerCase() == "i love")
      {

        
        let name = this.msg.slice(6, this.msg.length);
        /* mother*/
        if(name.split(" ").includes("mom") || name.split(" ").includes("mother") || name.split(" ").includes("mama") || name.split(" ").includes("mi") )
        {
          this.result = "She loves you too!";
          this.started = true;
          this.msg = "";
          return ;
        }
        
        /*father*/
        if(name.split(" ").includes("dad") || name.split(" ").includes("father") || name.split(" ").includes("papa") || name.split(" ").includes("ba") || name.split(" ").includes("baba")) 
        {
          this.result = "He loves you too!";
          this.started = true;
          this.msg = "";
          return ;
        }

        /*your girlfriend name for example*/
        /* notice wiam is not my girlfriend */
        if(name.split(" ").includes("wiam") )
        {
          this.result = "Love Your Sister Better";
          this.started = true;
          this.msg = "";
          return ;
        }

        /*javascript*/
        if(name.split(" ").includes("javascript") || name.split(" ").includes("js"))
        {
          this.result = "I love you too, oni-chan!";
          let theSound = new Audio(sound);
          theSound.currentTime = 1;
          theSound.play();
          this.started = true;
          this.msg = "";
          return ;
        }

        let index = Math.floor(Math.random() * messages.length);
        this.started = true;
        this.msg = "";
        this.result = messages[index];
      }
    }
  }
}
</script>

<style>
/*{
outline: 1px solid red;
}*/
#app , .app {
  font-family: 'Poppins', Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  height: 100vh;
  width: 100vw !important;
  overflow: hidden;
}

.bg-primary{
  background-image: linear-gradient(90deg, rgb(252, 61, 81), rgb(255, 129, 62));
}

.zenku-container{
width: 700px;
}

.footer-link{
font-size: 1.2em;
font-weight: 700;
}

@media ( max-width : 720px )
{
  .zenku-container{
  width: 90vw;
  }

  .footer-link{
  font-size: 1em;
  }

  .input{
  width: 90%;
  }


}

.input{
font-size: 1.6em;
width: 80%;
margin: 0 auto;
}

footer a {
color: #2c3e50;
text-decoration: none;
}

.msg-filter{
position: fixed;
width: 100%;
height: 100%;
background-color: #2c3e50;
opacity: .5;
z-index: 3;
}

.msg-section{
position: fixed;
left: 50%;
top: 50%;
transform: translate(-50% , -50%);
z-index: 4;
}
</style>
