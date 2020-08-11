<script>
	export default {
		appData: {},
		onLaunch: function(options) {
			this.appData = options;
			console.log('App Launch')
		},
		onShow: function(options) {
			this.appData = options;
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
