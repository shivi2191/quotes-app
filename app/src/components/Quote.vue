<template>
  <div class="col-sm-3 col-md-6 col-lg-4">
    <div id="idCard" class="tileContainerClass">
      <div class="card fontclass">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.tileContainerClass {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 100%;
  text-align: center;
  margin: 40px;
}

.tileContainerClass:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

#idCard {
  padding: 2px 16px;
}

.fontclass {
  font-family: fantasy;
}
</style>