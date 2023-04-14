<script>
export default {
    name: 'PersonalArea',
    data() {
        return {
            user: null,
            importo: 0,
            prelievo: 0,
            showSaldo: false,
            errore: false
        }
    },
    created() {
        let prova = JSON.parse(sessionStorage.getItem('user'))
        if (prova) {
            this.user = { ...JSON.parse(sessionStorage.getItem('user')), saldo: 1000 }
            console.log(this.user)
        }
    },
    mounted() {
        if (!this.user) {
            setTimeout(() => {
                this.$router.push({
                    name: 'logIn'
                })
            }, 1500)
        }
    },
    methods:{
        versa(){
          this.user.saldo += this.importo 
          console.log(this.user.saldo)
          this.showSaldo = true;
          setTimeout(()=>{
          this.showSaldo = false;     
          },1000)
        },
        preleva(){
            if (this.user.saldo<this.prelievo) {
                this.errore=true
                setTimeout(()=>{
                    this.errore = false;
                },1000)
            }else {
                this.user.saldo -= this.prelievo
            }
        }

    }

}
</script>

<template>
    <div class="container ">
        <div class="row justify-content-center">
            <div class="col-6 my-5 py-5">
                <div v-if="user" class="py-3">
                    <h1 class="text-center text-danger">
                        Pagina dell'utente : {{ user.email }}
                    </h1>
                    <div class="ma-3">
                        <div class="mb-3 w-50">
                            <label for="exampleInputEmail1" class="form-label">Prelievo</label>
                            <input v-model="prelievo" type="number" min="0" class="form-control" id="exampleInputEmail1"
                                aria-describedby="emailHelp">
                            <div v-if="errore" class="text-danger">
                                Hai superato limite carta
                            </div>
                            <button @click="preleva"  min="0"  class="btn btn-primary mt-3">Preleva</button>
                        </div>
                      
                        <div class="mb-3 w-50">
                            <label for="exampleInputPassword1" class="form-label">Versamento</label>
                            <input v-model="importo" type="number" class="form-control" id="exampleInputPassword1">
                            <button @click="versa"  min="0" class="btn btn-primary mt-3">Versa</button>
                        </div>
                        <p v-if="showSaldo" class="text-success"> Il saldo disponibile è pari :{{user.saldo}}</p>
                        <button v-on:click="showSaldo = !showSaldo" class="btn btn-primary btn-lg">Mostra saldo</button>
                    </div>
                </div>
                <div v-else class="py-3">
                    <h1 class="text-danger text-center">
                        Utente non registrato
                    </h1>
                </div>

            </div>
        </div>
    </div>
</template>

<style></style>