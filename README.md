# EZOllama
A ui intended to make offline ollama AI models ran through Termux on android devices seem more like an app than a terminal. 
<img width="270" height="460" alt="Screenshot_20260630_225623" src="https://github.com/user-attachments/assets/5b13e67f-23ca-45a1-ae52-c157762aefd4" />
<br>
 ## Installation 
1. install Termux & Termux:Boot off of F-Droid
2. open Termux:Boot then Termux
3. type in ```nano test.html``` then paste in the entirety of EZOllama.html into the file
   <br>
   ### automate hosting the server & starting the model:
5. click ctr + s then ctr + x to save and exit this file
6. then type ```mkdir -p ~/.termux/boot``` and ```nano ~/.termux/boot/start-my-services.sh```
7. in this new file paste:
   ```
   #!/data/data/com.termux/files/usr/bin/sh

    termux-wake-lock

   ollama serve

   python -m http.server 8080 &
   ```
8. click ctr + s then ctr + x to save and exit this file
9. finally, type ```chmod 755 ~/.termux/boot/start-my-services.sh```
### not automated:
every time you want to use the app, you need to go into termux and type in
<br>
```ollama serve``` in one terminal
<br>
and ```python -m http.server 8080``` in another
<br>
### Installing Models
1. firstly run ```pkg install ollama -y```
2. manually start ollama by running ```ollama serve```
3. finally, open a new session and type ```ollama run ``` followed by the name of the model you intend to use
<br>
Every model has its own strengths & weaknesses, make sure to research  which model is right for you!
