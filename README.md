# AI_StackChan_Minimal
AI Stack-chan - Minimal. Based on robo8080's [AI Stack-chan 2](https://github.com/robo8080/AI_StackChan2) and [ATOM Echo Port](https://github.com/robo8080/M5Unified_AtomEcho_ChatGPT), this project aims to create <B>a "toy Stack-chan" that anyone can easily enjoy</B> (excluding servo operation, wake words, etc.). You can start learning about programming and IoT when you become interested!
<br><br>
==Added GPT-4o mini and multilingual support (beta) on 2024/7/19==
<br><br>

<img src="images/AI_StackChan_Minimal01.jpg" width="50%"><br>
[![StackChan4ALL](images/StackChan4ALL.jpg)](https://x.com/robo8080/status/1781203208846860503)

Features<br>
- Redesigned as a "minimal configuration that can be used like a toy" so anyone can get started easily
	- Affordable price: Around 3,000 yen (~$20 USD)
	- Easy to build: Can be installed without a programming environment. Hardware assembly uses only "wires and snap-fit connections" (no soldering required)
	- Easy-to-use UI: Wireless WiFi/API key configuration (no need to write in programs or SD cards). You can also change character voices/AI models, and ask questions via text input for longer conversations
- Web services used and pricing (costs are minimal when using low-price models, but please be aware)
	- Conversational AI: [ChatGPT](https://platform.openai.com/docs/overview)
		- [Pricing - GPT-3.5 Turbo/4o](https://openai.com/api/pricing/)
	- Text-to-Speech: [Web VOICEVOX (Fast)](https://voicevox.su-shiki.com/su-shikiapis/)
		- Pricing - Free (intended for personal use)
		- Reference - VOICEVOX: [Character List](https://voicevox.hiroshiba.jp/)
		- Credits - VOICEVOX:Zundamon, VOICEVOX:Shikoku Metan, VOICEVOX:Aoyama Ryusei, VOICEVOX:WhiteCUL
	- Speech Recognition: Choose either [OpenAI Whisper](https://openai.com/api/pricing/) or [Google Cloud STT](https://cloud.google.com/speech-to-text?hl=en)
		- [Pricing - Audio models: Whisper](https://openai.com/api/pricing/)
		- [Pricing - Speech-to-Text V1 API](https://cloud.google.com/speech-to-text/pricing?hl=en)
<br>

Acknowledgments<br>
- First and foremost, a huge thank you to robo8080 who poured their heart and soul into releasing AI Stack-chan.<br>
- Thanks to everyone in the community who supported the birth of AI Stack-chan! (Illustration by Misuji)<br>
	- [![StackChan4ALL](images/StackChan4ALL2.jpg)](https://x.com/Chy_hobby/status/1679438264867102721)
- Google Cloud STT implementation was based on "MhageGH"'s [esp32_CloudSpeech](https://github.com/MhageGH/esp32_CloudSpeech/ "Title"). Thank you!<br>
- Thanks to "Inaba" and "kobatan" for their invaluable advice on implementing OpenAI Whisper support.<br>
---


### Required Materials and How to Build AI Stack-chan Minimal (Prices as of 2024/06/14) ###
It works with just an Atom Echo! However, assembling the following components will result in a cuter Minimal version<br>
- ATOM Echo (microcontroller unit) [approx. 2,000-2,500 yen / ~$15-18 USD]
	- The main unit that runs the program. When connected to a display, you can communicate with faces and text
	- <B>Note: The speaker is extremely small, so please use at low volume and for short periods.</B> Conversation is fine, but it's not suitable for music playback
		- <a href="https://www.mouser.jp/ProductDetail/M5Stack/C008-C?qs=81r%252BiQLm7BQ%2FzW%2Fdq5IHnA%3D%3D" target="_blank">Mouser: 2,066 yen</a>
		- [DigiKey: 2,220 yen](https://www.digikey.jp/ja/products/detail/m5stack-technology-co-ltd/C008-C/12174736)
		- [Switch Science: 2,475 yen](https://www.switch-science.com/products/6347)
- OLED Display (0.96 inch 128×64 dots) [approx. 600 yen / ~$4 USD]
	- One equipped with SSD1306. Connect to the unit with 4 wires (I2C connection)
	- <B>Note: Various sizes are available, so please verify it fits in the case: <B>Size: Width 25.2mm x Height 26mm</B>
		- <a href="https://akizukidenshi.com/catalog/g/g115870" target="_blank">Akizuki Denshi: 580 yen</a>
- Jumper Wires (Female-Male) (10cm) [approx. 700 yen / ~$5 USD]
	- Used to connect the ATOM Echo and OLED display. Please use short wires that fit inside the case
		- <a href="https://www.amazon.co.jp/dp/B072N2WR5N/" target="_blank">Amazon Japan: 699 yen</a>
- Enclosure Case
	- 3D models are available for free on this page. Please print and use. Pre-printed case sales are under consideration
		- [3D_model: Free](https://github.com/A-Uta/AI_StackChan_Minimal/tree/main/AI_StackChan_Minimal/3D_model)
			- [How to use] front.stl and back.stl are a set. Snap them together after printing.
			- [2024/06/10] Added v02 model


### Hardware Assembly Process (Overview) ###
 0. Bend the jumper wires at 90 degrees using needle-nose pliers (or tweezers if unavailable)
 1. Connect the jumper wires between [ATOM ECHO](https://docs.m5stack.com/en/atom/atomecho "Title") and the OLED display as shown below<br>
 <img src="images/wire_setting.jpg"><br>
 2. Coil the jumper wires as shown in the diagram
 3. Insert the display into the front of the 3D Model
 4. Insert the ATOM Echo head-first into the front as shown, and push the wires into the empty space at the bottom right
 5. Place the back of the 3D Model from behind and snap it closed using the ear tabs
 6. Complete!
![Image1](images/making_all01_A.jpg)<br><br>
- Complete assembly process (click image for video)<br>
[![Step01H](images/x_stackchan01h.jpg)](https://x.com/UtaAoya/status/1794201200294035694)

---

### Obtaining API Keys for Web Services ###
- OpenAI API (ChatGPT and Whisper)
	- [Reference: How to obtain/register OpenAI API key](https://nicecamera.kidsplates.jp/help/6648/)
	- Visit the [OpenAI website](https://openai.com/) and create an account. Email address and mobile phone number are required
	- After creating an account, generate an API key. API keys are paid, but there are free trial periods and credits
- Web VOICEVOX
	- Can be obtained from "Generate apiKey here" on the [WEB VOICEVOX API (Fast)](https://voicevox.su-shiki.com/su-shikiapis/) page
	- [Reference: How to obtain/register WEB VOICEVOX API key](https://zenn.dev/mongonta/articles/8aac1041c628d4)
	- <B>Note: As this is a free service, audio playback may be interrupted during busy times</B>
	- [Latest speaker ID list (humming not supported)](https://www.voicevox.su-shiki.com/voicevox-id)
- Google Cloud Speech to Text
	- <B>Note: Not required if using Whisper for speech recognition</B>
	- [Reference: How to create Google Cloud STT (speech recognition) API key (by Okimoku)](https://scrapbox.io/stack-chan/Google_Cloud_STT%EF%BC%88%E9%9F%B3%E5%A3%B0%E8%AA%8D%E8%AD%98%EF%BC%89%E3%81%AEAPI%E3%82%AD%E3%83%BC%E3%81%AE%E4%BD%9C%E3%82%8A%E6%96%B9)
	- [Reference: What is Google Speech Recognition API? Features, pricing plans, and how to use](https://www.notta.ai/blog/how-to-use-google-speech-to-text-api)
	- Visit the [Google Cloud Platform website](https://cloud.google.com/?hl=en) and create an account. Email address and mobile phone number are required. Card registration is mandatory, but there are free trials and free tiers
	- After creating an account, obtain an API key
	- Don't forget to enable Speech to Text for your API key
---

### Connecting PC to Hardware ###
1. (For Windows) Before connecting via USB, open Device Manager from search to find the COM port number you'll need to specify later<br>
[![Step01](images/M5Burner00.jpg)](https://x.com/UtaAoya/status/1801740652201525296)
- <B>Note: Atom Echo should be recognized on Windows without driver software, but for other operating systems or if not recognized, please refer to the following page</B>
	- [Reference: How to use M5Burner v3 (by Saito Tetsuya)](https://zenn.dev/saitotetsuya/articles/m5stack_m5burner_v3)<br>
		- This refers to the "Driver" section in step 3. Preparation
---

### Software: Installation Process (Using M5 Burner tool. No programming environment required) ###
1. Download M5Burner for your PC environment from [this M5Stack page](https://docs.m5stack.com/en/download)<br>
[![Step01](images/M5Burner01.jpg)](https://docs.m5stack.com/en/download)

2. (Windows version explanation from here) Extract the downloaded file and run M5Burner.exe<br>
[![Step02](images/M5Burner02.jpg)](https://github.com/A-Uta/AI_StackChan_Minimal)

3. When a message appears, click "More info" then click the "Run anyway" button to launch<br>
[![Step03](images/M5Burner03.jpg)](https://github.com/A-Uta/AI_StackChan_Minimal)

4. Select "ATOM" from the left menu and click the Download button for "Stackchan-AI Stack-chan-Minimal". After successful download, click the Burn button, then click Continue<br>
[![Step04](images/M5Burner04.jpg)](https://github.com/A-Uta/AI_StackChan_Minimal)

5. Click the Start button to begin installation (firmware writing), and it's complete when "Burn successfully, click here to return" is displayed<br>
[![Step04](images/M5Burner05.jpg)](https://github.com/A-Uta/AI_StackChan_Minimal)

- [Reference: How to use M5Burner v3 (by Saito Tetsuya)](https://zenn.dev/saitotetsuya/articles/m5stack_m5burner_v3)<br>
---


### Software: Requirements for Building & Installing via Programming ###
- [ATOM ECHO](https://docs.m5stack.com/en/atom/atomecho "Title")<br>
- VSCode<br>
- PlatformIO<br>
	- [Reference: Stack-chan Creation Notes by Electronics Beginner 6 (PlatformIO Environment Setup)](https://note.com/ku_nel_5/n/n5bbdd5e176bf)

*Please refer to "platformio.ini" for the libraries used. However, to enable text scrolling, the Avatar library has been copied to the lib folder with modifications (not loaded via platformio.ini)<br>

---


### How to Use (Click images for videos) ###
1. After building the program or installing the software, configure WiFi connection using the smartphone app: ESP Touch*<br>
[![Step01](images/x_stackchan01.jpg)](https://x.com/UtaAoya/status/1794857755968508118)
	- [Reference: ESP Touch: Setting up Wi-Fi from smartphone with Seeed Studio XIAO ESP32C3 SmartConfig](https://lab.seeed.co.jp/entry/2022/10/17/120000)
	- <B>Note: Select ESPTouch. "ESPTouch v2 is for ESP32C3 only"</B>
	- <B>Note: ESP Touch must connect to "2.4GHz" WiFi. Atom Echo cannot be found on 5GHz</B>
		- [Reference: Choosing wireless communication methods with M5StickC (ESP32)](https://lang-ship.com/blog/work/m5stickc-esp32-radio/)


2. Configure API keys from a web browser<br>
[![Step02](images/x_stackchan02.jpg)](https://x.com/UtaAoya/status/1794864738746478920)

3. Single click to "chat", double-click to "display settings status" and enjoy!<br>
[![Step03](images/x_stackchan03.jpg)](https://x.com/UtaAoya/status/1796206485296562645)

4. From the settings menu, you can change "character voice" and "conversational AI model". You can also have longer conversations using "text conversation"<br>
[![Step04](images/x_stackchan04.jpg)](https://x.com/UtaAoya/status/1801027113543204893)

5. From the settings menu under "Language/Character Voice", you can switch between Japanese/English/Chinese for conversations<br>
[![Step04](images/x_stackchan05.jpg)](https://x.com/UtaAoya/status/1812855452277023221)

---


### Frequently Asked Questions ###
Q. The character won't speak / audio cuts out<br>
A. The VoiceVox API key may not be set. Please configure the API key from the settings menu in your browser<br>

<br>
<br>
<br>