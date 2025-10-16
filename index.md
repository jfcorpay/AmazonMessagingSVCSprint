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
      function initEmbeddedMessaging() {
          try {
              console.log("Initializing Embedded Messaging...");

              embeddedservice_bootstrap.settings.language = 'en_US';

              window.addEventListener("onEmbeddedMessagingReady", function() {
                  console.log("Embedded Messaging is ready");

                  embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
                      "Card_Token": "12345"
                  });
              });

              embeddedservice_bootstrap.init(
                  '00DVE000006fyo0',
                  'Amazon_Messaging',
                  'https://fleetcorna--svcsprint.sandbox.my.site.com/ESWAmazonMessaging1760040501879',
                  {
                      scrt2URL: 'https://fleetcorna--svcsprint.sandbox.my.salesforce-scrt.com'
                  }
              );
          } catch (err) {
              console.error("Error initializing Embedded Messaging:", err);
          }
      }

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
