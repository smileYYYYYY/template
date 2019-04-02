<template>
	<div>
		<p>{{ `${day}天 ${h}小时 ${m}分钟 ${s}秒` }}</p>
	</div>
</template>
<script>
	  export default {
	  	name:'countdown1',
    data () {
      
            return {
      day: 0, h: 0, m: 0, s: 0
    }
  },
  
  mounted: function () {
    this.countdown()
  },
  methods: {
    countdown: function () {
      const end = Date.parse(new Date('2019.12.31,00:00'))
      const now = Date.parse(new Date())
      const t = end - now
      let day = parseInt(t / 1000 / 60 / 60 / 24)
      let h = parseInt(t / 1000 / 60 / 60 % 24)
      let m = parseInt(t / 1000 / 60 % 60)
      let s= parseInt(t / 1000 % 60)
      this.day = day
      this.h = h > 9 ? h : '0' + h
      this.m = m > 9 ? m : '0' + m
      this.s = s > 9 ? s : '0' + s
      const that = this
      setTimeout(function () {
        that.countdown()
      }, 1000)
    }
  }
  }
</script>
<style acoped>
  p{
    font-size: 30px;
    color: #e17052;
  }
</style>
</script>