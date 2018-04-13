<template>
  <div id="app">
    <ul>
    	<li>
    		<span>星期一</span>
    		<span>星期二</span>
    		<span>星期三</span>
    		<span>星期四</span>
    		<span>星期五</span>
    		<span>第几节</span>
    		<span>修改</span>
    	</li>
    	<li v-for='(i,index) in arr'>
    		<span>{{i.one}}</span>
    		<span>{{i.two}}</span>
    		<span>{{i.three}}</span>
    		<span>{{i.fore}}</span>
    		<span>{{i.five}}</span>
    		<span>第{{i.day}}课</span>
    		<span @click='add(index)'>修改</span>
    	</li>
    </ul>
  </div>
</template>
<script>
	export default {
		
		name:'app',
		data(){
			return{
				arr:[]
			}
		},
		methods:{
			add(e){
				alert(e)
			}
		},
		created(){
			this.$http.get("http://localhost:1000/sel").then(e=>this.arr=e.body)
		}
	}
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
