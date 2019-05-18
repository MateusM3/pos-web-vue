<template>
	<div class="contact">
		<h1>{{title}}</h1>
		
		 <div class="contact">
		 	<form>
		 		<div class="form-group">
		 			<div class="input-group-prepend">
		 				
		 				<input type="text" class="form-control" name="">
		 			</div>
		 			<div class="input-group-prepend">
		 				
		 				<input type="text" class="form-control" name="">
		 			</div>
		 			<div class="input-group-prepend">
		 			
		 				<textarea class="form-control">
		 					
		 				</textarea>
		 			</div>
		 			<button class="btn btn-primary btn-block">Enviar</button>
		 		</div>
		 	</form>
		 </div>
	</div>
</template>
<script>
	export default{
		name:'cotact',
		data (){
			return{
				title:'Contato'
			}
		}
	}
</script>
