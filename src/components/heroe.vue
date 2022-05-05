<template>
  <section class="py-5 text-center container">
    <div class="row py-lg-5">
      <div class="col-lg-6 col-md-8 mx-auto">
        <h1 class="fw-light">{{ sub }}</h1>
        <p class="lead text-muted">{{ alt }}</p>
         <img
          v-bind:src="picture"
          :alt="`${Nom} ${Prenom}`"
          :class="gender"
        /> 
        <h1>{{ Nom }} {{ Prenom }}</h1>
        <h3>Email: {{ Email }}</h3>
        <button id="male" class="male me-2" @click="getMale()">Genere un homme</button>

        <button id="female" class="female" @click="getFemale()">generer une femme</button>
        <p>
          <!-- <a href="#" class="btn btn-primary my-2">Main call to action</a>
          <a href="#" class="btn btn-secondary my-2">Secondary action</a> -->
        </p>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      sub: "Attribute Binding",
      alt: "Profil généré dynamiquement",
      Nom: 'nom',
      Prenom:'prenom',
      gender:'',
      Email: 'Email@email.mail',
      picture:'https://via.placeholder.com/128'
    };
  },
  methods:
  {
    async getMale()
    {
      const res= await fetch('https://randomuser.me/api?gender=male')
      const {results} = await res.json()
      this.Nom=results[0].name.first
      this.Prenom=results[0].name.last
      this.gender=results[0].gender
      this.Email=results[0].email
      this.picture=results[0].picture.large

    },
    async getFemale()
    {
      const res= await fetch('https://randomuser.me/api?gender=female')
      const {results} = await res.json()
      this.Nom=results[0].name.first
      this.Prenom=results[0].name.last
      this.gender=results[0].gender
      this.Email=results[0].email
      this.picture=results[0].picture.large

    }
  }
};
</script>

<style scoped>
img
{
  border-radius: 50%;
  border: 5px #333 solid;
  margin-bottom: 1rem;
}
.male {
  border-color: steelblue;
  background-color: steelblue;
}

.female {
  border-color: pink;
  background-color: pink;
  color: #333;
}

button {
  cursor: pointer;
  display: inline-block;
  background: #333;
  color: white;
  font-size: 18px;
  border: 0;
  padding: 1rem 1.5rem;
}

button:focus {
  outline: none;
}

button:hover {
  transform: scale(0.98);
}
</style>
