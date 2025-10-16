<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Embedded Messaging Test</title>
</head>
<body>
  <h1>Embedded Messaging Test Page</h1>

  <script type="text/javascript">
  (function() {
      // Initialize Embedded Messaging after bootstrap is fully loaded
      function initEmbeddedMessaging() {
          try {
              console.log("Initializing Embedded Messaging...");

              // Set language
              embeddedservice_bootstrap.settings.language = 'en_US';

              // Wait for the widget to be ready
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
                  'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879',
                  {
                      scrt2URL: 'https://fleetcorna--svcsprint.sandbox.my.salesforce-scrt.com'
                  }
              );
          } catch (err) {
              console.error("Error initializing Embedded Messaging:", err);
          }
      }

      // Dynamically load bootstrap.min.js from Salesforce
      var script = document.createElement('script');
      script.src = 'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879/assets/js/bootstrap.min.js';
      script.onload = initEmbeddedMessaging;
      script.onerror = function() {
          console.error("Failed to load bootstrap.min.js from Salesforce");
      };

      document.head.appendChild(script);
  })();
  </script>
</body>
</html>
