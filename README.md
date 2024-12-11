# Convert a Website to a Mobile Application

This guide provides the steps to convert any website into a mobile app using **Apache Cordova** and **JavaScript**. With this guide, you can create a mobile application from a website using Visual Studio Code (VS Code) without needing Android Studio. This tutorial is beginner-friendly and covers all necessary steps from installation to building the mobile app.

---

## **Prerequisites**

Before you begin, ensure that you have the following installed on your machine:

- **Node.js and npm** (Package Manager for Node.js)
- **Java JDK** (Java Development Kit, Version 17 or higher)
- **Android SDK** (Software Development Kit)
- **Cordova CLI** (Command Line Interface for Cordova)

### **Step 1: Install Required Software**

#### **1.1 Install Node.js and npm**
Node.js is required to run Cordova. You can download and install it from the official website.

- Download Node.js from [here](https://nodejs.org/).
- Verify the installation:
  ```bash
  node -v
  npm -v
  ```

#### **1.2 Install Java JDK**
Java is required to build Android applications. Follow these steps to install Java 17:

- Download Java 17 from [Oracle JDK 17](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html).
- Install Java and verify the installation:
  ```bash
  java -version
  ```

#### **1.3 Install Android SDK**
You need Android SDK tools for building Android apps.

- Install Android Studio to get the Android SDK (even though we won’t use Android Studio for building the app).
- You can download Android Studio from [here](https://developer.android.com/studio).
- During the installation, make sure to install Android SDK and Android Build Tools.

#### **1.4 Install Cordova CLI**
Cordova is a command-line tool that helps in building mobile applications from web technologies.

- Install Cordova globally via npm:
  ```bash
  npm install -g cordova
  ```
- Verify the installation:
  ```bash
  cordova -v
  ```

---

## **Step 2: Create a New Cordova Project**

Now, let’s create a new Cordova project where we will load the website inside a WebView.

- Open a terminal (Command Prompt or PowerShell on Windows).
- Navigate to the folder where you want to create the project and run the following command:
  ```bash
  cordova create myMobileApp com.example.mymobileapp MyMobileApp
  ```

- Navigate to the project directory:
  ```bash
  cd myMobileApp
  ```

- Add the Android platform to the project:
  ```bash
  cordova platform add android
  ```

---

## **Step 3: Modify WebView to Load Your Website**

1. Open the `www` folder inside your Cordova project.
2. Open the `index.html` file, which is the main entry point for the app.
3. Replace its contents with the following HTML code to load your website inside a WebView:

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Mobile App</title>
</head>
<body>
  <iframe src="https://yourwebsite.com" style="width:100%; height:100vh; border:none;"></iframe>
</body>
</html>
```

Replace `"https://yourwebsite.com"` with the URL of the website you want to convert into a mobile app.

---

## **Step 4: Configure Environment Variables (For Windows Users)**

If you're using Windows, ensure that the `JAVA_HOME` and `ANDROID_HOME` environment variables are set correctly.

### **4.1 Set JAVA_HOME**

- Go to **Control Panel > System and Security > System > Advanced system settings**.
- Under **System Properties**, click on **Environment Variables**.
- Add a new system variable:
  - Name: `JAVA_HOME`
  - Value: The path to your Java installation. Example: `C:\Program Files\Java\jdk-17`.

### **4.2 Set ANDROID_HOME**

- Add another system variable:
  - Name: `ANDROID_HOME`
  - Value: The path to your Android SDK. Example: `C:\Users\YourUsername\AppData\Local\Android\Sdk`.

---

## **Step 5: Build the App**

Now that everything is set up, it’s time to build your Android app.

1. Open a terminal in the project directory (`myMobileApp`).
2. Run the following command to build the app:
  ```bash
  cordova build android
  ```

- Cordova will generate an APK file that you can install on your Android phone.
- The generated APK file can be found in:
  ```
  myMobileApp/platforms/android/app/build/outputs/apk/debug/app-debug.apk
  ```

---

## **Step 6: Test the Mobile App**

1. Connect your Android device via USB or use an Android emulator.
2. Install the APK manually by transferring the file to your phone or using ADB commands:
   ```bash
   adb install path_to_your_apk_file
   ```

3. Once installed, open the app on your phone. The website you integrated should be displayed inside the app as a WebView.

---

## **Troubleshooting**

If you encounter issues, here are a few common fixes:

- **JAVA_HOME or ANDROID_HOME not set**: Ensure you have set the environment variables correctly as explained in Step 4.
- **Build errors**: Make sure your Java version is compatible with the Android Gradle plugin. For newer versions of the Android Gradle plugin, Java 17 is required.
- **Cordova issues**: If you face issues related to Cordova versions, try upgrading Cordova:
  ```bash
  npm install -g cordova@latest
  ```

---

## **Conclusion**

By following these steps, you have successfully converted a website into a mobile app using Cordova. You can now deploy your app to the Google Play Store or distribute it directly. This guide provides a simple and effective way to turn your website into a functional Android app without using Android Studio.

If you have any questions or run into issues, feel free to open an issue or reach out for support.

---

### **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### **Contributors**

- [Shah Ram](https://github.com/shahram8708)

---

### **Links**
- [Apache Cordova Official Docs](https://cordova.apache.org/docs/en/latest/)
- [Node.js Official Website](https://nodejs.org/)
- [Java JDK Downloads](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html)
- [Android SDK Setup](https://developer.android.com/studio)

---

### **Final Notes**

- The steps in this README are intended to help developers quickly convert their websites into Android mobile apps.
- It is important to test the app thoroughly and optimize it for mobile devices.
