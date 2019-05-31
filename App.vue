<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  box-sizing: border-box;
} 
.wt100{
  width: 100%;
}
.flexct{
  display: flex;
  flex-direction:column;
  justify-content: center;
  align-items: center;
}
.flexctrow{
  display: flex;
  flex-direction:row;
  justify-content: center;
  align-items: center;
}
.flexrow{
  display: flex;
  flex-direction:row;
  align-items: center;
  justify-content: flex-start;
}
.flexlb{
  display: flex;
  flex-direction:row;
  align-items: center;
  justify-content:space-between;
}
</style>
