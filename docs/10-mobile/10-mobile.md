## Lab 10: Mobile App (Phonegap)

1. In this Lab we will customize and install an Android app that uses the Cordova In-App Browser to provide a rich UI. Download and unzip topseed-mobile-master.zip from <a href='https://github.com/topseed/topseed-mobile' target='_blank'>here</a> to your location of choice on your developer machine. Open the project in VS Code. Download and install the Phonegap Desktop App from <a href='https://github.com/phonegap/phonegap-app-desktop/releases' target='_blank'>here</a>. Run the app, add the '/topseed-mobile' folder as a Project, and click the '>' button. A message 'Server is running on ...' should come up. Click on the URL to open the App in a browser. Resize the browser to mobile phone format. In Google Chrome, your can also hit 'Ctrl-Shift+i' to open the developer console to get approximate mobile phone dimensions (Phonegap Desktop App adds a grey margin). 

2. The app is configured to show a splash screen and then display content obtained from https://m.appthings.io. To customize, we will make it display the content you published to the CDN in Lab 3 instead. As you edit the project, the Phonegap Desktop App watches for changes in the /www folder of the project and attempts to refresh the browser view on each change. In /www/js/index.js, replace the URL following 'window.open' with the homepage URL of the helloworld app you deployed in Lab 3, i.e. your equivalent of 'https://staging.mydomain.com/page/one/index.html'. If you only deployed to the CDN, use your equivalent of 'https://1234567890.rsc.cdn77.org/page/one/index.html'. If you only deployed to Zeit.co, use your equivalent of  'https://demos-oosnsyzlphl.now.sh/page/one/index.html'. If you never deployed, you can use the published version of this tutorial at 'https://docs.topseed.io/tutorial/0-agenda/index.html'. To ensure we deliver the turbo (non-AMP) version of the page, we include /index.html in the path.

3. To allow the in-app browser to navigate to the newly configured URL, in /config.xml  \<allow-navigation href="https://m.appthings.io/*" /\>, replace 'm.appthings.io' with your equivalent from the previous step. The app should now display your site at the 
Phonegap Desktop App Server URL. It is a labor of love to replace the splash screen logo (at /www/css/index.css) and the icons used by the phone operating system (see /config.xml 'icon' values) with your own; we will skip over it here. Optional: change the values for the app 'name' and 'version' in /config.xml.

4. To install the customized app on an Android phone, create an account and login at <a href='https://build.phonegap.com' target='_blank'>https://build.phonegap.com</a>. You will be prompted to create an Adobe ID if you don't have one. 
Create a zip file of the contents of the project folder /topseed-mobile. On the <a href='https://build.phonegap.com/apps' target='_blank'>'Apps' tab </a>, click the '+ new app' button and upload the zip file (If your project is in Github, you can use the github clone URL instead). The site will take a few moments to build the app. Meanwhile, also log into <a href='https://build.phonegap.com' target='_blank'>https://build.phonegap.com</a> on your mobile phone. Once the build has completed, follow the prompts to download, install and run the version for your phone's operating system (here: Android). Done! For fun, close the app and reopen it by tapping on the app icon on your phone UI.

5. See <a href='http://docs.phonegap.com/' target='_blank'>http://docs.phonegap.com/</a> for further information about phonegap, for instruction how to deploy to Apple iOS,and how your app can access phone-specific APIs, such as address book, location information etc if necessary. We would use a 'service worker' to support offline-browsing as needed.

6. In this Lab, we have used the Cordova In-App Browser to render app content from a CDN. As shown in Lab 6, the app can also obtain data securely from separate API servers. Thanks to Appshell, Turbo and Caching introduced in Lab 4, the app has a smooth 'single page application' feel. As a result, we were able to develop a rich mobile app without requiring special Android SDK/iOS development skills. 


