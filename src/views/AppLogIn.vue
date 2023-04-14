<script>

    export default{
        data(){
            return{
                email:'',
                password:'',
                isVerified:null,
                userList:[{
                    email:'za@email.com',
                    password:'Ciao!123',
                    
                }]
            }
        },
        methods:{
            getUser(){
                if (this.userList[0].email === this.email  && this.userList[0].password === this.password) {
                    this.isVerified = 'true'
                }else{
                    this.isVerified = 'false'
                }
                console.log(this.isVerified)
                
                if (this.isVerified==='true') {
                    sessionStorage.setItem('user', JSON.stringify({email:this.email , password: this.password}))
                }
                setTimeout(()=> {
                    this.isVerified = null;
                }, 1000
                )
            }        
        },
        computed:{
             getEmail(){
           
                let REGEXEMAIL = "[a-zA-Z0-9._%-]+@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,4}";
                let regex = new RegExp(REGEXEMAIL);
                return regex.test(this.email);

             },
             getPassword(){

                let REGEXPASSWORD = "((?=.*\\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[!@#$%]).{8,20})";
                let regex = new RegExp(REGEXPASSWORD);
                return regex.test(this.password);
             }
             
        },
        
    }
</script>

<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-6 my-3">
                <form  @submit.prevent="getUser" class="my-3 py-5">
                    <div  v-show = "isVerified" :class="{'text-danger':isVerified==='false','text-success':isVerified==='true'}">             
                        {{ isVerified === 'true' ? 'Utente coorrettamente Loggato' : 'Password o Email non valida'}} 
                    </div>
                    <div class="mb-3">
                        <label for="exampleInputEmail1" class="form-label">Email address</label>
                        <input v-model.trim="email" type="email" class="form-control" :class="{'is-invalid':!getEmail&&this.email.length>0}" id="exampleInputEmail1" aria-describedby="emailHelp">
                    </div>
                    <div class="mb-3">
                        <label for="exampleInputPassword1" class="form-label">Password</label>
                        <input v-model.trim="password" type="password" class="form-control" :class="{'is-invalid':!getPassword&&this.password.length>0}" id="exampleInputPassword1" aria-describedby="passwordHelp">
                    </div>
                    <button type="submit" class="btn btn-primary">Submit</button>
                </form>
            </div>
        </div>
    </div>
</template>

<style></style>