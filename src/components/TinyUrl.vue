<template>
  <div class="row px-3 link-container">
    <div id="" class="col-1 d-flex align-items-center">
      <img
        :src="favicon"
        style="width: 30px"
      />
    </div>
    <div id="info" class="col-11">
      <div class="row">
        <div class="fw-bold">{{ short_url }}</div>
        <div class="fw-light">{{ url }}</div>
        <div class="col fw-light">{{ elapse_time }} hours ago</div>
        <div class="col fw-light" style="text-align: right">
          {{ clicks }} Clicks
        </div>
      </div>
    </div>
    <hr />
  </div>
</template>

<script>
export default {
  props: [
    'short_url',
    'url',
    'elapse_time',
    'clicks',
    'favicon'
  ],
};
</script>

<style scoped>
.link-container {
  background: lightgray;
}
#info {
  padding-left: 18px;
}
</style>