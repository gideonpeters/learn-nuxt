<template>
	<section class="single-recipe">
		<h1 class="text-4xl">{{recipe.title}}</h1>
		<div>
			<img class="recipe-image" :src="recipe.imageLink" />
		</div>
		<p>{{recipe.description}}</p>
	</section>
</template>

<script>
export default {
	data: () => ({}),
	asyncData(context) {
		return new Promise((resolve, reject) => {
			setTimeout(() => {
				resolve({
					recipe: [
						{
							id: 1,
							title: 'Some food',
							description: 'Some nice preview text',
							imageLink:
								'https://www.eatright.org/-/media/eatrightimages/food/nutrition/nutritionfactsandfoodlabels/sodium-salt-1083487948.jpg'
						},
						{
							id: 2,
							title: 'Some other food',
							description: 'Some nice preview text',
							imageLink:
								'https://img.taste.com.au/K02TrrZJ/w720-h480-cfill-q80/taste/2016/11/rachel-87711-2.jpeg'
						}
					].find((el) => {
						return el.id == context.params.id
					})
				})
			}, 1500)
		})
	}
}
</script>

<style scoped>
.single-recipe {
	display: flex;
	flex-flow: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	padding: 30px;
}

.recipe-image {
	width: 100%;
}
</style>