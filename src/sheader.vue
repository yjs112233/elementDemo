<template>
	<el-row :gutter="20">
	  <el-col :span="5"><div class="grid-content bg-purple" :style="{height: rowHeight + 'px', backgroundColor:'#6F6A1A'}">

	 </div></el-col>
	  <el-col :span="13"><div class="grid-content bg-purple" :style="{height: rowHeight + 'px', backgroundColor:'#6F6A1A'}">
	  <el-menu
	    :default-active="activeIndex2"
	    class="el-menu-demo"
	    mode="horizontal"
	    @select="handleSelect"
	    background-color="#6F6A1A"
	    text-color="#fff"
	    active-text-color="#ffd04b">
	    <el-menu-item index="1"><template slot="title">我的工作台</template></el-menu-item>
	    <el-menu-item index="2"><template >我的工作台</template></el-menu-item>
	    <el-menu-item index="3" disabled>消息中心</el-menu-item>
	    <el-menu-item index="4"><a href="" target="_blank">订单管理</a></el-menu-item>
	  </el-menu>
	  </div></el-col>
	  <el-col :span="6"><div class="grid-content bg-purple" :style="{height: rowHeight + 'px', backgroundColor:'#6F6A1A'}">
	 <div class="block"><el-avatar :size="50" :src="circleUrl"></el-avatar></div>
	  </div></el-col>
	</el-row>
</template>

<script>
	export default {
		data(){
			return {
				rowHeight: 0,
				activeIndex: '1',
				        activeIndex2: '1',
						circleUrl: "https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png",
						        squareUrl: "https://cube.elemecdn.com/9/c2/f0ee8a3c7c9638a54940382568c9dpng.png",
						        sizeList: ["large", "medium", "small"]
			}
		},
		watch:{
			rowHeight(val){
				console.log(this.rowHeight)
			}
		},
		methods: {
		      handleSelect(key, keyPath) {
		        console.log(key, keyPath);
		      }
		    }
	}
</script>

<style>
	.el-row {
	    margin-bottom: 20px;
	    &:last-child {
	      margin-bottom: 0;
	    }
	  }
	  .el-col {
	    border-radius: 4px;
	  }
	  .bg-purple-dark {
	    background: #99a9bf;
	  }
	  .bg-purple {
	    background: #d3dce6;
	  }
	  .bg-purple-light {
	    background: #e5e9f2;
	  }
	  .grid-content {
	    border-radius: 4px;
	    min-height: 36px;
	  }
	  .row-bg {
	    padding: 10px 0;
	    background-color: #f9fafc;
	  }
</style>
