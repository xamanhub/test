<!DOCTYPE html>
<html lang="zh-cn">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
	<style>
		#myCanvas:hover{
			cursor:url(https://june1.ewszjk.m.jaeapp.com/JuneWireless/3.0m/images/pencil.ico) 8 8,pointer;
		}
	</style>
</head>
<body>
<div style="display:flex;flex-wrap:wrap;width:100%;justify-content:space-between;">
    <canvas width="720" height="1280" style="border:1px solid #000" id="myCanvas">您的浏览器不支持canvas </canvas>
	<div style="display:flex;flex-wrap:wrap;width:100%;justify-content:space-between;">
		<p>线条颜色：<input type="color" name = "lineColor" id = "lineColor"/></p>
		<p>线条宽度：<input type="number" name = "lineWidth" id = "lineWidth" value="3"/></p>
		<p>导入图片：<input id="importImg" type="file" accept="image/jpeg,image/gif"/></p>
		<p>画布大小：<input id="canvasSize" type="input" placeholder="500"/></p>
	</div>
	<div style="display:flex;flex-wrap:wrap;width:100%;justify-content:space-between;">
		<p><button id="back">返回</button></p>
		<p><button id="clean">清空</button></p>
		<p><button id="save">保存</button></p>
	</div>
</div>
<div id="mask" style="z-index:1000;width:0;height:100%;opacity:0.6;background-color:#000;position:fixed;top:0;left:0;display:flex;justify-content:center;items-algin:center;overflow:hidden;">
	<button id="savePng">保存成png格式的图片</button>
	<button id="saveJpg">保存成jpg格式的图片</button>
	<button id="saveBmp">保存成bmp格式的图片</button>
</div>
<script type="text/javascript">
    var c =document.getElementById('myCanvas');
    // 标识画布并指明上下文
    var ctx = c.getContext('2d');
	
	var h = window.screen.availHeight;
	var w = window.screen.availWidth;
	c.setAttribute('width', w);
	c.setAttribute('height', h);
	
	var excuArr = [];
	var excuArrAll = [];
	objArr=[ctx]

    ctx.strokeStyle = '#000';
    ctx.lineWidth = 3;

	var addHandler = function(element, type, handler){
		element["on" + type] = handler;
	}

	var move = 'ontouchmove' in document ? 'touchmove' : 'mousemove' ;
	var down = 'ontouchstart' in document ? 'touchstart' : 'mousedown' ;
	var up = 'ontouchend' in document ? 'touchend' : 'mouseup' ;

	addHandler(c,down,function(e){
		var ev = 'ontouchmove' in document ? e.touches[0] : e ;
		let colorValue = document.getElementById('lineColor').value;
		let lineWidthValue = parseInt(document.getElementById('lineWidth').value||"3");
		ctx.strokeStyle = colorValue;
		ctx.lineWidth = lineWidthValue;
        ctx.beginPath();
        ctx.moveTo(ev.clientX,ev.clientY)
		excuArr.push({
			excuObj:0,
			property:"strokeStyle",
			value:colorValue
		},{
			excuObj:0,
			property:"lineWidth",
			value:lineWidthValue
		},{
			excuObj:0,
			method:{
				methodName:"beginPath",
				params:[]
			},
		},{
			excuObj:0,
			method:{
				methodName:"moveTo",
				params:[ev.clientX,ev.clientY]
			},
		});
		addHandler(c,move,function(e){
			var ev = 'ontouchmove' in document ? e.touches[0] : e ;
            ctx.lineTo(ev.clientX,ev.clientY);
            ctx.stroke()
			excuArr.push({
				excuObj:0,
				method:{
					methodName:"lineTo",
					params:[ev.clientX,ev.clientY]
				},
			},{
				excuObj:0,
				method:{
					methodName:"stroke",
					params:[]
				},
			});
			e.preventDefault();
		});
		addHandler(c,up,function(e){
			excuArrAll.push(excuArr);
			excuArr = [];
            c.onmousemove = null;
		});
		e.preventDefault();
	});

