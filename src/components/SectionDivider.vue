<template>
    <div class="light-background">
      <div class="width80">
        <div class="divider"></div>
      </div>
    </div>
</template>

<style>
.divider:after, .divider:before {
  position: relative;
  margin-top: 2px;
  width: 50%;
  height: 2px;
  content: ""; 
}

.divider:before {
  float: left;
  background: linear-gradient(to right, rgba(200, 200, 200, 0), rgba(200, 200, 200, 1) 50%);
}

.divider:after {
  float: right;
  background: linear-gradient(to left, rgba(100, 200, 200, 0), rgba(200, 200, 200, 1) 50%);
}

.width80 {
  width: 80%;
  margin: 0px auto;
  padding-top: 50px;
}

.light-background {
  background: #fff;
  margin-top: 50px;
  width: 100%;
  height: 100px;
}

</style>