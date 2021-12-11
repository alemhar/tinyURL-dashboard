<template>
  <div class="col-3 text-center">
    <div class="card">
      <div class="card-body">
        <p class="card-text text-secondary">{{ name }}</p>
        <h4 id="counts" class="card-title fs-bold">{{ count }}</h4>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["name", "count"],
};
</script>

<style scoped>
#counts {
  font-weight: 800 !important;
}
</style>