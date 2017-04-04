---
title: "Egy bizonylat- és árfolyam-korrekció frissítése Microsoft Dynamics 365 műveletek 1611-es verziójához"
description: "Néhány szervezet adja meg a naplók, amelyekben a bizonylat egynél több vevőhöz vagy szállítóhoz van, és is futtathatja a Kinnlevőségek vagy számlák külföldi pénznemben fizetendő átértékelési eljárás. Ez a témakör a következő lépések e szervezetek kell műveletek verzió 1611 azok rendszerre Microsoft Dynamics 365."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Egy bizonylat- és árfolyam-korrekció frissítése Microsoft Dynamics 365 műveletek 1611-es verziójához

Néhány szervezet adja meg a naplók, amelyekben a bizonylat egynél több vevőhöz vagy szállítóhoz van, és is futtathatja a Kinnlevőségek vagy számlák külföldi pénznemben fizetendő átértékelési eljárás. Ez a témakör a következő lépések e szervezetek kell műveletek verzió 1611 azok rendszerre Microsoft Dynamics 365.

Amikor Microsoft Dynamics 365 műveletek verzió 1611 frissít, kövesse az alábbi lépéseket.

1.  Dynamics 365 műveletekhez való frissítése előtt futtassa a deviza-átértékelési folyamatok a Kinnlevőségek és kötelezettségek. Állítsa be a **metódus** mező **számladátum**. Újraértékelési tranzakció jön létre, amely az utolsó árfolyam-korrekció visszavonása. Emiatt a nyitott tranzakciókat lehet értékelni az eredeti pénznem.
2.  Dynamics 365 1611 műveletek verzió frissítése.
3.  Futtassa újra a Kinnlevőségek és a fiókok külföldi pénznemben fizetendő átértékelési folyamatokat. Ez az idő beállítása a **metódus** mező **Standard**. Új átértékelés tranzakció jön létre, amely az aktuális árfolyamokkal. Ez a tranzakció nem realizált nyereség/veszteség és a megfelelő összesített főkönyvi számláján rögzíti.



