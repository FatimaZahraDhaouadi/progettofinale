<!-- js | parteLogica-->
<script>
export default {
  name: 'AppHeader',
  data(){
    return{
      utente:null
    }
  },
  created(){
    let prova = JSON.parse(sessionStorage.getItem('user'))
    if(prova){
        this.utente=JSON.parse(sessionStorage.getItem('user'))
        console.log(this.utente)
    }
  },
}
</script>
<!-- HTML -->
<template>
 <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-dark">
        <div class="container-fluid">
          <router-link to="/" class="navbar-brand fw-bold">
            <img :src="require('@/components/media/logo.png')" alt="NBC" width="170" height="150" class="d-inline-block align-text-center">
            NBC
          </router-link>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav ms-auto mr-auto text-white">
              <li class="nav-item">
                <router-link to="/" class="nav-link active">Home</router-link>
              </li>
              <li class="nav-item">
                <router-link v-if="!utente"  to="/logIn" class="nav-link active">LogIn</router-link>
                <router-link v-else  to="/me" class="nav-link active">Personal Area</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/about" class="nav-link active">About</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/contacts" class="nav-link active">Contacts</router-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </header> 
</template>

<!-- css -->
<style scoped>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    
}

.navbar-brand {
    font-size: 60px;
    font-weight: bold;
    color: rgb(233, 233, 233);
}


.navbar-nav .nav-link {
  color: rgb(233, 233, 233);
    margin-right: 100px;

}
</style>
