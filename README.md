# ynotranslations
Repository to host translations for the games present on [YNOproject](https://ynoproject.net).

## Installation Instructions
These instructions will allow you to use these translations offline.

### Requirements
* Download the [EasyRPG Player](https://easyrpg.org/player/downloads/) (make sure to use the version 0.8.0 or more recent, this info should be displayed on startup).
* Download the content of this repository (on the main page of the repository, `Code` -> `Download ZIP`).
* Download one of the games compatible with the translations available. Yume Nikki requires the [English Steam version](https://store.steampowered.com/app/650700/Yume_Nikki/), [Amillusion](https://ynfg.yume.wiki/Amillusion#Download), [Dream Genie](https://ynfg.yume.wiki/Dream_Genie_(梦鬼)#Original), and [FOG](https://rosegorm.itch.io/fog) require their latest English version, and [OneShot requires the EasyRPG adaptation made for YNOproject](https://drive.google.com/file/d/1KQFx1mACXlGNamy1dM2tIZqx2JZNVLDk/view?usp=drive_link). All the other games require to use the latest version released by their author(s) in their original language.
* Download the [RTP of RPG Maker 2000 and/or 2003](https://www.rpgmakerweb.com/run-time-package), if the game requires it. Yume 2kki and Ultra Violet require the RPG Maker 2000 RTP ([preferably in Japanese](https://tkool.jp/products/rtp/2000rtp.zip), otherwise [Yume 2kki will display a warning when saving](https://github.com/EasyRPG/Player/issues/3172), though this doesn't affect the gameplay), while Collective Unconscious and Uneven Dream require the RPG Maker 2003 RTP.

### Process
1. Unzip the content of the ynotranslations zip file.
2. Put the folder containing the translations of the game (named after the name of the game) in the folder of said game (the folder with the MapXXX.lmu files - make sure to put the folder in it, not just its content).
3. Rename said folder to `Language`.
4. Put the executable of the EasyRPG Player in the folder of the game or one of its root directories and start it (in the latter case, after launching the Player, select the folder(s) leading to the game to start it). Some platforms such as homebrews or Android may require to put your games in specific locations rather than where you want, so make sure to follow that too.
5. Once on the title screen, you should have an option to change the language of the game. Alternatively, in the latest version of the Player, opening the settings menu (accessible by pressing F1 or the Start button of a controller) should display a Language option if the translations are properly installed.

If you want to use a translation for the game Braingirl or OneShot, change the language through the settings menu if you are using an up to date version of the Player, or alternatively, you will need to pass the argument `--language {LANGUAGE}` to the executable (where `{LANGUAGE}` is the name of the folder of the translation wanted), which will launch the game directly in the selected language without having to use the language menu (using this argument to start a game without a `Language` folder will force older versions of the Player to close, so make sure to not use it in said case).

### Installing the RTP
This part assumes you are installing the RTP on Windows. If you are not, please refer to the [RTP page of the EasyRPG Wiki](https://wiki.easyrpg.org/user/player/rtp) for more specific details for your platform. If you want to install a Japanese RTP, you will need to use a locale application emulator such as [Locale Emulator](https://xupefei.github.io/Locale-Emulator/), or change the locale of your OS when launching the installer, otherwise the installation will fail at 44%.
1. Use the wizard installer given with the RTP download.
2. Process through the installation.
After this, the RTP should be installed, and EasyRPG Player should be able to detect it on the next launch.

## Producing a Translation

### Requirements
* A po file editor, such as [Poedit](https://poedit.net/). Alternatively, a text editor can be used, but it is NOT recommended as the syntax can vary for `\` characters, and that it is way easier to break the intended syntax, making the file unusable, which should not happen while using a proper tool.
* A text editor to edit the meta.ini file.
* A picture file editor, such as [paint.net](https://www.getpaint.net/), [GIMP](https://www.gimp.org/), [Aseprite](https://www.aseprite.org/)... Any can be used as long as it doesn't butcher the index, colours used and format.
* The EasyRPG tool [lcftrans](https://easyrpg.org/tools/) to generate the po files of the game needed for the translation, and to easily update them to the latest version of the game. Alternatively, if you do not understand or cannot make it work, you can either use the po files of another translation as the basis of yours, or ask for help in the [YNOproject Discord server](https://ynoproject.net/discord) or in one of the [EasyRPG platforms](https://easyrpg.org/contact/).
* [EasyRPG Player](https://easyrpg.org/player/downloads/) (make sure to use the version 0.8.0 or more recent, this info should be displayed on startup), to be able to test your translation.

#### Optional/Per Game/Language
* An audio file editor if there are vocals to translate, such as [Audacity](https://www.audacityteam.org/), though no audio files are translated in those games at the moment.
* If the game uses xyz files to store its pictures to translate (done for some files in Yume 2kki, done for all files in Yume Nikki, Mikan Muzou and OneShot), use the EasyRPG tools [xyz2png and png2xyz](https://easyrpg.org/tools/) to convert those files between the png (for edition) and xyz (for release) formats. Alternatively, you can use RPG Maker 2000 or 2003 to convert those files, by opening a project, going in the Resource Manager, and select Import file to the XYZ format, or Export file to the PNG format, both by selecting the file wanted. To more easily view the xyz files while searching in the various folders, you can use the EasyRPG tool [XYZ Thumbnailer](https://easyrpg.org/tools/) to be able to preview them in your file explorer.
* Font (WIP)

### Before Starting
- [Yume 2kki has rules tied to translations that must be respected](https://wikiwiki.jp/yumenikki-g3/%E6%B1%BA%E5%AE%9A%E4%BA%8B%E9%A0%85#TranslationGuidelines): please consult them before working on any translation work for Yume 2kki.
- If you want to work on a translation for Collective Unconscious, please enter in contact with the Collective Unconscious Team to do so (the Collective Unconscious Development Discord server is linked in the YNOproject Discord server).
- If you are submitting a translation for OneShot, do not base your work/do not reuse the commercial translations of OneShot.
- Do not upload translations or assets from translations you do not have the right for.

### Process
1. In the folder of your game, create a folder named `Language` next to the other game folders (Battle, CharSet, Picture...), if one doesn't exist yet.
2. In the Language folder, create a `{LANGUAGE}` folder (where `{LANGUAGE}` is the [Set 1 ISO Language Name of your language](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes), e.g. `de` for German, `fr` for French, `ja` for Japanese, `zh` for Chinese...). This will be your language folder to work with.
3. Create a Meta.ini in the folder of your language.
4. Write the Meta.ini file based on the syntax present on the [EasyRPG Translation Guide](https://easyrpg.org/player/guide/game_translation/). Write the name of your language in your own language for the `Name` field, and write a short description including contributors for the `Description` field, unless the character set of your own language is not supported without defining font which is not done before the language is selected: in that case, please write them in English. The Language word used for the `Term` field must match with how the game writes entries on the title screen (e.g. Yume 2kki centers the text, Dream Genie only uses the first letter, FOG writes in all capital letters...). Only include the `GameTitle` field if it is translated in your language.
5. Generate the po files needed for your translation. (WIP section, will expand it later)
6. Copy the po files in the folder of your language.
7. Delete the po files that are empty (can be the case with RPG_RT.ldb.battle.po), contain no text to translate (e.g. only lines there to display money or variable with no text to translate), and delete the RPG_RT.lmt.po file as well (contains the names of all maps, which are only used in 1) the debug menu to teleport to another map 2) the teleport skill menu to teleport to another map 3) if a Maniac patch game requests the map name using the command Control String Variables, none of them tied to the games translated here).
8. Translate the po files that contain lines you will translate using your po file editor. If a line is the same between the original language and your language, no need to translate it as the line in the original language will be used. If a message contains `\` characters, make sure to follow the syntax used in the original message. If a message box made out of several lines must take more than the four lines allowed by the game, you can write `<easyrpg:new_page>` after your fourth line, then format it as if it was a new message box. Lastly, `\_` corresponds to an half space in RPG Maker, which can be useful in some cases to center text or to fit more text in a place where no alternative is possible.
9. Delete the mo files generated by the po tool used, as those files aren't used for the translations.
10. Check the various folders of the game you want to translate, and locate files containing text you want to translate (for example, pictures in the Picture folder containing instructions).
11. Add the files you want to translate to the folder of your language, by replicating the file structure (e.g. if you were interested in the file `instructions` in the `Picture` folder, add a `Picture` folder in the folder of your translation, and place your `instructions` file there, while keeping the same filename).
12. Translate the files you need to translate using the appropriate tools (e.g. picture file editor to edit pictures). Make sure to not alter the colours used while editing your picture, to not change the colour used as the first placement in the index (this colour is used for transparency if the command calling it in-game is set to use transparency, so altering it would lead to display issues), and to respect how the original picture looks and how it should look whenever possible (graphy, colours used...).
13. Test your translation (see the next section).
14. If everything is translated and works correctly, you can create a pull request to include your content in this repository.

### Testing Process
- Test each place where text is displayed and where translated assets are used. This includes the menu, save menu, load menu all characters/items/skills used in the game, and more globally every place where the game uses text.
- Make sure every asset is properly displayed.
- Make sure every asset is properly set to be transparent when it should, and set to not be transparent when it should not.
- Make sure no unneeded/useless file is present (no content, no content to translate, mo file...).

### Testing Tips
- You can use the Fast Forward function in EasyRPG (hold F for x3 speed, G for x10) to go faster to places containing text to translate. You can also open the settings (by pressing F1 or the Start button of a controller) and change the speed set for those keys to go up to x100.
- You can use the TestPlay mode of EasyRPG to make things easier. To enable it, either pass the argument `--test-play` to the executable, replace the executable of the game (RPG_RT.exe) by the EasyRPG Player one and start the game through RPG Maker, or put the Player in a folder below the one of your game, and press Shift in the game browser while selecting your game to start it in TestPlay mode. While in TestPlay mode, you can press F9 to open the Debug Menu, which allows you to open the menu, save menu and load menu, useful to test their lines and save anywhere, allow you to give yourself all the items of the game, making it easier to test them, and allowing you to teleport directly to the maps containing text by selecting their ID. Holding CTRL will allow you to walk through walls, F10 interrupt the current running event, F11 save where you want, and Shift display test instantaneously.
- When generating a Map po file, each line will have a comment containing `ID X, Page Y, Line Z, Pos (A,B)`. The Pos corresponds to the coordinates where the event is on the map, so you can directly teleport yourself to the event using the teleport action in the Debug Menu. Alternatively, ID corresponds to the ID of the event containing the line, and Page in which page of the event it is, so you can use the function Call Event in the Debug Menu by specifying the ID and Page to more quickly display the line.
- You can use RPG Maker to slightly edit the games to give yourself what you want, such as skills, allow you to access specific menus to more quickly see things, or again directly display the assets needed. If you do that, make sure it doesn't affect the assets in use, such as the generated po files.


## Credits
* aku - Library's books for the English translation of Yume 2kki
* Aya - Initial French translation of Yume 2kki
* bathynomus - Brazilian Portuguese translation of Collective Unconscious
* Carbonara - French translations of Yume Nikki, .flow, Deep Dreams, Someday, Uneven Dream, Braingirl, Muma|Rope, Dream Genie, Mikan Muzou, Ultra Violet, She Awaits, Oversomnia, nostAlgic, Collective Unconscious, If, Unaccomplished; Misc edits and fixes on the Chinese translation of Yume Nikki, English translation of Yume 2kki, Mikan Muzou, French translation of Answered Prayers; Jigsaw Puzzle World, Plated Snow Country menu, Quick effect menu, Database for the English translation of Yume 2kki; Picture editing help on the Spanish translation of Yume 2kki, Romanian translations of Yume Nikki, Yume 2kki, Uneven Dream, Brazilian Portuguese translation of Yume 2kki; Update of Someday's translations; Testing and maintenance
* Catmat (貓毯) - Porting and maintenance of the Simplified Chinese and Traditional Chinese translations of Yume Nikki
* CDMilky - Romanian translation of Yume 2kki
* chillcicada (寒蝉) - Chinese translation of Muma|Rope
* CloudyThoughts - Esperanto translation of Yume Nikki
* Cool Person#8939 (369071 2458) - Finnish translation of Yume Nikki
* Cottage776 - Misc fixes for the Korean translation of Answered Prayers
* Eel - English translation of .flow
* ElTipejoLoco - Spanish translations of Deep Dreams, Mikan Muzou
* Eternal Dream Arabization team ( الحلم المتجدد للتعريب) - Help on the Arabic translation of Yume Nikki
* fcoldstar (飛揚寒星) - Simplified Chinese and Traditional Chinese translations of Yume Nikki
* Fettuccine Alfredo - Finnish translation of Collective Unconscious
* FlashfyreDev (Sam) - English translation of Yume 2kki; Misc edits on the English translation of Mikan Muzou
* .flow Chinese Group (.flow汉化组) - Chinese translation of .flow
* fokifox - Russian translation of Yume Nikki
* Fonvight - Russian translations of Yume 2kki, .flow, Answered Prayers, Deep Dreams, Someday, Uneven Dream, Braingirl, Muma|Rope, Dream Genie, Ultra Violet; English translation of the wallpaper gallery in Yume 2kki
* FukoSan - Spanish translation of Yume 2kki
* GiAnMMV - Italian translation of Yume Nikki
* Gugu (菇菇) - Chinese translation of .flow
* handsomedove - Korean translation of Yume 2kki
* Harti - German translation of Yume Nikki
* Haruku - Korean translation of .flow
* Hieshe - Brazilian Portuguese translation of Yume Nikki
* IStoleThePies - Text correction in the English translation of Yume 2kki
* Kong - Brazilian Portuguese translation of Yume 2kki, English Yume 2kki Memory Card game
* Kowinski - Testing of the Russian translation of She Awaits
* KRBlacky - Korean translations of Yume 2kki, Answered Prayers, Deep Dreams
* krossower1 - Polish translation of Yume 2kki
* Leo9 - Esperanto translations of Yume Nikki, .flow
* lich65 - Korean translation of Yume Nikki
* Lovena - Initial French translation of Yume 2kki; French translation of Oversomnia, nostAlgic
* maple - Polish translation of Uneven Dream, Collective Unconscious
* MAZ - Arabic translation of Yume Nikki
* Mhhh (Sundance) - Initial French translation of Yume 2kki; French translation of Answered Prayers
* Midomido - Japanese translation of Answered Prayers, Deep Dreams, Braingirl, Muma|Rope; English translation of the Debug Room in Yume 2kki
* miikka847 - Finnish translation of Yume Nikki
* Moucky2333 - Chinese translation of Uneven Dream, Collective Unconscious; Porting of the Chinese translation of Dream Genie; Testing of the Chinese translation of Someday
* Moustluigi - Initial French translation of Yume 2kki
* nask - Initial French translation of Yume 2kki
* nekhnona - Romanian translations of Yume Nikki, Yume 2kki, Uneven Dream
* Nex0.10 - Porting of the Chinese translation of Dream Genie
* Niko (Нико) - Spanish translations of Answered Prayers, Muma|Rope, .flow; Spanish translation of Yume 2kki
* nimiala - Toki Pona translations of Yume Nikki, Yume 2kki
* Nulsdodage (Wavyup) - Korean translation of Yume 2kki, Someday, English translation of Mikan Muzou
* Pats - Spanish translation of Yume Nikki
* Plush - Italian translations of .flow, Collective Unconscious
* portal - Initial French translation of Yume 2kki
* Proton - Finnish translation of Collective Unconscious
* RødGrødMedFløde - Danish translation of Yume Nikki
* Sainibi - Japanese translation of Someday
* Sakura - Japanese translation of Someday
* Sarah - Simplified Chinese and Traditional Chinese translations of Yume Nikki
* Shakzass - Spanish translation of Collective Unconscious
* Shirleycrow - Chinese translation of Someday
* srv_ui - Feedback on the French translation of She Awaits
* sniperbob - Hebrew translation of Yume Nikki
* takne77 - Estonian translation of Yume Nikki
* TrolChelavi - Russian translation of She Awaits
* uroyu - Japanese translations of Collective Unconscious, OneShot, Unaccomplished
* VioletNeiv - Vietnamese translations of Yume Nikki, Yume 2kki, .flow, Answered Prayers, Deep Dreams, Ultra Violet
* Voyager - Spanish translation of Yume Nikki
* Xiaodao (小岛) - Porting of the Simplified Chinese and Traditional Chinese translations of Yume Nikki
* YNOproject Chinese Team (YNOproject汉化组) - Chinese translation of Deep Dreams, Uneven Dream, Collective Unconscious
* YouArentDistorted (yugamineena) - English translation of Ultra Violet, nostAlgic, If; Wavy Up, Gimmick Runner, Plated Snow Country & Library's books for the English translation of Yume 2kki
* Yume 2kki Chinese Translation Group (梦二记汉化组) - Chinese translation of Yume 2kki
  
The Japanese version of Yume Nikki, Spanish version of Someday, French and Japanese versions of Amillusion, Chinese version of Dream Genie, Chinese version of Unaccomplished, and Spanish version of FOG, are made by the author(s) of their game, and are respectively made by Kikiyama, Jojogape, Team Compote, TanDen___ ☄, Moucky2333, and Alexis Priscilla.



