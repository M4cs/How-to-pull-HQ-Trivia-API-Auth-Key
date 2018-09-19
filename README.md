# How to pull HQ Trivia API Auth Key
A short tutorial showing how to grab your HQ Trivia API Authentication Key for Use with HQ Trivia Bots or API Calls.

# Requirements:

- Charles Proxy
- An iOS or Android Device (We will be using iOS but the process is the same)
- A computer that can run Charles Proxy.

# Setting Up Computer:

#### Setting Up Proxy
First we need to open Charles Proxy. If you haven't already downloaded it go ahead and do that now. Navigate to Proxy > Proxy Settings like this.

![alt text](https://i.imgur.com/VlpkgBi.png)

From here you will need to setup your proxy settings. We need to change our port to something other than 8080. I chose 8000.

![alt text](https://i.imgur.com/8os0hyk.png)

After this we need to setup our SSL settings. To do this navigate to Proxy > SSL Proxying Settings. 

![alt text[(https://i.imgur.com/vedJ6th.png)

#### Setting Up Clients

From here we need to add a client. For HQ Trivia we can add this:

![alt text](https://i.imgur.com/3DmI9vF.png)

After that we need to set-up the client certificates. In order to do this navigate to the **Client Certificate** tab in your SSL Proxying Settings. Add a new client and input this:

(*Replace the "phone local host" with whatever your phones IP Address is. You can find this by going to Settings > Wifi > The little (i) next to your Wi-Fi connection.*)

Picture of Charles:

![alt text](https://i.imgur.com/46RgJGU.png)

My iPhones IP:

![alt text](https://i.imgur.com/x8ByXOa.png)

# Setting Up On Phone:

Now we move to our phone. For this tutorial I'm using iOS 12 on an iPhone 7 so it should work for anybody. On Android everything is practically the same but when installing the root certifiate you just navigate to the directory you saved it in (easiest to save to SD card) and press on the certificate. It will auto-install it.

#### Adding Charles Proxy Proxy

On our iPhone we need to navigate to Settings. From Settings go into Wifi settings and press on the little (i) next to your home network. It should bring you to a screen like this:

![alt text](https://i.imgur.com/BnXw2fg.png)

From here press on Proxy and change it to Manual. Fill in the information with the IP from your computer. (You can find this with ipconfig on Windows and ifconfig on Unix)

![alt text](https://i.imgur.com/Mum3DnY.png) ![alt text](https://i.imgur.com/IWV45DT.png)
Replace "computer.local.host" with your computers IP address. (Mine was 10.0.0.144. Common ones include 192.168.0.XXX, 192.168.1.XXX, and 10.0.0.XXX)

#### Installing The Root Certificate

Now we need to start the intercepter in Charles Proxy in order to download the SSL Certificate. In order to do this press the little Recorder button on Charles Proxy shown here:

![alt text](https://i.imgur.com/AYFycA2.png)

Now we need to navigate to charlesproxy.com/getssl on our device. You should get something like this pop up:

![alt text](https://i.imgur.com/kf5hvER.png)

Press allow and continue the installation of the certificate. If you are on Android is basically the same thing just save it to an SD Card or your file system, naviagte to it and press on the cert to install it.

Now we need to go to Settings > General > About > Certificate Trust > and Trust Charles Proxy. It should look like this:

![alt text](https://i.imgur.com/kf5hvER.png)

We are all set-up to start using Charles Proxy on our devices!

# Grabbing The API Key

Now for the fun part. Intercepting the traffic and pulling our API key from the headers. For the HQ Trivia API you need your user authentication which is sent everytime you open the app.

Start recording on Charles Proxy and open up HQ Trivia on your device. You will see https://api-quiz.hype.space show up with some directories below it. These should look like this in the sidebar:

![alt text](https://i.imgur.com/y7eW5Aw.png)

If you have this it's working! Simply click on any file inside that directory and in the right window of Charles Proxy you will see this!

![alt text](https://i.imgur.com/l6ORvl8.png)

 That "Authentication:" key is what we need. You're all set-up to start calling the HQ Trivia API now with your Authentication Key! Hope this helped out!
 
 # Links:
 
 Twitter: [@maxbridgland](https://twitter.com/maxbridgland)
 Discord Link for Dev Server: [Here](https://discord.gg/kuCqSMt)
 Donations: [Here](https://paypal.me/AuxilumDevelopment)
