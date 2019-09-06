<template>
	<section class="recipes">
		<recipe
			v-for="(recipe, ix) in recipes"
			:key="ix"
			:id="recipe.id"
			:thumbnail="recipe.imageLink"
			:title="recipe.title"
			:previewText="recipe.description"
		/>
	</section>
</template>

<script>
import Recipe from './../../components/Recipe'
export default {
	components: {
		Recipe
	},
	data: () => ({
		recipes: [
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
		]
	})
}
</script>

<style scoped>
.recipes {
	display: flex;
	flex-flow: row wrap;
	justify-content: center;
	align-items: center;
}
</style>
