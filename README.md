	<div>
			时间倒计时：<span></span>
		</div>
		<script type="text/javascript">
			let Ospan=document.querySelector('span');
			let countTime=function countTime(){
				let nowTime=new Date();
				tarTime=new Date('2019/06/24 18:00:00');
				const t=tarTime-nowTime;
				//=>毫秒差中计算出对应的"时分秒";
				if(t>=0){
					let hours=Math.floor(t/1000/60/60%24);
					let minutes=Math.floor(t/1000/60%60);
					let seconds=Math.floor(t/1000%60);
					hours< 10 ? hours='0'+hours:null;
					minutes<10 ?minutes='0'+minutes:null;
					seconds<10 ?seconds='0'+seconds:null;
					Ospan.innerHTML=`${hours}:${minutes}:${seconds}`;
					return;
				}
				Ospan.innerHTML='--:--:--';
			}
			countTime();
		</script>
