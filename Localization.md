# <font color='red'>WARNING! This project has been migrated to <a href='https://github.com/AgentMC/power8/wiki/Localization'>GitHub</a> </font> #
# Introduction #

Many people want their favorite software be presented in their language. But independent developers (like we) cannot afford hiring team of professionals each time a new version is released.

Here comes the power of community. If you want Power8 to be run in your mother tongue - no problem, go translate it!

# Details: Initial translate #

What you need is basically just couple of steps:

## 1. Get RESX file to translate ##
Download this file:
https://power8.googlecode.com/svn/trunk/Properties/Resources.resx - Main (and the only) resource file

## 2. Get Tool to translate ##
There are many tools to do this. The first simple one I found is [Resx Editor](http://sourceforge.net/projects/resx/). [Download](http://sourceforge.net/projects/resx/files/latest/download) it.

## 3. Translate! ##
Open the file you got with Resx Editor you got, and translate all the rows you can find.

## 4. Join your translation to Power8 ##
After you translated everything, contact any of the project team members, giving us these files and the Culture you're translating them into. For more information on culture, visit http://msdn.microsoft.com/ru-ru/goglobal/bb896001.aspx

That's it!

After you give us the files, we'll check them and join to the Power8 source code. They will automatically go to the next version release.

## 5. Test the UI ##
After that, we usually send the new translator the special build, that allows to quickly check the layout of windows usually hidden:
  * Welcome arrow (shown on 1st startup; currently no resources are from there, but who knows...);
  * Update Notifier (right-click the main button and choose "Check for updates". The test version is made to be something like "0.0.0.0", so it will show message);
  * Settings dialog (right-click the main button and choose "Settings...". Check all the tabs);
  * Show more computers (Main window - Network - "Show more...". Please note, it's OK that DEBUG version shows only "Computer0" to "Computer2999";
  * Restart Explorer (CTRL+SHIFT+Click the main button, note that the window's buttons do nothing via this command).


## Side notes ##
  1. Resx files have comments on some lines - follow them.
  1. If you like, after you contributed the translation, we can grant you a Contributor status.
  1. Your translation will be automatically shown on the Windows system where current UI language is set to your culture.
  1. After your translation is joined the project, we will put your name to main project page, and we can put there some your id/link/etc.
  1. One of the translatable resources is URL that you can use to point to your site, or use mailto: URI format; other one is string that includes your name - you and your contacts will be displayed in P8's About window.


# Details: update localization #

Each version and release adds new strings (images, videos as well :) ).
When it is close enough to the release and we believe no data will be introduced anymore, we synchronize ResX-s, i.e. we add new untranslated strings to your language's ResX file.

We do it only in case there's someone to translate the new strings. If the localizer goes out of the game, we "freeze" the ResX file - so some strings will be displayed in English for such languages.

After the sync is completed, we notify translators, and this notification contains the list of new strings.

Then, the preferred way is to proceed as described above except you download your culture's ResX. To do it, go [here](https://code.google.com/p/power8/source/browse/#svn%2Ftrunk%2FProperties), click on ResX you need (for example, `Resources.ru.resx` file), and then on the right side, click the "View raw file" link and select "Save Link As.." or "Save Target As..." or whatever your browser suggests for saving link target locally. The file will be downloaded to your PC.
![https://power8.googlecode.com/svn/wiki/Power8New02.png](https://power8.googlecode.com/svn/wiki/Power8New02.png)

It is recommended that you check **ALL** the strings in the file in case we forgot something and ensure that they are translated.

Next, contact us and we'll update the file and include it to release.