<script type="text/javascript">
(function() {
    // Initialize Embedded Messaging after bootstrap.js loads
    function initEmbeddedMessaging() {
        try {
            // Set language
            embeddedservice_bootstrap.settings.language = 'en_US';

            // Listen for when Embedded Messaging is ready
            window.addEventListener("onEmbeddedMessagingReady", function() {
                console.log("Embedded Messaging is ready");

                // Set hidden pre-chat fields
                embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
                    "Card_Token": "12345"
                });
            });

            // Initialize the Embedded Messaging widget
            embeddedservice_bootstrap.init(
                '00DVE000006fyo0', // Org Id
                'Amazon_Messaging', // Deployment name
                'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879', // Base URL
                {
                    scrt2URL: 'https://fleetcorna--svcsprint.sandbox.my.salesforce-scrt.com' // Optional
                }
            );
        } catch (err) {
            console.error('Error initializing Embedded Messaging:', err);
        }
    }

    // Dynamically load bootstrap.min.js
    var script = document.createElement('script');
    script.type = 'text/javascript';
    script.src = 'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879/assets/js/bootstrap.min.js';
    script.onload = initEmbeddedMessaging; // Run after script loads
    script.onerror = function() {
        console.error('Failed to load bootstrap.min.js');
    };

    // Append the script to the head to start loading
    document.head.appendChild(script);
})();
</script>
