<script>
export default{
    name: 'CardEl',
    
    props:{
     item:Object,
   }
    
}
</script>

<template>
    <div class="col">
        <div class="card">
            <div class="card-body">
                <h5 class="text-center" v-html="item.icon"></h5>
                <h5 class="card-title text-center py-2">{{ item.title }}</h5>
                <p class="card-text text-center">
                    With supporting text below as a natural lead-in to
                    additional content.
                </p>
            </div>
        </div>
    </div>
</template>

<style>
</style>