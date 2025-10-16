<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			embeddedservice_bootstrap.init(
				'00DVE000006fyo0',
				'Amazon_Messaging',
				'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879',
				{
					scrt2URL: 'https://fleetcorna--svcsprint.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
