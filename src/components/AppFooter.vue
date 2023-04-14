<script>
export default{
  name:'AppFooter'
}
</script>

<template>
    <footer class="bg-dark text-white py-3">
      <div class="container ">
        <div class="row text-center">
          <div class="col-md-4">
            <h4>About Us</h4>
            <p>La nostra banca offre soluzioni finanziarie di alta qualità. Contattaci per maggiori informazioni.</p>
          </div>
          <div class="col-md-4">
            <h4>Contact Us</h4>
            <p>Email: info@company.com</p>
            <p>Phone: +1 (555) 123-4567</p>
          </div>
          <div class="col-md-4">
            <h4>Follow Us</h4>
            <ul class="list-inline">
              <li class="list-inline-item"><a href="#"><img :src="require('@/components/media/fb.png')" alt="Facebook" width="30" height="30"></a></li>
              <li class="list-inline-item"><a href="#"><img :src="require('@/components/media/instagg.png')" alt="Instagram" width="30" height="30"></a></li>
              <li class="list-inline-item"><a href="#"><img :src="require('@/components/media/linkedln.png')" alt="linkedln"  width="30" height="30"></a></li>
              <li class="list-inline-item"><a href="#"><img :src="require('@/components/media/twitt.png')" alt="twitt" width="30" height="30"></a></li>
              <li class="list-inline-item"><a href="#"><img :src="require('@/components/media/gith.png')" alt="gith"  width="30" height="30"></a></li>
            </ul>
          </div>
        </div>
        <hr>
        <div class="row">
          <div class="col-md-12 text-center">
            <p>&copy; 2023 Company, Inc.</p>
          </div>
        </div>
      </div>
    </footer>
  </template>

<style>
</style>