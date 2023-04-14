<script>
import CardEl from './CardEl.vue';

export default {
    name: "CardList",
    data() {
        return {
            list: [{
                    icon: "<i class=\"ms_icons fa-solid fa-money-bill-transfer\"></i>",
                    title: "VERSAMENTO"
                }, {
                    icon: "<i class=\"ms_icons fa-solid fa-money-check-dollar\"></i>",
                    title: "PRELIEVO"
                }, {
                    icon: "<i class=\"ms_icons fa-solid fa-building-columns\"></i>",
                    title: "SALDO"
                }
            ]
        };
    },
    components: { CardEl }
}

</script>
<template>
    <section class="py-5">
        <h2 class=" text-center pt-3 pb-3 fw-bold">OPERATION</h2>
        <div class="container pb-5">

            <div class="row row-cols-lg-3 row-cols-sm-1 pb-5">
             <CardEl v-for="(item, index) in list" :key="index" :item="item" />
            <!--<div class="col" v-for="(item, index) in list" :key="index">
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
                </div>  -->       
            </div>
        </div>
    </section>
</template>

           


    

<style></style>
