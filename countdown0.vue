<template>
	<div>
		<p>{{d}}天{{h}}时{{m}}分{{s}}秒</p>
	</div>
</template>
<script>
	export default{
		name:'countdown0',
		data(){
			return{
				d:0,h:0,m:0,s:0
			}
		},
		mounted:function(){
			this.countdown()
		},
		methods:{
			countdown:function(){
				const end=new Date("2019/12/31 00:00:00");
				const now=new Date();
				const t=end.getTime()-now.getTime();
				let d=Math.floor(t/1000/60/60/24);
				let h=Math.floor(t/1000/60/60%24);
				let m=Math.floor(t/1000/60%60);
				let s=Math.floor(t/1000%60);
				this.d=d;
				this.h=h>9?h:'0'+h;
				this.m=m>9?m:'0'+m;
				this.s=s>9?s:'0'+s;
				const that=this;
				setTimeout(function(){
					that.countdown()
				},1000)

			}
		}
	}
</script>