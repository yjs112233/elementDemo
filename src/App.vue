<template>
  <div id="app">
	  <el-container>
	    <el-header :style = "{height: head.init + 'px', backgroundColor:'#6F6A1A'}">
			<sheader ref="sheader"></sheader>
		</el-header>
	    <el-main :style = "{height: main.init + 'px'}">Main</el-main>
	    <el-footer :style = "{height: foot.init + 'px'}">Footer</el-footer>
	  </el-container>
  </div>
</template>

<script>
	import sheader from './sheader.vue'
export default {
	components:{
		sheader
	},
	data(){
		return {
			head : {
			  init : 20,
			  size : 0.08
			},
			main : {
			  init : 20,
			},
			foot : {
			  init : 20,
			  size : 0.1
			}
		}
	},
	beforeMount(){
		const h = document.documentElement.clientHeight;
		sessionStorage.setItem("h", h);
	},
	mounted(){
		const h = sessionStorage.getItem("h");
		this.head.init = h * this.head.size;
		this.$refs.sheader.rowHeight = this.head.init;
		console.log(this.$refs.sheader.rowHeight)
		this.main.init = h * (1 - this.head.size - this.foot.size);
		this.foot.init = h * this.foot.size;
	},
  methods: {
    startHacking () {
      this.$notify({
        title: 'It works!',
        type: 'success',
        message: 'We\'ve laid the ground work for you. It\'s time for you to build something epic!',
        duration: 5000
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, sans-serif;
  text-align: center;
}

.el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
