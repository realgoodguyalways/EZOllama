# EZOllama
A ui intended to make offline ollama AI models ran through Termux on android devices seem more like an app than a terminal. 
<img width="270" height="460" alt="Screenshot_20260630_225623" src="https://github.com/user-attachments/assets/5b13e67f-23ca-45a1-ae52-c157762aefd4" />
<br>
 ## Installation 
1. install Termux & Termux:Boot off of F-Droid
2. open Termux:Boot then Termux
3. type in ```nano test.html``` then paste in the entirety of EZOllama.html into the file
   <br>
5. click ctr + s then ctr + x to save and exit this file
### automate hosting the server & starting the model:
6. type ```mkdir -p ~/.termux/boot``` and ```nano ~/.termux/boot/start-my-services.sh```
8. in this new file paste:
   ```
   #!/data/data/com.termux/files/usr/bin/sh

    termux-wake-lock

   ollama serve &
   sleep 5
   python -m http.server 8080 &
   ```
9. click ctr + s then ctr + x to save and exit this file
10. finally, type ```chmod 755 ~/.termux/boot/start-my-services.sh```
### not automated:
every time you want to use the app, you need to go into termux and type in
<br>
```ollama serve``` in one terminal
<br>
and ```python -m http.server 8080``` in another
<br> 
### accessing the app
1. go to chrome and type in ```127.0.0.1:8080/test.html```
### adding to homescreen
1. click on the 3 dots in the top right corner of the site, and scroll until you find add to home screen
2. once you click that, you can make an app like button that will open this site!
### Installing Models
1. firstly run ```pkg install ollama -y```
2. manually start ollama by running ```ollama serve```
3. finally, open a new session and type ```ollama run ``` followed by the name of the model you intend to use
<br>
Every model has its own strengths & weaknesses, make sure to research  which model is right for you!
