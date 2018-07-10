# tips macbook

## Clean Hard drive Garage Band

https://www.tekrevue.com/tip/delete-garageband/

Apple’s GarageBand is a fantastic app that brings powerful audio creation and editing tools to music lovers of all levels. But it’s also a huge waste of space for users who don’t need it. Whether you’re musically challenged like us, or if you already use more advanced software like Logic Pro, Audition, or Pro Tools, here’s how you can delete GarageBand from your Mac, and save several gigabytes of storage space in the process.

Manually Delete GarageBand
As a rich media application, GarageBand installs relatively large groups of media files to several locations on your Mac’s drive. Based on a clean install of GarageBand 10.0.2 on OS X 10.9.3, key locations of large files include:

Macintosh HD/Applications/GarageBand.app (1.16GB)
Macintosh HD/Library/Application Support/GarageBand (995MB)
Macintosh HD/Library/Application Support/Logic (880MB)
Macintosh HD/Library/Audio/Apple Loops (up to 10GB)*
*Note that the size of the Apple Loops directory will vary depending on the number and type of loops downloaded by the user. You should not delete this folder (or the Logic folder) if you are using Logic Pro.

Under normal circumstances, however, users looking to delete GarageBand can expect to save around 3GB of space. It may not seem like much, especially as storage capacities continue to rise, but 3GB can make a huge difference for those with small SSDs.

To delete GarageBand, first quit all open applications and make a full system backup to be on the safe side. This can be accomplished via something like Time Machine or with the creation of a bootable clone with an app like Carbon Copy Cloner.

Once you’re all backed up, head to the locations listed above and delete them one by one, authenticating with an administrator account if asked. If you need a quick way to get to the folders in your System Library folder, open Finder and press Command-Shift-G to launch the Go to Folder window. Then just paste the folder’s location into the box and press Go.

With all files and folders moved to the Trash, right-click on the Trash icon in your Dock and choose Empty Trash. Finally, reboot to ensure that everything related to GarageBand is gone.

Delete GarageBand with a Third Party App
The above process nukes the GarageBand app and takes care of its large files, but there are still some small preference and support files that may be left behind. You can remove these manually by searching for “GarageBand” in your various system folders, or you can quickly hit them all with a third party OS X “uninstaller” app.

The two OS X uninstaller apps that we recommend are AppZapper ($13) and AppCleaner (Free). Both operate similarly: you launch the uninstaller app which gives you a blank “drop zone,” and you drag and drop the app you want to delete into the drop zone. AppZapper and AppCleaner will then scour your Mac for all of the associated support, preference, and data files that aren’t in the app’s self-contained bundle. These apps aren’t perfect, and do indeed miss things from time to time, but they’re generally a good place to start when trying to delete unwanted OS X apps.

There’s just a small bit of configuration that we must do first before we can use either app to delete GarageBand. The apps’ developers didn’t want users to inadvertently try to delete key OS X apps like Finder and Safari, so they installed safeguards to “protect” Apple applications.

AppZapper Preferences

To temporarily disable this safeguard so that we can delete GarageBand, launch either app and go to its Preferences menu by clicking the app’s name in the Menu Bar and selecting Preferences. In AppZapper, uncheck the box “Keep Apple Applications Safe.” In AppCleaner, go to the General tab and uncheck the box “Protect Default Apps.”

AppCleaner Delete GarageBand

With these boxes unchecked, you’ll now be able to drag and drop the GarageBand.app file into the drop zone and see the various preference and support files that are associated with it. Browse the list to make sure nothing important was incorrectly included and then press Zap! or Delete to remove the files. Just as with the manual instructions above, a reboot following this process is a good idea.

Once you delete GarageBand and its associated files, head back to the Preferences of either app and re-check the boxes that protect the deletion of default Apple applications. While handy, both of these apps can quickly get you in trouble if you delete the wrong files, so having that extra safeguard is key.

## Macbook itunes with AppSore

https://www.macg.co/logiciels/2017/10/le-retour-de-lapp-store-sur-mac-avec-itunes-1263-99993

En livrant mi-septembre iTunes 12.7, Apple a voulu réduire la voilure de son logiciel à tout faire, en supprimant l'accès à l'App Store (iOS) et la gestion des applications mobiles. Après tout, la majorité des utilisateurs d'iPhone et d'iPad se contentent d'explorer la boutique depuis leur appareil (et beaucoup n'ont tout simplement pas de Mac ou de PC).

Mais voilà, cette disparition n'a pas fait les affaires de tous. Ils sont un certain nombre à la regretter, en particulier dans les entreprises. Avec Apple Configurator et le programme d'achat en volumes, le constructeur a des solutions de gestion de flotte pour les sociétés, mais il peut être utile d'avoir un iTunes capable de déployer des applications sur des appareils iOS.


Installation d'iTunes 12.6.3 sur un Mac équipé d'iTunes 12.7.
C'est pourquoi Apple livre, un peu à la surprise générale, une nouvelle version d'iTunes au numéro de version antérieur à 12.7, mais que l'on peut installer en remplacement de 12.7. iTunes 12.6.3 est disponible pour macOS, Windows 32 et 64 bits (la note support officielle avec les liens de téléchargement).

Après installation d'iTunes 12.6.3 en remplacement d'iTunes 12.7, le logiciel prévient que la bibliothèque iTunes (iTunes Library.itl) ne peut être lue, celle-ci ayant été convertie par iTunes 12.7.


Il existe une manipulation facile pour retrouver le contenu de sa bibliothèque iTunes sous iTunes 12.6.3. Rendez-vous dans le dossier Utilisateurs > (Votre nom d'utilisateur) > Musique > iTunes Music > Previous iTunes Libraries. Repérez la bibliothèque convertie avec iTunes 12.7 : c'est celle qui présente la date du jour où vous avez installé cette version (sans doute autour de mi-septembre). Chez moi, c'est la sauvegarde précédente qui a fonctionné.


Remplacez le fichier iTunes Library.itl présent dans le dossier par la précédente bibliothèque iTunes Music. Vous aurez au préalable changé le nom de cette bibliothèque en iTunes Library.itl. Et comme par magie, on y retrouvera l'App Store, la bibliothèque d'apps, ainsi que la possibilité de télécharger et d'organiser les applications.



L'avantage de cette « nouvelle » version d'iTunes, c'est que l'on retrouve l'App Store sur nos bons vieux ordinateurs de bureau, ainsi que la gestion des apps. Et ce, aussi bien pour les entreprises que pour les particuliers. Autre intérêt, Apple ne proposera pas constamment la mise à jour vers iTunes 12.7. On ne sait pas en revanche le comportement du système quand une version 12.8 ou ultérieure viendra frapper à la porte : fermera-t-elle à nouveau la porte de la boutique après installation ?

