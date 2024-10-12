# Kanjidamage helper

Helps to find Kanji (meaning, components, onyomi, stroke order).

Source: https://www.kanjidamage.com/

![plot](/source/img/kd_01.gif)


### A. How to: Desktop
- **0** Download and unpack files (Code > Download ZIP)
- **1** Open ```kanjidamagehelper.html``` in your Web Browser, save in Bookmarks if required.
- **2** Hold ```CTR``` and mouseover on the Kanji.

### B. How to use: Anki
### Installation
- **0** Download and unpack files (Code > Download ZIP)
- **1** Add ```Official KanjiDamage deck``` (https://ankiweb.net/shared/info/748570187) or reordered version, it will download required images and JQuery library for a script work.

- **2** Add script ```anki/kanjidamage_anki_v0.1.js``` to folder ```APPDATA%\Roaming\Anki2\{profile name}\collection.media\```
	- **2.1**  To open ```%APPDATA%``` folder press ```Windows logo Key + R```, then type ```%APPDATA%``` and press ```Enter```

- **3** Change Anki Card Type template
	- **3.1**  Add JQuery library (came with "Official KanjiDamage deck")
   
   		```<script type="text/javascript" src="_jquery-2.2.2.min.js"></script>```
	- **3.2**  Add script
  
		```<script type="text/javascript" src="_kanjidamage_anki_v0.1.js"></script>```
		
	- **3.3**  Add popup
   
		```<div id="kdpp"></div>```
		
	- **3.4**  Add class ```kd``` to area where to search Kanji
		```<div class="kd">{{kanjis}}</div>```
		
	- **3.5**  Add styling
```
#kdpp{
	display: none;
	position: absolute;   
	padding: 5px 10px 10px 10px;
	background: #fff;	
	border: 1px solid #a8a8a8;	
	border-radius: 8px;	
	opacity:0.95;
	z-index:99;
}

#kdpp p{
	padding: 5px 0 0 0;
	margin: 0;
	font-size:16px;
	text-align:left;
}

#kdpp p:nth-child(1){
	color: #119933;	
	font-size:24px;
}

#kdpp p:nth-child(2){
	color: #aa3011;
}

#kdpp p:nth-child(3){
	color: #f0a011;
}

#kdpp p:nth-child(4){
	text-align:center;
}

#kdpp p:nth-child(4) img{
	width: 150px;
}
```

- **4** How it looks
  
![plot](/source/img/install_guide_01.jpg)
![plot](/source/img/install_guide_02.jpg)

### C. Customization
- **1** File ```/source/script.js```
	- **1.1** Kanji sort by frequency (by default) as ```Official KanjiDamage deck REORDERED``` 
		```
		//var kid = kfoundid[i]; //sort by number
		var kid = data[kfoundid[i]][5]; //sort by frequency
		```
	- **1.2** Kanji sort by ID number as ```Official KanjiDamage deck``` 
		```
		var kid = kfoundid[i]; //sort by number
		//var kid = data[kfoundid[i]][5]; //sort by frequency
		```
![plot](/source/img/install_guide_05.jpg)
- **2** File /source/style.css
	- **2.1** Change text color, size and font
		```
		body, textarea, input{
			font-size: 24px;
			color: #281e1e;
			font-family: Hiragino Sans,"?????? Pro","Hiragino Kaku Gothic Pro","????",Meiryo,"MS P????",sans-serif,Roboto;  
		}
		```
	- **2.1** Change background
		```
		body{						
			background-color: #e0e0e0;
			background-image:  radial-gradient(#7c7c7c 0.8px, transparent 0.8px), radial-gradient(#7c7c7c 0.8px, #dcdcdc 0.8px);
			background-size: 32px 32px;
			background-position: 0 0,16px 16px;		
		}
		```
- **3** File ```kanjidamagehelper.html```
	- **3.1** ```500``` is maximum learned Kanji number (based on sorting way, frequency or ID number). Update it due learning progress.			
		```
		<input type="text" value="500" id="tlmax">
		```
