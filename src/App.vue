<script setup lang="ts">

  import SearchBar from './components/SearchBar.vue';
  import OutputBox from './components/OutputBox.vue';
  import { ref } from 'vue';
  
  const receivedText = ref('');

  const receiveText = (text:any) => {
    console.log(text);
    receivedText.value = text;
  };
</script>

<template>
  <div class="wrapper">
    <div class="not-footer">
        <header>
          <h1>WikiWhat.</h1>
          <h2>Tip-of-the-tongue Wikipedia search.</h2>
          <hr>
        </header>
      <main>
        <SearchBar @emit-search="receiveText"/>
        <OutputBox :receivedText="receivedText"/>
      </main>
    </div>

    <footer>
      <nav>
        <a target="_blank" href="https://github.com/desmondbergen">
          <div class="link">
            <img src="./components/icons/github-mark.png" alt="My github">
            <p>desmond bergen</p>
          </div>
        </a>
      </nav>
    </footer>
  </div>
</template>
<style scoped>
  .wrapper{
    margin-top:10rem;
    display:flex;
    flex-direction:column;
    align-items:center;
  }
  .not-footer{
    display:flex;
    flex-direction:column;
    align-items:center;
    max-width:50rem;
  }
  h1, h2, p{
    font-family:"Kode Mono",Helvetica,Arial,sans-serif;
  }
  header h1{
    font-size:32px;
  }
  header h2{
    font-size:24px;
  }
  footer{
    margin:1rem;
    position:absolute;
    left:0%;
    bottom:0%;
  }
  .link{
    display:flex;
    align-items:center;
    color:white;
    opacity:0.5;
    transition: opacity 0.5s;
  
  }
  .link p{
    margin-top:0.2rem;

  }
  .link img{
    height:2rem;
    width:2rem;
    margin-right:0.5rem;
  }
  .link:hover{
    opacity:1;
  }
</style>