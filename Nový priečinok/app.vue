<template>
  <main> 

  <h1> Zoznam ludi </h1>
  <section class="list"> 
    <section v-for="person of persons" v-bind:key="person" class="card-container"> 
      <section v-bind:class="{'card': true, 'adult': person.age >= 18}" class="card"> 
      <article class="info"> 
        <div class="name">{{person.fname}} {{person.lname}}</div>
        <div class="birthday"> {{person.age}} <span class="year-title">years</span> </div>
      </article>
      <footer class="footer-card">
        <span class="btn edit"> Edit </span>
        <span class="btn remove"> Remove </span>

      </footer>
      </section>
    </section>
  </section>

  </main>
</template>

<script setup>
let persons = [
        {
            fname: "Magdalena",
            lname: "Mikulova",
            age: 22
        },
        {
            fname: "Mirka",
            lname: "Makovicova",
            age: 30
        },
        {
            fname: "Hugo",
            lname: "Hugovic",
            age: 15
        },
        {
            fname: "Miki",
            lname: "Hric",
            age: 19
        },
        {
            fname: "Andrea",
            lname: "Veresova",
            age: 40
        },
        {
            fname: "Nora",
            lname: "Mojsejova",
            age: 13
        },
    ]
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;500;600;700&display=swap');
    body {
        font-size: 10px;    
        font-family: 'Oswald', sans-serif;
        padding: 1rem;
    }
    main {
        display: flex;
        flex-direction: column;
        gap: .75rem;
    }
    .list {
        display: flex;
        gap: 20px;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: stretch;
        font-size: 1.2rem;
    }
    .card-container {
        flex-grow: 1;
    }
    .card {
        background: rgba(255,255,255, 1);
        border: 1px solid #bbb;
        color: #444;
        box-shadow: 0 3px 5px rgba(0,0,0,.2);
        border-top-width: 5px;
        border-top-color: dodgerblue;
    }
    .card.adult {
        border-top-color: orange;
    }
    .card:hover {

    }
    .info {
        padding: 1rem;
        text-align: center;
        font-size: 1.3rem;
    }
    .name {


    }
    .age {
        font-weight: 300;
        font-size: 1rem;
    }
    .year-title {
        color: #bbbbbb;
    }
    .footer-card {
        display: flex;
    }
    .btn {
        padding: .75rem 2rem;
        color: white;
        width: 50px;
        flex-grow: 1;
        text-align: center;
        transition: .5s;
        font-size: 1rem;
    }
    .btn.edit {
        background: rgb(91, 236, 91);
    }
    .btn.remove {
        background: red;
    }
    .btn:hover {
        opacity: .3;
        cursor: pointer;;
    }
</style>