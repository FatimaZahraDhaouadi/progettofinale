<!--TEAMWORK Zahra,Benito-->

<template>
    <AppCarousel/>
    <CardList/>

</template>

<script>
// @ is an alias to /src
import AppCarousel from '@/components/AppCarousel.vue';
import CardList from '@/components/CardList.vue';

export default {
  name: 'HomeView',
  components: {
    AppCarousel,
    CardList
    
  }
}
</script>
