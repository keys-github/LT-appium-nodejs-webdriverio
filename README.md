# WebDriverIO With Appium — TestMu AI (Formerly LambdaTest)

<p align="center">
<img height="500" src="https://user-images.githubusercontent.com/95698164/171858859-b08009f7-101e-43a9-8e4e-293bd690ccd5.png">
</p>

<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

_WebdriverIO is a framework for automating web and mobile applications. It makes it easier to interact with your app, and provides a set of plugins that help you create a scalable, robust and stable test suite. Perform [WebDriverIO tests on TestMu AI's online cloud.](https://www.testmuai.com/appium-mobile-testing/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio)._

_Learn the basics of [Appium testing on the TestMu AI platform](https://www.testmuai.com/support/docs/getting-started-with-appium-testing/)._

[<img height="53" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)

## Table of Contents

- [Pre-requisites](#pre-requisites)
- [Run Your First Test](#run-your-first-test)
- [Executing The Tests](#executing-the-tests)

## Pre-requisites

Before you can start performing App automation testing with Appium, you would need to follow these steps:

- Download and install **NodeJS**. You should be having **NodeJS v6** or newer. Click [here](https://nodejs.org/en/) to download.
- Make sure you are using the latest version of **JavaScript**.
- Install **npm** from the official website by clicking [here](https://www.npmjs.com/).

### Clone The Sample Project

Clone the TestMu AI’s :link: [LT-appium-nodejs-webdriverio](https://github.com/LambdaTest/LT-appium-nodejs-webdriverio) repository and navigate to the code directory as shown below:

```bash
git clone https://github.com/LambdaTest/LT-appium-nodejs-webdriverio
cd LT-appium-nodejs-webdriverio
```

### Setting Up Your Authentication

Make sure you have your TestMu AI credentials with you to run test automation scripts on LambdaTest. To obtain your access credentials, [purchase a plan](https://billing.lambdatest.com/billing/plans/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio) or access the [Automation Dashboard](https://appautomation.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio).

Set TestMu AI `Username` and `Access Key` in environment variables.

**For Linux/macOS:**

```js
export LT_USERNAME=YOUR_LAMBDATEST_USERNAME \
export LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```

**For Windows:**

```js
set LT_USERNAME=YOUR_LAMBDATEST_USERNAME `
set LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```

### Upload Your Application

Upload your **_iOS_** application (.ipa file) or **_android_** application (.apk file) to the TestMu AI servers using our **REST API**. You need to provide your **Username** and **AccessKey** in the format `Username:AccessKey` in the **cURL** command for authentication. Make sure to add the path of the **appFile** in the cURL request. Here is an example cURL request to upload your app using our REST API:

**Using App File:**

**For Linux/macOS:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'appFile=@"/Users/macuser/Downloads/proverbial_android.apk"'
```

**For Windows:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -F "appFile=@"/Users/macuser/Downloads/proverbial_android.apk""
```

**Using App URL:**

**For Linux/macOS:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'url="https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk"'
```

**For Windows:**

```js
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -d "{"url":"https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk","name":"sample.apk"}"
```

**Tip:**

- If you do not have any **.apk** or **.ipa** file, you can run your sample tests on TestMu AI by using our sample :link: [Android app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk) or sample :link: [iOS app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_ios.ipa).
- Response of above cURL will be a **JSON** object containing the `App URL` of the format - <lt://APP123456789123456789> and will be used in the next step.

## Run Your First Test

Once you are done with the above-mentioned steps, you can initiate your first WebDriverIO test on LambdaTest.

**Test Scenario:** Check out [Android-test.js](https://github.com/LambdaTest/LT-appium-nodejs-webdriverio/blob/master/specs/android-test.js) file to view the sample test script for android and [iOS-test.js](https://github.com/LambdaTest/LT-appium-nodejs-webdriverio/blob/master/specs/ios-test.js) for iOS.

### Configuring Your Test Capabilities

You need to update your capabilities in `*.config.js` files. In this sample project, we have provided the examples for running tests on both **Android** and **iOS** apps. You can find the configs for both iOS and Android in the `iOS-sample` and `android-sample` directories correspondingly. We are passing platform name, platform version, device name and app url (generated earlier) along with other capabilities like build name and test name via capabilities object. You need to pass the path of your test script in `specs` object to run your own automation script. The capabilities object in the sample code for a single test are defined as:

<Tabs className="docs__val">

<TabItem value="ios-config" label="ios-single.conf.js" default>

```javascript title="ios/ios-single.conf.js"
exports.config = {
  user: process.env.LT_USERNAME || "YOUR_USERNAME",
  key: process.env.LT_ACCESS_KEY || "YOUR_ACCESS_KEY",

  updateJob: false,
  //highlight-next-line
  specs: ["specs/ios-test.js"], //path of your test script
  exclude: [],

  //highlight-start
  capabilities: [
    {
      build: "NodeJS WebDriverIO iOS",
      name: "Sample Test - WebDriverIO",
      isRealMobile: true,
      deviceName: "iPhone 13 Pro",
      platformVersion: "15",
      platformName: "iOS",
      app: "YOUR_APP_URL",
    },
  ],
  //highlight-end

  logLevel: "info",
  coloredLogs: true,
  screenshotPath: "./errorShots/",
  baseUrl: "",
  waitforTimeout: 10000,
  connectionRetryTimeout: 90000,
  connectionRetryCount: 3,
  path: "/wd/hub",
  hostname: "mobile-hub.lambdatest.com",
  port: 80,

  framework: "mocha",
  mochaOpts: {
    ui: "bdd",
    timeout: 20000,
  },
};
```

</TabItem>
<TabItem value="android-config" label="android-single.conf.js" default>

```javascript title="android/android-single.conf.js"
exports.config = {
  user: process.env.LT_USERNAME || "YOUR_USERNAME",
  key: process.env.LT_ACCESS_KEY || "YOUR_ACCESS_KEY",

  updateJob: false,
  //highlight-next-line
  specs: ["specs/android-test.js"], //path of your test script
  exclude: [],

  //highlight-start
  capabilities: [
    {
      build: "NodeJS WebDriverIO Android",
      name: "Sample Test - WebDriverIO",
      isRealMobile: true,
      platformName: "Android",
      deviceName: "Galaxy S9",
      platformVersion: "10",
      app: "YOUR_APP_URL",
    },
  ],
  //highlight-end

  logLevel: "info",
  coloredLogs: true,
  screenshotPath: "./errorShots/",
  baseUrl: "",
  waitforTimeout: 10000,
  connectionRetryTimeout: 90000,
  connectionRetryCount: 3,
  path: "/wd/hub",
  hostname: "mobile-hub.lambdatest.com",
  port: 80,

  framework: "mocha",
  mochaOpts: {
    ui: "bdd",
    timeout: 20000,
  },
};
```

</TabItem>

</Tabs>

**Info Note:**

- You must add the generated **APP_URL** to the `"app"` capability in the config file.
- You can generate capabilities for your test requirements with the help of our inbuilt :link: **[Capabilities Generator tool](https://www.testmuai.com/capabilities-generator/)**. A more Detailed Capability Guide is available [here :page_facing_up:](https://www.testmuai.com/support/docs/desired-capabilities-in-appium/) .

## Executing The Tests
**Step-5:** To Run Android Test 

```bash
cd android-sample
```

**Step-6:** Install the required dependencies using the following command:

```bash
npm i
```

**Step-7:** Execute the following command to run your test on TestMu AI platform:

**Single:**

- *MacOS/Linux*/Windows* 

```bash
npm run SingleAndroidApp
```

**Parallel:**

- *MacOS/Linux*/Windows* 

```bash
npm run parallel
```


**Info:** Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on the :link: [TestMu AI App Automation Dashboard](https://appautomation.lambdatest.com/build/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio).

## Additional Links

- [Advanced Configuration for Capabilities](https://www.testmuai.com/support/docs/desired-capabilities-in-appium/)
- [How to test locally hosted apps](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/)
- [How to integrate TestMu AI with CI/CD](https://www.testmuai.com/support/docs/integrations-with-ci-cd-tools/)

## Documentation & Resources :books:

Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

- [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio)
- [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio)
- [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio)

## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-nodejs-webdriverio) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

**🔄 Our Rebrand Journey**

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

**🔭 Explore TestMu AI**

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)