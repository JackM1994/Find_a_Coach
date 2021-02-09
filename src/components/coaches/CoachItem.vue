<template>
	<li>
		<h3>{{ fullName }}</h3>
		<h4>${{ rate }}/hour</h4>
		<div>
			<span v-for="area in areas" :key="area">{{ area }}</span>
		</div>
		<div class="actions">
			<router-link :to="coachContactLink">Contact</router-link>
			<router-link :to="coachDetailsLink">View Details</router-link>
		</div>
	</li>
</template>

<script>
	export default {
		props: ['id', 'firstName', 'lastName', 'rate', 'areas'],
		computed: {
			fullName(){
				return this.$route.path + this.firstName + ' ' + this.lastName;
			},
			coachContactLink(){
				return this.$route.path + '/coaches/' + this.id + '/contact'
			},
			coachDetailsLink(){
				return this.$route.path + '/coaches/' + this.id;
			}
		}
	}
</script>

<style scoped>
	@import './coach-item.css'
</style>