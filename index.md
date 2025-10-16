<script type="text/javascript">
	function initEmbeddedMessaging() {
		try {
			// Set the language
			embeddedservice_bootstrap.settings.language = 'en_US'; 

			// Wait for the messaging framework to finish initializing
			window.addEventListener("onEmbeddedMessagingReady", () => {
				console.log("Received the onEmbeddedMessagingReady event…");

				// Set the hidden pre-chat field for Card Token
				embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
					"Card_Token": "12345" // Replace with your actual token value or dynamic variable
				});
			});

			// Initialize the Embedded Messaging deployment
			embeddedservice_bootstrap.init(
				'00DVE000006fyo0', // Salesforce Org ID
				'Amazon_Messaging', // Embedded Service Deployment Name
				'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879', // Deployment URL
				{
					scrt2URL: 'https://fleetcorna--svcsprint.sandbox.my.salesforce-scrt.com' // SCRT URL
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>

</script>
<script type='text/javascript' src='https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
