<template>
  <div class="hello">
      <img src="../assets/upload.png" alt="" id="img">
      <input type="file" accept="image/png,image/jpg,image/jpeg" @change="change($event)">
  </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  created() {
  	this.$on('getdata', function(data){
  		console.log('hello页面', data)
  	})
  },
  methods : {
    change( event ) {
        let image = document.getElementById('img'); //预览对象
        const obj = this.clip(event , {
          resultObj : image,
          aspectRatio : 1
        })
				console.log(obj)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    img{
        display: block;
        width: 120px;
        height: 120px;
    }
    h3{
        text-align: center;
    }
    h1, h2 {
      font-weight: normal;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      display: inline-block;
      margin: 0 10px;
    }

    a {
      color: #42b983;
    }
</style>
