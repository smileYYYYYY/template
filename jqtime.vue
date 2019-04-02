<template>
	<div>
		<P id="time"></P>
	</div>
</template>
<script>
import $ from 'jquery'
export default{
	name:'jqtime',
	data(){
		return{

		}
	},
	mounted:function(){
		this.timer()
	},
	methods:{
		timer:function(){
			$(function(){
			var mydate = new Date();
			var t=mydate.toLocaleString();
			$("#time").text(t);
			});
		}
	}
}
</script>