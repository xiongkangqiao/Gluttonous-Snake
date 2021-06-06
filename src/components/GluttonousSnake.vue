<template>
  <div class="project" style="position: relative;width: 100%;height: 540px;background-color: #3493cb">
    <div class="mapDiv" style="position: absolute;top: 50%;left: 50%;transform: translate(-50%, -50%);width: 300px;height: 300px;background-color: #3ba1c4">

    </div>
  </div>
</template>

<script>
export default {
  name: 'GluttonousSnake',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      snakeBody: [[3, 1, 'head'], [2, 1, 'body'], [1, 1, 'body']],
      direct:'right',
    }
  },
  methods:{
    init(){
      for (var i = 0; i < this.snakeBody.length; i++) {
        var snake = document.createElement('div');
        snake.style.width = 20 + 'px';
        snake.style.height = 20 + 'px';
        snake.style.position = 'absolute';
        snake.style.left = this.snakeBody[i][0] * 20 + 'px';
        snake.style.top = this.snakeBody[i][1] * 20 + 'px';
        snake.classList.add(this.snakeBody[i][2]);
        document.getElementsByClassName('mapDiv')[0].appendChild(snake).classList.add('snake');
        //判断蛇头自身的方向
        switch (this.direct) {
          case 'right':
            break;
          case 'up':
            snake.style.transform = 'rotate(270deg)'
            break;
          case 'left':
            snake.style.transform = 'rotate(180deg)'
            break;
          case 'down':
            snake.style.transform = 'rotate(90deg)'
            break;
          default:
            break;
        }
      }
    }
  },
  mounted() {
    this.init()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/deep/ .snake{
  background-color: #c8378c;
  border-radius: 10px;
}
</style>
