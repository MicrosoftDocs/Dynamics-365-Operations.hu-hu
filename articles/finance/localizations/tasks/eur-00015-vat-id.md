---
title: EUR-00015 Adószám beállítása
description: Ez az eljárás végigvezeti az áfaazonosító regisztrációs előfeltételein, például egy regisztrációs típus beállításán és a hozzárendelésén egy nyilvántartási kategóriához.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5488bb020209d6bf6fb39ae0b4f897f5513bdf93
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821803"
---
# <a name="eur-00015-set-up-vat-id"></a>EUR-00015 Adószám beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti az áfaazonosító regisztrációs előfeltételein, például egy regisztrációs típus beállításán és a hozzárendelésén egy nyilvántartási kategóriához. További információ a regisztrációs azonosítókról és a regisztrációs azonosítók feldolgozásáról, a szükséges előfeltételeket is beleértve, a Regisztrációs azonosító súgótémakörben található. 

Ez az információ minden európai országra/régióra vonatkozik. Ezt a feladatot elsődleges németországi címmel rendelkező DEMF bemutatócég mint jogi személy segítségével hozták létre. Ez a feladat rendszergazdáknak szól. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.

1. Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Regisztrációtípusok > Regisztrációtípusok lehetőségre.
2. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. A Név mezőbe írja be az „Áfaazonosító” szöveget.
4. A Leírás mezőbe írja be az áfaazonosítót.
5. Az Ország/régió mezőben adja meg vagy válassza a DEU értéket
6. Válassza ki az Igen lehetőséget az Egyedi mezőben.
    * Jelölje be ezt a jelölőnégyzetet annak ellenőrzéséhez, hogy az áfaazonosító egyedi-e.  
7. Válassza az Igen lehetőséget az Ország elsődleges címe mezőben.
    * Jelölje be ezt a jelölőnégyzetet, ha az áfaazonosítónak a megadott országhoz/régióhoz tartozó összes címhez érvényesnek kell lennie.  
8. Kattintson a Létrehozás lehetőségre.
9. Kattintson a Hozzáadás gombra.
10. Az Ország/régió mezőben adja meg vagy válassza az ITA értéket
11. A Formátum mezőbe írja be a következő értéket „###########”.
    * Amikor ilyen típusú kijelölt országhoz/régióhoz ad meg regisztrációs azonosítót, a regisztrációs azonosítót ennek a formátumnak megfelelően ellenőrizzük.  
12. Jelölje be az Egyedi jelölőnégyzetet.
    * Jelölje be ezt a jelölőnégyzetet annak ellenőrzéséhez, hogy az áfaazonosító egyedi-e.  
13. Jelölje be az Ország elsődleges címe jelölőnégyzetet.
    * Jelölje be ezt a jelölőnégyzetet, ha az áfaazonosítónak a megadott országhoz/régióhoz tartozó összes címhez érvényesnek kell lennie.  
14. Kattintson a Mentés gombra.
15. Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Regisztrációtípusok > Nyilvántartási kategóriák lehetőségre.
16. Kattintson az Új lehetőségre.
17. Az Ország/régió mezőben adja meg vagy válassza az Áfaazonosító, DEU értéket
18. A Nyilvántartási kategória mezőben válassza az „Áfaazonosító” lehetőséget.
    * Rendelje hozzá a korábban létrehozott regisztrációs típust egy előre megadott nyilvántartási kategóriához.  
19. Kattintson az Új lehetőségre.
20. Az Ország/régió mezőben adja meg vagy válassza az Áfaazonosító, ITA értéket
21. A Nyilvántartási kategória mezőben válassza az „Áfaazonosító” lehetőséget.
    * Rendelje hozzá a létrehozott regisztrációs típust egy előre megadott nyilvántartási kategóriához.  
22. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]