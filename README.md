# **Bubble Polybar**

**Bubble Polybar** is designed to prioritize **user comfort** and **elevate productivity** on Linux systems. These Polybar dotfiles have been curated with a keen emphasis on **streamlining your experience**, offering a **seamless computing environment**. It also has a **spotify module** in which you can **open spotify**, know the **name of the current playing song** and **its progress**, **pause**, **play** and **change the song**.
<p align="center">
<a href="color-presets/coal/colors.txt">
<img src="imgs/coal.gif"
	alt="black bar"
	width="100%"
	height="auto"
/>
</a>
</p>

Here are some examples of how this bar looks with some **color presets** (learn how to customize **colors** [here](#change-colors)):

<p align="center">
<a href="color-presets/night-blue/colors.txt">
<img src="imgs/night-blue.gif"
	alt="dark blue bar"
	width="100%"
	height="auto"
/>
<a href="color-presets/snow/colors.txt">
<img src="imgs/snow.gif"
	alt="white bar"
	width="100%"
	height="auto"
/>
</a>
<a href="color-presets/sky-blue/colors.txt">
<img src="imgs/sky-blue.jpg"
	alt="light blue bar"
	width="100%"
	height="auto"
/>
</a>
<a href="color-presets/cotton-candy/colors.txt">
<img src="imgs/cotton-candy.jpg"
	alt="pink bar"
	width="100%"
/>
</a>
</p>

## **Installation**
### **Install Polybar**
Ensure you have **Polybar** installed in your system (you can use the packet manager of your Linux distribution to install it), you can download it from [the official Polybar GitHub repository](https://github.com/polybar/polybar). **You should not download it from apt or other package managers, because they usually dont have the latest version and it might not work properly**.
### **Install dependencies**
In order to run this polybar dotfiles, you have to install the following dependencies:
- **bash**, **net-tools**, **sed**, **bc**, **awk**, **coreutils**, **grep**, **ffmpeg**, **procps**, **curl**, **cron**, **xclip**, **python3**, **pip** (install them through the packet manager of your linux distribution).
- **spotify-cli** (install it through **pip**):

		$: pip install spotify-cli-linux
- **CodeNewRoman Nerd Font** (download it from [Nerd Fonts](https://www.nerdfonts.com/font-downloads)) and **Hack Font** (download it from [source-foundry's GitHub](https://github.com/source-foundry/Hack/releases/tag/v3.003)). Unzip them and place them in **/usr/share/fonts**.

		$: unzip folder.zip -d folder
  		$: sudo mv folder /usr/share/fonts
### **Install Bubble Polybar**
- Clone this repository into the **~/.config/polybar** directory (create it if doesn't exist).

		$: mkdir -p ~/.config/polybar
		$: cd ~/.config/polybar
		$: git clone https://github.com/wdeloo/bubble-polybar
- Edit the **cron** file running the following command:

		$: crontab -e
	and add the following line to the opened file:

		* * * * * ~/.config/polybar/bubble-polybar/scripts/ip/ip.sh getPub
- Allow turning off and reboot as non privileged user editing **/etc/sudoers**:

		$: sudo nano /etc/sudoers
	and add the following two lines:

		%wheel ALL=(ALL:ALL) NOPASSWD: /usr/bin/systemctl poweroff
		%wheel ALL=(ALL:ALL) NOPASSWD: /usr/bin/systemctl reboot
- Edit the **~/.config/polybar/bubble-polybar/scripts/programs.txt** file and edit the **programs** you want to run when clicking on each module at the right of the bar (*browser*, *text editor*, *file manager*, *terminal*, *launcher*):

		$: nano ~/.config/polybar/bubble-polybar/scripts/programs.txt
- To change the notes, use the scripts **~/.config/polybar/bubble-polybar/scripts/note/note1** and **~/.config/polybar/bubble-polybar/scripts/note/note2**.
## **Run** or **Refresh** Bubble Polybar
- Run the "**bubble-run.sh**" script:

		$: ~/.config/polybar/bubble-polybar/scripts/bubble-run.sh
## Customize Bar
***DONT FORGET TO REFRESH THE POLYBAR AFTER MAKING ANY CHANGE IN THE BAR***
### **Change Colors**
- Edit the **~/.config/polybar/bubble-polybar/scripts/colors.txt** file and write **3 colors** in [hex format](https://g.co/kgs/bRy6NYK) in the **3 first lines** (*background*, *text*, *icons*). Then, refresh the bar to apply the changes:

		$: nano ~/.config/polybar/bubble-polybar/scripts/colors.txt
		$: ~/.config/polybar/bubble-polybar/scripts/bubble-run.sh
### **Change Icons**
- Edit the **\*.sh** script in **~/.config/polybar/bubble-polybar/scripts/\*** and search for the icon and replace it. For example, if you want to change the clock icon at the left of the time, edit the **~/.config/polybar/bubble-polybar/scripts/date/date.sh** file and replace the clock icon with something else:

		$: nano ~/.config/polybar/bubble-polybar/scripts/date/date.sh
	you can find some icons to use in [Nerd Fonts](https://www.nerdfonts.com/cheat-sheet).
