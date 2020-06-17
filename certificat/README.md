# Certificat

[https://help.apple.com/developer-account/](https://help.apple.com/developer-account/)

Les certificats sont des fichiers .cer ou .p12 lorsqu'ils sont exportés depuis de trousseau.

## Qui peut créer des certificats ?
1. Les membres "Admin" et "Account Holder" peuvent créer des certificats de distribution et de développement.
2. Les membres "Developer" peuvent créer uniquement des certificats de développement.


## Pour créer un certificat :

1. Création d'un fichier de demande de signature de certificat. (fichier avec extension .certSigningRequest)
2. Transmission du fichier auprès d'Apple sur le site Apple Developper
3. Apple génère le certificat (fichier .cer)
4. Télécharger le fichier .cer
5. On double clique sur le fichier .cer
6. Il est transmis au Trousseau d'accès (Session / Mes certificats)

## Pour importer un certificat depuis le compte Apple Developper

1. Télécharger le fichier .cer
2. On double clique sur le fichier .cer
3. Il est transmis au Trousseau d'accès (Session / Mes certificats)

## Pour exporter / importer un certificat entre 2 ordinateurs

1. Depuis le trousseau d'accès, exporter avec un fichier .p12
2. Créer un mot de passe pour plus de sécurité
3. Importer le ficher .p12 avec mot de passe


## Certificat de développement

## Certificat de distribution

# Provisioning Profile

Le Provisioning Profile est associé à :

* un certificat
* un Bundle ID
* plusieurs Devices IDs (Development) / aucun device ID (distribution)   

## Qui peut créer des Provisioning Profile ?
1. Les membres "Admin" et "Account Holder" peuvent créer des Provisioning Profile.
2. Les membres "Developer" ne peuvent pas en créer.

## J'ai un provisioning profile, mais je ne me rappelle plus à quel certificat il est associé

Depuis le Finder, sélectionner le fichier .mobileprovision, et regarder l'aperçu. Il y a une section SHA1 qui définie le certificat associé.
Ensuite, il faut aller dans le trousseau d'accès pour vérifier qu'il est bien présent. Session > Mes certificats > Menu contextuel > lire les informations > empreintes > sha1

## Pour créer un Provisioning Profile

1. Se loguuer sur le site apple.developer.com
2. Appuyer sur Profiles 
3. Appuyer sur le bouton +
4. Associer l'App ID
5. Associer le certificat
6. Télécharger le fichier.mobileprovision
7. L'ouvrir avec Xcode

## Où trouver les Provisioning Profile dans Xcode

```
cd ~/Library/MobileDevice/Provisioning\ Profiles 
```

