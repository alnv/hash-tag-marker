hash-tag-marker
===============

HashTagMarker - Tutorial: Mit Javascript Hash Tags markieren!

### [Example](http://alexandernaumov.de/examples/hash-tag-marker/)
### [Mehr Infos](http://alexandernaumov.de/blog/hashtags-in-einem-textarea-hervorheben.html)

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <title>Tutorial: #Hashtags makieren!</title>
    <meta name="author" content="Alexander Naumov">
		<style>
				/*
				* BASE STYLES
				*/
				html{
					background: #f1f1f1;
					height: 100%;
				}
				
				body{
					font-family: "Comic Sans MS", cursive, sans-serif;
					height: 100%;
					color: #3c3c3c;
					
				}
				
				.wrapper{
					position: relative;
					top: 15%;
					width: 90%;
					max-width: 450px;
					margin: 0 auto;
					text-align: center;
					padding: 2.5%;
					background: #fff;
					border: 1px solid #cccccc;
				}
				h1{
					margin: 0;
					padding: 0;
					font-size: 20px;
					font-size: 1.25rem;
					line-height: 1.75em;
				}
				h2{
					margin: 0;
					padding: 0;
					font-size: 18px;
					font-size: 1.125rem;
					line-height: 1.75em;
					margin-bottom: .5em;
				}
				.blue{
					color: #009bd3;
				}
				
				textarea{
					border: 1px solid #009bd3;
					border-radius: 5px;
					background: #fff;
					color: #3c3c3c;
					font-size: 16px;
					font-size: 1rem;
					font-family: "Comic Sans MS", cursive, sans-serif;
					resize: none;
					outline: none;
					width: 100%;
					height: 5em;
					-webkit-box-sizing: border-box;
					-moz-box-sizing: border-box;
					-o-box-sizing: border-box;
					box-sizing: border-box;
					margin: 0;
					padding: 5px;
				}
				
				/*
				* MAGIC
				*/
				.textarea{
					position: relative;
					overflow: hidden;
				}
				
				.content{
					position: relative;
				}
				
				.tag{
					background: #009bd3;
					color: #fff;
					border-radius: 5px;
				}
				
				.hashtags{
					text-align: left;
					position: absolute;
					left: 0;
					top: 0;
					border-radius: 5px;
					padding: 1px;
					margin: 5px;
					
					/*
					* text color have to be unvisible
					*/
					color: rgba(0,0,0,0);
					
				}
				
				
				
		</style>
</head>

<body>

	<div class="wrapper">
		
		<div class="header">
			<h1>Tutorial: #Hashtags makieren!</h1>
		</div>
		
		<div class="example">
			
			<h2>Beispiel: Schreibe etwas mit <span class="blue">#hashtag</span></h2>
			
			<div class="textarea">
				<textarea class="content"></textarea>
				<div class="hashtags"></div>
			</div>
			
		</div>
		
	</div>

</body>

	<script>
		
		(function(){
			
			'use strict';
			
			var content = document.querySelector('.content');
			var hashtags = document.querySelector('.hashtags');
			var str;
			content.addEventListener('keyup', function(){
				str = content.value;
				str = str.replace(/#([a-zA-Z0-9]+)/g, '<span class="tag">#'+'$1'+'</span>');
				hashtags.innerHTML = str;
			});
			
		})();
		
	</script>

</html>
```
