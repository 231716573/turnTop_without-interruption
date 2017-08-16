# turnTop_without-interruption
无间断翻过效果

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<style type="text/css">
#up_zzjs{border:1px solid #ccc;width:170px;height:82px;line-height:20px;overflow:hidden;}
#up_zzjs #up_li{list-style-type:none;margin:0;padding:0;margin-left:6px;}
/*系统支持ie8就选line-height:16px;，但不支持opera 否则选line-height:20px;*/
#up_zzjs #up_li a{font-size:12px; line-height:16px;}
</style>

<div id="up_zzjs">
<div id="marqueebox">
<div id="up_li"><a href="http://www.zzjs.net/" target="_blank"><span style="color:#FF0000">滚动文字一号</span></a></div>
<div id="up_li"><a href="http://www.zzjs.net/" target="_blank"><span style="color:#3333FF">滚动文字二号</span></a></div>
<div id="up_li"><a href="http://www.zzjs.net/" target="_blank"><span style="color:#3333FF">滚动文字三号</span></a></div>
<div id="up_li"><a href="http://www.zzjs.net/" target="_blank"><span style="color:#3333FF">滚动文字四号</span></a></div>
<script language="javascript">
function startmarquee(lh,speed,delay) {
	var p=false;
	var t;
	var o=document.getElementById("marqueebox");
	o.innerHTML+=o.innerHTML;
	o.style.marginTop=0;
	o.onmouseover=function(){p=true;}
	o.onmouseout=function(){p=false;}
	function start(){
		t=setInterval(scrolling,speed);
		if(!p) o.style.marginTop=parseInt(o.style.marginTop)-2+"px";
	}

	function scrolling(){
		if(parseInt(o.style.marginTop)%lh!=0){
		o.style.marginTop=parseInt(o.style.marginTop)-2+"px";
		if(Math.abs(parseInt(o.style.marginTop))>=o.scrollHeight/2) o.style.marginTop=0;
		}else{
			clearInterval(t);
		setTimeout(start,delay);
		}
	}
	setTimeout(start,delay);
}
startmarquee(20,20,1500);
</script>
</body>
</html>
```