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
									<li>Turbo mode was made heavily based on Dota IMBA:</li>
									<li>Gold and experience multiplier from all sources</li>
									<li>Faster drafting</li>
									<li>Ancients do not regenerate health</li>
									<li>Lane creeps are upgraded at a much faster rate than normal</li>
									<li>Very fast couriers</li>
									<li>Reduced Roshan respawn timer</li>
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
							<!-- <li>todo: give credits to Lemoncake, the guy who initially made Dota 2 Gamepedia because many informations are found out there</li> -->
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
						name: "Crystal Maiden",
						image: self.cdn_hero("crystal_maiden"),
						abilities: [
							{
								name: "Freezing Field (Scepter)",
								image: self.cdn_ability("crystal_maiden_freezing_field"),
								items: [
									"IMBA Ability description: Heart of the Glacier: Also briefly inflicts frostbite to enemies in the area.",
									"IMBA release date: TBD",
									"Vanilla scepter description: Applies Frostbite to any unit that has been standing in the Freezing Field for over 1.75s.",
									"Dota 2 release date: 26/11/2019",
									"Concept credits: TBD",
									"Code credits: TBD",
									"Note: This scepter upgrade was added in 7.23.",
								]
							},
						]
					},
					{
						name: "Ember Spirit",
						image: self.cdn_hero("ember_spirit"),
						abilities: [
							{
								name: "Fire Remnant (Shard)",
								image: self.cdn_ability("ember_spirit_fire_remnant"),
								items: [
									"IMBA ability description: Shared Flame: Remnants also benefit from Flame Guard, dealing half the normal damage.",
									"IMBA release date: 22/03/2018",
									"Vanilla shard description: Fire Remnants deal damage per second in an area around them. If an enemy hero dies near Ember Spirit, a Fire Remnant charge will be replenished.",
									"Dota 2 release date: 17/12/2020",
									"Concept credits: Firetoad",
									"Code credits: Firetoad",
									"Note: This shard upgrade was added in 7.28.",
								]
							},
						]
					},
					{
						name: "Kunkka",
						image: self.cdn_hero("kunkka"),
						abilities: [
							{
								name: "Ghostship (Scepter)",
								image: self.cdn_ability("kunkka_ghostship"),
								items: [
									"IMBA ability description: ON A BOAT: The ship drags enemies along its path.",
									"IMBA release Date: TBD",
									"Vanilla shard description: ",
									"Dota 2 release date: TBD",
									"Concept credits: TBD",
									"Code credits: TBD",
									"Note: This scepter upgrade was added in 6.86, and then removed in 7.23.",
								]
							},
						]
					},
					{
						name: "Omniknight",
						image: self.cdn_hero("omniknight"),
						abilities: [
							{
								name: "Hammer of Purity (IMBA name: Hammer of Virtue)",
								image: self.cdn_ability("sven_storm_bolt"),
								items: [
									"IMBA ability description: Imbues the hammer with holy power, converting your next attack to pure damage. The pure energy bounces off the enemy and scatters, healing yourself and all nearby allied heroes for a percentage of the attack damage. Goes into a cooldown after landing a successful attack.",
									"IMBA release Date: 04/04/2017",
									"Vanilla ability description: Causes Omniknight's next attack to deal bonus pure damage based on his attack damage value, and temporarily reduce the target's outgoing damage.",
									"Dota 2 release Date: 23/02/2022",
									"Concept credits: Firetoad",
									"Code credits: Shush",
									"Note: This ability was added in 7.31.",
								]
							},
						]
					},
					{
						name: "Sven",
						image: self.cdn_hero("sven"),
						abilities: [
							{
								name: "Storm Hammer (Scepter)",
								image: self.cdn_ability("sven_storm_bolt"),
								items: [
									"IMBA description: Sven launches HIMSELF towards the enemy, damaging and stunning nearby units.",
									"IMBA release Date: 04/08/2015",
									"Vanilla description: Storm Hammer gains +500 cast range and you travel along it. Upon impact, it hits automatically lands an attack on the primary target.",
									"Dota 2 release Date: 26/11/2019",
									"Concept credits: Firetoad",
									"Code credits: Firetoad",
									"Note: This scepter upgrade was added in 7.23.",
								]
							},
						]
					},
				],

				/* Below is an example of how code sample should be, just copy-paste and replace required values to add a new item. */
				items: [
					{
						name: "Sogat Cuirass",
						image: self.cdn_item("item_sogat_cuirass"),
						items: [
							"Initially called Heracle's Armor, Greatwyrm Plate and later on Calaminh's Tutela Plate, this item has been renamed in memory of Sogat, original creator of X Hero Siege in Warcraft 3.",
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