var oCanvas = document.getElementById("myCanvas");
var ctx = oCanvas.getContext("2d");

function draw(item,ctx){
    ctx.beginPath();
    ctx.moveTo(item.locations[0][0],item.locations[0][1]);
    for(let i = 0;i<item.locations.length;i++){
        let x = item.locations[i][0];
        let y = item.locations[i][1];
        ctx.lineTo(x,y);
        console.log(1234567)
    }
    ctx.closePath();

    ctx.fillStyle = item.color;
    ctx.fill();

    ctx.strokeStyle = "#000";
    ctx.lineWidth = 2;
    ctx.stroke();
}

function drawImg(item,w,h,ctx){
	ctx.drawImage(item,0,0,w,h)
	let objIndex = objArr.findIndex((items)=>{
		return items.src==item.src
	})
	objIndex = "objArr["+objIndex+"]";
	ctxIndex = "objArr[0]";
	excuArr.push({
		excuObj:0,
		method:{
			methodName:"drawImage",
			params:[objIndex,0,0,w,h]
		}
	})
	excuArrAll.push(excuArr)
	excuArr = [];
}

var imgId = document.getElementById("imgId");

document.getElementById("importImg").onchange = function (e){
	let files = e.target.files;
	for(let i=0;i<files.length;i++){
		let src = window.URL.createObjectURL(files[i]) // 将文件生成url
		let img = document.createElement("img");
		img.onload=function(){
			objArr.push(img);
			let w = img.width;
			let h = img.height;
			drawImg(img,w,h,ctx);
		}
		img.src=src;
	}
}
document.getElementById("back").onclick = function (){
		console.log(excuArrAll.length)
	if(excuArrAll.length>0){
		ctx.clearRect(0,0,800,500);
		excuArrAll.pop();
		for(let i=0;i<excuArrAll.length;i++){
			let excu = excuArrAll[i];
			for(let j=0;j<excu.length;j++){
				let obj = JSON.parse(JSON.stringify(excu[j]));
				if(obj.method){
					for(let h=0;h<obj.method.params.length;h++){
						if(typeof obj.method.params[h] =="string"&& obj.method.params[h].indexOf("objArr")==0){
							obj.method.params[h] = eval(obj.method.params[h])
						}
					}
					if(obj.excuObj>-1){
						objArr[obj.excuObj][obj.method.methodName](...obj.method.params)
					}else{
						drawImg(...obj.method.params)
					}
				}else if(obj.property){
					objArr[obj.excuObj][obj.property] = obj.value
				}
			}
		}
	}
}
document.getElementById("save").onclick = function (){
    document.getElementById("mask").style.width="100%"
}
document.getElementById("savePng").onclick = function (){
    downLoad(saveAsPNG(oCanvas));
	document.getElementById("mask").style.width=0;
}
document.getElementById("saveJpg").onclick = function (){
    downLoad(saveAsJPG(oCanvas));
	document.getElementById("mask").style.width=0;
}
document.getElementById("saveBmp").onclick = function (){
    downLoad(saveAsBMP(oCanvas));
	document.getElementById("mask").style.width=0;
}
document.getElementById("clean").onclick = function (){
    ctx.clearRect(0,0,800,500);
	excuArrAll = [[]];
}

// 保存成png格式的图片
function saveAsPNG(canvas) {
    return canvas.toDataURL("image/png");
}

// 保存成jpg格式的图片
function saveAsJPG(canvas) {
    return canvas.toDataURL("image/jpeg");
}

// 保存成bmp格式的图片  目前浏览器支持性不好
function saveAsBMP(canvas) {
    return canvas.toDataURL("image/bmp");
}

/**
 * @author web得胜
 * @param {String} url 需要下载的文件地址
 * */
function downLoad(url){
    var oA = document.createElement("a");
    oA.download = 'aaa';// 设置下载的文件名，默认是'下载'
	console.log(url)
    oA.href = url;
    document.body.appendChild(oA);
    oA.click();
    oA.remove(); // 下载之后把创建的元素删除
}
</script>

</body>
</html>
