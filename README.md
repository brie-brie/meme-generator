<html>
<html>
<head>
		<!-- <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">-->
	<title></title>
	<style>
	#div-container{
			border: 10px solid black;
			width: 60%;
			padding: 370px;
			text-align: center;
			margin: -8px;
			background-color: rgb(33, 65, 248);
			
	}
	h1{
		color:white
	}
	
</style>
</head>
<body>
		<div id="div-container">
			<h1 class="txt-center" >Hello User! Welcome to Memetastic</h1>
			
		<div class="container mx-auto col-md-4">
        	<div class="input-group my-4 text-center text-muted">
        <h3><em>Please enter a number between 0-99</em></h3>
        <input type="text" id="input-meme" placeholder="Enter Number Here" class="form-control p-4"><br></br>
        <div class="input-group-append">
		
			<button type="button" class="btn btn-primary" id="submit-btn">Meme Generator</button> 
			<br></br>
		
                        </div>
                    </div>
					</div>
								
        <div class="card" id="card-data">
		<h3 id="name-h3"></h3>

        <img id="img-meme" src="" width="250px"/>
        </div>
	</div>
    
    
		<script 
		src="https://code.jquery.com/jquery-3.4.1.js"
		integrity="sha256-WpOohJOqMqqyKL9FccASB9O0KwACQJpFTUBLTYOVvVU="
		crossorigin="anonymous"></script>


		<!-- <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
		<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
		<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
		-->
	<script type="text/javascript">
		$(document).ready(function(){  
			$('#card-data').hide();
            	$("#submit-btn").click(function(){
                	var test = $("#input-meme").val();
               		$.ajax({  
						type: "GET", 
						url: 'https://api.imgflip.com/get_memes',  
						success: function(result) {
						console.log(result);
                    	$('#card-data').show();
						let memeName=result.data.memes[test].name;
						let imgSrc=result.data.memes[test].url;
						console.log(memeName);
						$("#name-h3").text(memeName);
						$("#img-meme").attr('src',imgSrc);

				},  
				error: function(XMLHttpRequest, errorMsg, errorThrown) {
					alert(errorMsg);
				}  
			})
		})
	})
		</script>
		

</body>
</html>
