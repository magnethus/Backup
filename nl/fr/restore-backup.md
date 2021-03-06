---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauration à partir d'une sauvegarde

Procédez comme indiqué ci-après pour effectuer une restauration de fichier en utilisant {{site.data.keyword.backup_full}}. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restore-bmr-system-volume-image.html).

## Démarrage du portail {{site.data.keyword.backup_notm}}

Prenez soin de démarrer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}. Sinon, le lien du portail {{site.data.keyword.backup_notm}} ne fonctionnera pas.
{:important}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window}, puis cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.

      Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
4. Cliquez sur **Portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail {{site.data.keyword.backup_notm}} dans votre navigateur.

## Restauration de vos données

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**
2. Cliquez sur l'agent pour afficher les travaux.
3. Cliquez sur le travail qui contient les données souhaitées.
4. Cliquez sur **Exécuter la restauration**.
5. Sélectionnez la source de la restauration.
6. Sélectionnez la version de la sauvegarde.
7. Entrez le mot de passe de chiffrement.
8. Cliquez sur **Suivant** pour continuer.
9. Cochez les cases en regard des fichiers et des répertoires que vous voulez inclure, puis cliquez sur **Inclure** pour enregistrer vos sélections.
10. Vous pouvez filtrer davantage vos sélections à l'aide de la fenêtre qui s'affiche, ou cliquer sur **OK** pour utiliser en l'état les sélections que vous avez effectuées.
Une fois que vous avez ajouté vos choix en matière de fichiers et de répertoires, les fichiers ne peuvent plus être sélectionnés dans le panneau **Fichiers de données**. Ils sont affichés dans le panneau **Groupe de sauvegarde** sur la droite.

   Vous pouvez répéter l'étape 10 pour ajouter d'autres fichiers ou pour supprimer des fichiers que vous aviez ajoutés (à l'aide d'une instruction **Exclude**). Vous pouvez également utiliser l'option **Supprimer** pour éliminer une ligne quelconque du panneau **Groupe de sauvegarde**.
   {:tip}

11. Une fois que vous avez configuré ce groupe de sauvegarde selon vos souhaits, cliquez sur **Suivant** pour continuer.
12. Conservez les paramètres par défaut dans le panneau suivant ou personnalisez la restauration d'après vos préférences, puis cliquez sur **Exécuter la restauration**.
13. Les fichiers sont restaurés lorsque le statut passe à **Restauration terminée** sur l'écran **Informations du processus**.
