
# MRTK 101: Utilizing MRTK for Quest 2 Development [ Part — 1 ]

![](https://miro.medium.com/max/700/1*Nd8MO8jgCGUV3z6pXElQRw.png)

MRTK is a widely-used development toolkit that offers a range of features and capabilities to developers creating immersive experiences for a variety of platforms, primarily for Hololens. It can be used to develop native code applications, but it is particularly well-suited for use with Unity. MRTK offers a range of features to developers, including hardware bindings, utilities, and visual elements with a well-architected API. It’s a little-known fact that MRTK can also be utilized for creating applications for Meta Quest 2. With MRTK, you can create immersive experiences that are not only compatible with Quest 2, but also with the shiny-but-pricey Hololens 2! So even if you don’t have a Hololens of your own, this pipeline allows you to create cutting-edge AR experiences. In spite of all its advantages, the documentation on this topic is very limited. So, I decided to create this guide for simplifying this process. Put on your glasses, we are diving into MRTK!

![](https://miro.medium.com/max/621/1*rpGI-4PzFT7lR1A98JdWCQ.gif)

# Prerequisites

-   Mixed Reality Feature Tool (Download from  [here](https://www.microsoft.com/en-us/download/details.aspx?id=102778))
-   Unity 2020.3.6 and above ( With Android Build Module)
-   Quest, Quest 2, or Rift S Headset ( Recommended ).
-   If a headset is used, its development mode must be activated.

Before diving in, here are a few things to keep in mind.

1.  The methods and techniques outlined in this article have been tested and found to work with Quest1, Rift S (and potentially a few other VR headsets which I have no chance to test)
2.  You can also find the example project on my GitHub

With that said, let’s get started!

# 1 — Ready, Set, MRTK!

To begin, we will create an empty Unity project named “MRTK_VRTemplate” using the 3D SRP template. For the purpose of this tutorial, I will be using Unity version 2021.3.5f1. It’s recommended that you use the same version to ensure compatibility and avoid any potential issues.

![](https://miro.medium.com/max/700/1*duVehQDyTecpci3YWbtlQw.png)

After the project has been created and the engine has initialized, the project will open. At this point, I like to set up a folder structure that keeps everything specific to this project organized. To do this, I create a root folder under the “Assets” folder and name it after the project. This helps me to separate any additional modules or assets that are specific to this project from my native assets. The resulting folder structure under the “Assets” folder should look like this:

![](https://miro.medium.com/max/212/1*jwrGcHsjC7sIMfMkFWU88g.png)

To get started with MRTK, we will be using the Mixed Reality Feature Tool, which will help us to easily populate our application with MRTK assets and take advantage of all the features and capabilities that MRTK has to offer.

1.  Simply click on the “Start” button. The tool will then prompt you to locate your Unity project, which you can do by navigating to the directory where your “Assets” folder is located. The Feature Tool will analyze this path and automatically detect the current editor version.
2.  Click On “Discover Features”.

![](https://miro.medium.com/max/700/1*YJguoSUr7NrCsxTeps2OjQ.png)

3. Simply select the desired features as shown in the images below. Alternatively, you can customize your feature selection by adding any additional features that you may need for your application. This flexibility allows you to tailor your MRTK feature set to the specific needs of your project.

![](https://miro.medium.com/max/700/1*yOsLm6tHay6pI7qWi0TTRA.png)

![](https://miro.medium.com/max/700/1*ks-FOkzMLkcRXBUCFUz9RQ.png)

_! It’s important to ensure that the version of the Mixed Reality Toolkit features is set to 2.7.3 to ensure compatibility and avoid any potential issues._

4. Click on a flurry of approval buttons! Just three of them. Then sit back and let Feature Tool do the rest.

Upon opening the Unity Editor, you will notice that new assets are being loaded. Once this process is complete and all assets have been loaded, you can proceed to the next step.

5. You may see a prompt from Unity asking you to restart the editor, but you can ignore this for now. After a moment, the MRTK Project Configurator should open. When it does, you’ll be asked to select a preferred backend. For the purposes of this tutorial, you should select OpenXR, as everything we’ll be doing is based on OpenXR.

![](https://miro.medium.com/max/700/1*IZrPl_CBgr2nrPZOjTn8jg.png)

Again, gears turn, belts creak and the engine grumbles…

6. For now, we will skip the next step and come back to it later..

![](https://miro.medium.com/max/700/1*YN0taTo8toRooBwf4LA3Cw.png)

7. In the next step, be sure to click on the “Apply” button.

![](https://miro.medium.com/max/700/1*y94i8RKiOyQM54umE-Gb7Q.png)

8. Make sure to click on the “Import TMP Essentials” button to, you guessed it, import TMP essentials into your project.

9. Make sure to click on the “Got it, next!” and “Done” buttons in the next steps.

Well, we’re not quite done yet. In fact, we’re just getting started! Next up, we’ll be opening an example MRTK scene to see how everything works. But first, we need to load the example scenes. To do this, go to  **Window > Package Manager**  in the top menu. From there, you’ll be able to access the MRTK example scenes**.**

![](https://miro.medium.com/max/700/1*hojQ56DnQ5yGQKCCoofUig.png)

You are Supposed to see “Packages: In Project” on the top. If not, select this option and you will see the MRTK Packages are listed in the “Microsoft” scope. Click on “Mixed Reality Toolkit Examples”.

![](https://miro.medium.com/max/700/1*OqPp_R0Fy1SWxcX06SwmBg.png)

In the right menu, click on “Samples” and it will open the list of available examples. Click on “Import” which is sitting beside “Demos-HandTracking”.

10. When you get back to the editor, you will see that there is a “Samples” folder added to Hierarchy. Locate the “Scenes” folder and open the scene “HandInteractionExamples.scene”.

![](https://miro.medium.com/max/438/1*2RMQl02vCU-hcHbdu8SbBg.png)

When we hit the play button, we can interact with the elements in the simulation using our simulated hands. By pressing the “Space” key, we can activate the right hand, and by pressing the “Left-Shift” key, we can activate the left hand. To rotate the hands, we can simply hold down the “Ctrl” key and use the mouse. While it may take a bit of practice to get the hang of it, the benefits of this system for speeding up our development pipeline make it well worth the effort.

![](https://miro.medium.com/max/293/1*gmw3H-Z4TZjPp28AhyhnlA.gif)

Next, we will load the “Oculus Integration” asset from the  [asset store](https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022). After adding this to your assets, you have to go to  **Window > Package Manager**  again. This time “Packages: My Assets” must be selected.

![](https://miro.medium.com/max/419/1*69xXAuqBgpImsXTD9PRm0w.png)

Find “Oculus Integration” from the list. Select it, and click on “download” which is located at the right-bottom of the window. After it is downloaded, simply click on “import”. Again, gears turn, etc…

Then, you should make sure that the following option is set in the top bar.

![](https://miro.medium.com/max/700/1*lGPvN1UB2eGVgYYfbLK4tQ.png)

Also, integrate Oculus Integration Modules to MRTK.

![](https://miro.medium.com/max/700/1*jwQM6edgmDkVwi6aERo-BA.png)

# Configuration

1.  Go to **Edit > Project Settings**. From the “Player” submenu, find the “Active Input Handling” setting and set it to “both”. This may force you to restart the editor.
2.  Also, you should set the following options in the “Player” menu. Make sure “Android” is selected.

![](https://miro.medium.com/max/700/1*kgPLXr7ISJLilCKez0B7IA.png)

3. Options to be changed are shown below.

![](https://miro.medium.com/max/700/1*Ib4xRZjktfPQY6YbheAtvA.png)

4. Then, go to “XR Plugin Management”. Set everything as the images. I will explain each setting one by one.

Setting — 1 :

![](https://miro.medium.com/max/700/1*SpyHoqp4-9y0qAumAs-dnA.png)

5. This set includes the required configuration to be used in both Windows Builds and Editor. Make sure everything just looks the same. If you want this application to run on your headset when you hit to the play button, this configuration is required. Not enough though.

Setting — 2:

![](https://miro.medium.com/max/700/1*NRzgCCeEpWcDkLMFyeJCZw.png)

6. This set includes the required configuration to be used when the application is loaded into the Headset. If you see an exclamation mark beside any setting, simply click on the mark. It will take you to a page as below.

![](https://miro.medium.com/max/700/1*xW-grPf5pgHvNbHGtshitA.png)

7. It may look different depending on your unique engine configuration but the point is the same. The “Fix” button will mostly fix the issue. If not, check it again when we finish the rest of the configuration. If it still persists, the warning message will guide you while you are fixing the issue.

![](https://miro.medium.com/max/700/1*lf_9Du-OW1JhhOGRQPgbdQ.png)

![](https://miro.medium.com/max/700/1*HzG6W-CSr3Pc5lTCYhTTHg.png)

**Render Mode**  determines how the scene will be rendered per eye. Single-pass takes a copy of the left eye and shows the same image in both eyes. This results in a 2d image but it is computationally lighter. Multi-pass renders the camera per eye which is full 3d and computationally heavy.

**Depth Submission Mode** is really hard to explain and also is out of this topic.

**Interaction Profiles** are where you will add the controller profile that you want your project to be compatible with. Use the “+” button to add controller profiles. The sample set will work.

**Play Mode OpenXR**  **Runtime**  determines the behavior of the engine when we hit the “Play” button. If you select  **Windows Mixed Reality**, the application will play in simulation mode. If you select  **Oculus Open XR**, the application will start on the device which is connected to your PC ( Oculus Link must be activated.). Well, after this long journey in the “configuration forest”, we are almost there.

# Final Touches

![](https://miro.medium.com/max/427/1*ypYRYWncUAAbd1Se6JJjWA.gif)

We have successfully completed all necessary configurations for our application to be fully functional on a Quest 2 device. By connecting the Quest 2 to a PC using Oculus Link, the application will be displayed on the headset with no issues. Although we are excited about this achievement, there are a few remaining issues that we will address in the next article. I will provide detailed instructions on how to enable hand tracking and guide you through the process of uploading your application to the headset, making it a standalone experience. Until then, happy coding!