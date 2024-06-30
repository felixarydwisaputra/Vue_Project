<script setup>
  import { ref, onMounted } from 'vue'

  const quote = ref({"text" : "", "author" : ""})
  const quotes = ref([
    {
      "text" : "Where do you Live, You have an Account?",
      "author" : "Abang Ujang"
    },
    {
      "text" : "You have an Account?",
      "author" : "Stefan William"
    },
    {
      "text" : "I Like Your Enemy",
      "author" : "Michael Salman"
    },
    {
      "text" : "I Cant Help You, But you",
      "author" : "Albert Sadino"
    }
  ])

    const randomQuote = () => {
      const random = Math.floor(Math.random() * quotes.value.length)
      quote.value = quotes.value[random]
    }

    onMounted(randomQuote)
    
</script>

<template>
  <div class="container">
    <div class="card">
      <h1>Random Quote Generator</h1>
      <div class="quote">
        <p>"{{ quote.text }}"</p>
        <cite>-- {{ quote.author }}</cite>
      </div>
      <button @click="randomQuote">Generate Quote</button>
    </div>
  </div>
</template>

<style scoped>
  .container{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90dvh;
    min-width: 100%;
  }
  
  .card{
    padding: 1rem 3rem;
    padding-bottom: 2rem;
    text-align: center;
    min-width: 30%;
    box-shadow: 1px 1px 10px #ccc;
    border-radius: 10px;
  }

  .quote{
    background-color: #DDD;
    margin: 2rem;
    padding-bottom: 2rem; 
    border: 1px solid #ccc;
    padding-top: 1rem;
  }

  button{
    padding: .5rem 2rem;
    cursor: pointer;
  }
</style>