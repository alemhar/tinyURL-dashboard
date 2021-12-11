<template>
  <nav id="navbar" class="navbar navbar-expand-lg navbar-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#"><img id="logo" src="@/assets/tinyurl_logo.png"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item px-5">
          <button type="button" class="btn btn-primary fw-bold text-white">CREATE TINYURL</button>
        </li>
        <li class="nav-item px-1">
          <button type="button" style="background: #002a61" class="btn fw-bold text-white">?</button>
        </li>
        <li class="nav-item px-1">
          <button type="button" style="background: #087da8" class="btn text-white">Features</button>
        </li>
        <li class="nav-item px-1">
          <button type="button" style="padding-right: 0; background: #087da8" class="btn text-white">Account<b-avatar style="height: 1rem;margin-right: 0"/></button>
        </li>
        
      </ul>
      
    </div>
  </div>
</nav>
</template>

<script>
export default {
  name: 'custom-header',
  props: {
    msg: String
  }
}
</script>
<style scoped>
#navbar {
    background: #17527d;
}
#logo {
    width: 40%;
    padding-left: 20px;
}
#navbarSupportedContent{
  flex: none !important;
}

</style>
