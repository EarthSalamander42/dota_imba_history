<template>
	<div class="war_of_the_gods">
		<div class="custard-header-top pt60 pb50">
			<div class="container text-center ranking-head">
				<h1>Dota IMBA History</h1> <!-- Title -->
				<div class="sub">LIST OF IMBA ABILITIES AND ITEMS IMPLEMENTED IN DOTA 2</div> <!-- Secondary Title -->
			</div>
		</div>

		<div class="global">
			<div class="dark_background">

				<div class="general pt80 pb80" style="margin-bottom: -100px;">
					<div class="container">
						<h2>General</h2>
						<div class="row">
							<div class="col-md-8">
								<ul class="notes">
									<li></li> <!-- Text line sample. Write anything between <li> and </li>. Commented examples below -->
<!--
									<li>Additional gold multiplier up to 2x at 200k networth differential (linear scaling)</li>
									<li>Additional experience multiplier up to 2x at 100 level differential (linear scaling)</li>
-->
								</ul>
							</div>
<!--
							<div class="col-md-4">
								<img src="https://cdn.frostrose-studio.com/static/images/events/7_12/base_keeper.png" width="260" alt="creep">
							</div>
-->
						</div>
					</div>
				</div>

				<!-- Don't touch anything in there, content added at the bottom of the file -->
				<div class="heroes pt80 pb80">
					<div class="container">
						<h2>Heroes</h2>

						<Hero v-for="hero in heroes" :image="hero.image" :name="hero.name" :key="hero.name" :abilities="hero.abilities" class="hero_row" />

						<h2>Items</h2>
	
						<Item v-for="item in items" :image="item.image" :name="item.name" :key="item.name" :items="item.items"/>
					</div>
				</div>
				<!-- End of don't touch anything in there -->

				<!-- Add yourself below if contributing to the list, alphabetical order -->
				<div class="credits pt80 pb80">
					<div class="container">
						<h2 class="mb30">Credits</h2>
						<ul class="notes">
							<li>Anyone contributing to this page</li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import Hero from "./Patches/Hero";
	import Item from "./Patches/Item";

		export default {
		name: "WarOfTheGods",
		components: { Item, Hero },
		data() {
			var self = this;

			return {
				heroes: [
					/* Below is an example of how code sample should be, just copy-paste and replace required values to add a new hero. */
					{
						name: "Sven",
						image: self.cdn_hero("sven"),
						abilities: [
							{
								name: "Storm Hammer",
								image: self.cdn_ability("sven_storm_bolt"),
								items: [
									"Description: Sven launches HIMSELF towards the enemy, damaging and stunning nearby units.",
									"IMBA release Date: TBD",
									"Note: This effect was added as part of Aghanim Scepter's upgrade in 7.23.",
									"Dota 2 release Date: TBD",
								]
							},
/*
							{
								name: "Rolling Boulder",
								image: self.cdn_ability("earth_spirit_rolling_boulder"),
								items: [
									"Target is no longer slowed on stone hit, stunned instead. (using vanilla values)",
								]
							},
							{
								name: "Stone Remnant",
								image: self.cdn_ability("earth_spirit_stone_caller"),
								items: [
									"Earth's Mark: Added 10 max stacks limit on a single unit.",
								]
							},
							{
								name: "Magnetize",
								image: self.cdn_ability("earth_spirit_magnetize"),
								items: [
									"Earth's Wrath: Bonus damage reduced from 50 to 25.",
								]
							},
*/
						]
					},
				],

				/* Below is an example of how code sample should be, just copy-paste and replace required values to add a new item. */
				items: [
					{
						name: "Sogat Cuirass",
						image: self.cdn_item("item_sogat_cuirass"),
						items: [
							"Initially called Heracle's Armor and later on Greatwyrm Plate, this item has been renamed in memory of Sogat, original creator of X Hero Siege in Warcraft 3.",
						]
					},
				],
			};
		},

		methods: {
			cdn_hero(name) {
				return "https://cdn.frostrose-studio.com/static/images/heroes/" + name + ".png";
			},
			cdn_ability(ability) {
				return "https://cdn.frostrose-studio.com/static/images/abilities/" + ability + ".png";
			},
			cdn_item(item) {
				return "https://cdn.frostrose-studio.com/static/images/items/" + item + ".png";
			}
		}
	};
</script>

<style scoped>

</style>
