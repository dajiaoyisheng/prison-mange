<template>
  <div>
    <div class="toolbar">
    <div class="block Polygon-block">
      <div class="wrap">
        <input type="radio" name="type" id="rect"><div class="label">矩形</div>
      </div>
      <div class="wrap">
        <input type="radio" name="type" id="round"><div class="label">圆形</div>
      </div>
      <div class="wrap">
        <input type="radio" name="type" id="ellipse"><div class="label">椭圆</div>
      </div>
    </div>
    <div class="block style-block">
      <label for="size">线条粗细 <input type="range" name="size" id="size" step="0.5" min="0.5" max="10" value="1"><span>1</span></label>
      <label for="strokeColor">描边颜色 <input type="color" name="strokeColor" value="#ff0000" id="strokeColor"><span>#ff0000</span></label>
    </div>
    <div class="block">
      <button id="cancel">撤 销</button>
      <button id="next">重 做</button>
      <button id="clear">清 空</button>
    </div>
    <div class="block">
      <button id="export">导 出</button>
      <button id="import">导 入</button>
    </div>
    <div class="block info-block">
      <div class="info" id="pos">
        X: <span> 0</span>
        Y: <span> 0</span>
      </div>
    </div>
  </div>
  <div>
    <div class="left" style="width: 18%;"></div>
    <div class="center">
      <canvas id='canvas' width="1000" height="600">浏览器不支持canvas</canvas>
    </div>
  </div>
</div>
</template>

<script>
    import Draw from './draw/action';

    export default {
        name: 'App',
        mounted() {
          let draw = new Draw('canvas');
          document.getElementsByClassName('toolbar')[0].addEventListener('click',function(e){
              if(e.target.getAttribute('type')=='radio'){
                draw.setDrawState(true);
                var lineWidth = document.getElementById('size').value;
			          var strokeStyle = document.getElementById('strokeColor').value;
			          var type = 'solid';
                var elems = document.getElementsByName('type');
                for(var i = 0,len = elems.length;i < len;i++){
			            if(elems[i].checked){
				            type = elems[i].id;break;
			            }
		            }
                draw.setShape(lineWidth, strokeStyle, type);
                draw.init();
              }
          },false);

          document.getElementById('clear').onclick = draw.clear;
          document.getElementById('export').onclick = function() {
            let data = draw.exportGraphs();
            console.log(JSON.stringify(data));
          }
          document.getElementById('import').onclick = function() {
            let data = '[{"pos":{"x":223,"y":71},"type":"rect","points":[{"x":170,"y":36},{"x":222.5,"y":36},{"x":275,"y":36},{"x":275,"y":71},{"x":275,"y":106},{"x":222.5,"y":106},{"x":170,"y":106},{"x":170,"y":71}],"sides":5,"stars":5,"lineWidth":"1","strokeStyle":"#ff0000","fillStyle":"#f00","isFill":false},{"pos":{"x":395,"y":87},"type":"round","points":[{"x":439,"y":108}],"sides":5,"stars":5,"lineWidth":"1","strokeStyle":"#ff0000","fillStyle":"#f00","isFill":false,"radius":49},{"pos":{"x":575,"y":132},"type":"ellipse","points":[{"x":644,"y":140},{"x":578.9733829441328,"y":97.72957210685465}],"sides":5,"stars":5,"lineWidth":"1","strokeStyle":"#ff0000","fillStyle":"#f00","isFill":false,"angle":0.11542666036692473,"a":69,"b":34.5}]';
            draw.loadData(JSON.parse(data));
          }

        }
    }
</script>
<style>
    body {
        margin: 0;
    }

    .toolbar {
        /* padding: 10px; */
        color: #555;
        font-size: 14px;
        display: flex;
        flex-flow: row nowrap;
        min-width: 1000px;
    }

    .block {
        padding: 4px;
        height: 90px;
        display: flex;
        border: 1px solid #eee;
        border-width: 1px 0 1px 1px;
        flex-flow: column wrap;
        justify-content: space-around;
    }

    .style-block {
        width: 240px;
    }

    .style-block span {
        padding-left: 10px;
    }

    .Polygon-block {
        width: 240px;
    }

    .Polygon-block input[type=number] {
        /* margin-top: 4px; */
        width: 40px;
        padding: 2px 4px;
        border: 1px solid #ddd;
        border-radius: 4px;
        outline: none;
    }

    .info-block {
        width: 120px;
        border: 1px solid #eee;
    }

    .info {
        line-height: 2;
        padding-left: 10px;
    }

    .info span {
        font-size: 12px;
        color: #e00;
    }

    .wrap {
        position: relative;
        width: 80px;
        height: 30px;
        text-align: center;
        overflow: hidden;
    }

    .wrap .label {
        padding: 4px;
        border-radius: 5px;
    }

    .wrap [type=radio] {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 99;
        opacity: 0;
        cursor: pointer;
    }

    .wrap [type=radio]:checked~.label {
        /* 覆盖radio */
        background: hsl(200, 100%, 40%);
        color: hsl(0, 0%, 100%)
    }

    .desc {
        line-height: 2;
        color: hsl(0, 0%, 80%)
    }

    label {
        display: block;
        padding: 2px;
    }

    button {
        margin-left: 10px;
        border: 1px solid #ddd;
        border-radius: 4px;
        background: #fff;
        padding: 3px 20px;
        cursor: pointer;
        outline: none;
    }

    button:hover {
        background: #eee;
    }

    canvas {
        float: left;
    }
</style>
