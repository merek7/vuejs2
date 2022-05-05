<template>
  <section class="py-5 text-center container">
    <div class="row py-lg-5">
      <div class="col-lg-6 col-md-8 mx-auto">
        <h1 class="fw-light">{{ sub }}</h1>
        <p class="lead text-muted">{{ alt }}</p>
         <img
          v-bind:src="picture"
          :alt="`${User} ${Prenom}`"
          :class="gender"
        /> 
        <h1>{{ Nom }} {{ Prenom }}</h1>
        <h3>Email: {{ email }}</h3>
        <button class="male me-2">Genere un homme</button>

        <button class="female">generer une femme</button>
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
      alt: "Humain generer dynamiquement",
      Nom: 'User',
      Prenom:'Test',
      Email: 'Te',
      picture:'https://randomuser.me/api/portraits/men/10.jpg'
    };
  },
};
</script>

<style scoped>
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
