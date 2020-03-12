---
layout: post
title: Outil "4D_Info_Report"
permalink: /info_report_fr/
categories: [PROCESS, SUPPORT]
tags: [info, report, component, 4D]
lang: fr
lang-ref: info_report
---

![info_report](/images/info_report.png)

## A quoi sert ce composant ? (version 4.9rZF)

Le composant `4D_Info_Report` sert à collecter un maximum d'informations :

* sur l'environnement système, matériel, 4D

* sur la base : structure, données, triggers, index, réglages personnalisés utilisés, etc.

* en temps réel et en production : mémoire, cache, utilisateurs connectés, process, etc.

</br>

## Comment utiliser ce composant ? EditerSupprimerEditer

**_Procédure n°1 :_**

Créer un dossier "Components" à côté de la structure ou de l'application (si ce dossier n'existe pas), copier le composant désarchivé et redémarrer 4D ou 4D Server.

Vous pourrez directement exécuter la méthode partagée : "aa4D_NP_Report_Manage_Display" depuis 4D Distant.

Un dialogue du composant vous permettra de démarrer la procédure stockée pour créer un rapport toutes les N minutes sur le Server.

Vous pouvez aussi implémenter dans votre base hôte cet exemple de code dans la méthode base "Sur démarrage serveur" pour exécuter toute méthode partagée (leur nom commence par "aa4D_") :

<pre>
  <code class="4d">
 TABLEAU TEXTE($at_Components;0)
 LISTE COMPOSANTS($at_Components)
 Si(Chercher dans tableau($at_Components;"4D_Info_Report@")>0)
  // pour démarrer la procédure stockée créant un rapport toutes les 5 minutes
    EXECUTER METHODE("aa4D_NP_Schedule_Reports_Server";*;5;0)
 Fin de si
  </code>
</pre>

Procédure n°2 :

Vous pouvez juste créer un rapport en exécutant la méthode partagée "aa4D_NP_Util_CreateReport_Serv".

Les rapports (fichier texte) sont créés dans un nouveau dossier "Folder_Reports" à côté du fichier de données.


Dans les 2 cas, vous devez ensuite créer une nouvelle méthode partagée "aa4D_Host_GetDBParam" avec le code ci-dessous :

  // Nom de la méthode: aa4D_Host_GetDBParam (doit être partagée avec les composants)
 C_ENTIER LONG($1) // sélecteur
 C_REEL($0)
 $0:=-1 // Erreur, pas de paramètre
 Si(Nombre de parametres>0)
    $0:=Lire parametre base($1)
 Fin de si

</br>

## Comment analyser les rapports ? EditerSupprimerEditer

Vous pouvez analyser ces rapports :

    à partir d'un 4D distant en exécutant la méthode "aa4D_NP_Report_Manage_Display",

    à partir d'un 4D monoposte en ouvrant le composant et en cliquant sur le menu "Fichier" puis sur "Local reports compare".


Démonstration vidéo sur l'utilisation du composant en français :

    en Haute Définition sur le site de Vimeo

</br>

## Téléchargement EditerSupprimerEditer

* documentation (en anglais) : 4D_Info_Report_v4_9_Ref_v28.pdf

* base hôte v15 utilisant des méthodes hôtes à inclure dans votre base (merci d'ajouter le composant dans le dossier "Components" pour tester) : 4D_Info_Report_Host_T_v7_v15.zip

* composant en version 4D v18 : 4D_Info_Report_v4_9rZF_v18.zip

* composant en version 4D v17 (compilé uniquement en 64 bits) : 4D_Info_Report_v4_9rZF_64-bit_v17.zip

* composant en version 4D v17 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZF_v17.zip

</br>

## Archives

* composant en version 4D v16 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZC_rev1_v16.zip

* composant en version 4D v15 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZ8_rev1_v15.zip

* composant en version 4D v14 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZ2_v14_rev1.zip

    composant en version 4D v13 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZ2_v13_rev1.zip

    composant en version 4D v12 (compilé aussi en 64 bits) : 4D_Info_Report_v4_9rZ_v12.zip

    base hôte v12 utilisant des méthodes hôtes à inclure dans votre base (merci d'ajouter le composant dans le dossier "Components" pour tester) : 4D_Info_Report_Host_T_v6_v12.zip