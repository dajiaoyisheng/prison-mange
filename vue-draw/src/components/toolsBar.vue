<template>
  <div>
    <ul class="draw_controller cf">
      <li class="normal pencil" title="铅笔"></li>
      <li class="normal handwriting" title="涂鸦"></li>
      <li class="normal line showLine" title="线条大小"></li>
      <li class="normal showColor" id="chooseColor" title="选择颜色"></li>
      <li class="normal rubber" title="橡皮擦"></li>

      <span>|</span>

      <li class="normal drawLine" title="画直线"></li>
      <li class="normal square" title="方形"></li>
      <li class="normal circle" title="圆"></li>
      <li class="normal fill" title="填充前景"></li>

      <span>|</span>

      <li class="normal cancel" title="撤销上一个操作"></li>
      <li class="normal next" title="重做上一个操作"></li>
      <li class="normal clearContext" title="清屏"></li>
      <li class="normal save" title="保存"></li>
      <li class="normal downloadImage" title="下载">
          <a href="#" download="picture.png" id="downloadImage_a"></a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "toolsBar",
};
</script>

<style scoped>
.cf {
  display: block;
  zoom: 1;
}
* html .cf {
  height: 1%;
}
.cf:after {
  content: " ";
  display: block;
  height: 0;
  clear: both;
  visibility: hidden;
}

.draw_controller {
    width: 860px;
    height: 60px;
    padding-top: 24px;
}

.draw_controller li a {
    display: block;
    width: 30px;
    height: 30px;
}

.draw_controller li {
    float: left;
    width: 30px;
    height: 30px;
    box-shadow: 0 0 4px #49a4db;
    margin: 0 10px;
    cursor: pointer;
    list-style: none;
    background-image: url(../assets/images/draw.png);
    background-color: #FFF;
    background-repeat: no-repeat;
    -webkit-transition: background-color 0.2s ease-in-out;
}

.draw_controller li:nth-child(1) {
    background-position: 0px 0px;
}

.draw_controller li:nth-child(2) {
    background-position: -30px 0px;
}

.draw_controller li:nth-child(3) {
    background-position: -60px 0px;
}

.draw_controller li:nth-child(4) {
    background-position: -90px 0px;
}

.draw_controller li:nth-child(5) {
    background-position: -120px 0px;
}

.draw_controller li:nth-child(7) {
    background-position: -150px 0px;
}

.draw_controller li:nth-child(8) {
    background-position: -180px 0px;
}

.draw_controller li:nth-child(9) {
    background-position: -210px 0px;
}

.draw_controller li:nth-child(10) {
    background-position: -240px 0px;
}

.draw_controller li:nth-child(12) {
    background-position: -270px 0px;
}

.draw_controller li:nth-child(13) {
    background-position: -300px 0px;
}

.draw_controller li:nth-child(14) {
    background-position: -330px 0px;
}

.draw_controller li:nth-child(15) {
    background-position: -360px 0px;
}

.draw_controller li:nth-child(16) {
    background-position: -390px 0px;
}

.draw_controller li:hover {
    background-color: #49a4db;
    box-shadow: 0 0 4px #99bce2;
}

.draw_controller li.active {
    background-color: #49a4db;
    box-shadow: 0 0 4px #99bce2;
}

.draw_controller li:nth-child(1):hover,
.draw_controller li:nth-child(1).active {
    background-position: 0px -30px;
}

.draw_controller li:nth-child(2):hover,
.draw_controller li:nth-child(2).active {
    background-position: -30px -30px;
}

.draw_controller li:nth-child(3):hover,
.draw_controller li:nth-child(3).active {
    background-position: -60px -30px;
}

.draw_controller li:nth-child(4):hover,
.draw_controller li:nth-child(4).active {
    background-position: -90px -30px;
}

.draw_controller li:nth-child(5):hover,
.draw_controller li:nth-child(5).active {
    background-position: -120px -30px;
}

.draw_controller li:nth-child(7):hover,
.draw_controller li:nth-child(7).active {
    background-position: -150px -30px;
}

.draw_controller li:nth-child(8):hover,
.draw_controller li:nth-child(8).active {
    background-position: -180px -30px;
}

.draw_controller li:nth-child(9):hover,
.draw_controller li:nth-child(9).active {
    background-position: -210px -30px;
}

.draw_controller li:nth-child(10):hover,
.draw_controller li:nth-child(10).active {
    background-position: -240px -30px;
}

.draw_controller li:nth-child(12):hover,
.draw_controller li:nth-child(12).active {
    background-position: -270px -30px;
}

.draw_controller li:nth-child(13):hover,
.draw_controller li:nth-child(13).active {
    background-position: -300px -30px;
}

.draw_controller li:nth-child(14):hover,
.draw_controller li:nth-child(14).active {
    background-position: -330px -30px;
}

.draw_controller li:nth-child(15):hover,
.draw_controller li:nth-child(15).active {
    background-position: -360px -30px;
}

.draw_controller li:nth-child(16):hover,
.draw_controller li:nth-child(16).active {
    background-position: -390px -30px;
}

.draw_controller span {
    float: left;
    width: 4px;
    padding-top: 8px;
    color: #ccc;
    margin: 0 10px;
}

.draw_controller .normal {
    border-radius: 50%;
}

.draw_controller .active {
    border-radius: 50%;
}

</style>
