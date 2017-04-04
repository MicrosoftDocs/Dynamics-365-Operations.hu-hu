---
title: "Új kiskereskedelmi környezetben a kiindulási adatok inicializálása"
description: "A cikk ismerteti a Microsoft Dynamics 365 műveletek - kiskereskedelmi az inicializálási folyamat részeként létrehozott adatokat."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 137c675781cf75d9ce621a84c89224019c161362
ms.lasthandoff: 03/31/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Új kiskereskedelmi környezetben a kiindulási adatok inicializálása

A cikk ismerteti a Microsoft Dynamics 365 műveletek - kiskereskedelmi az inicializálási folyamat részeként létrehozott adatokat.

Miután megtörtént a Kiskereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kiskereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok. **Fontos:** A kiskereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kiskereskedelmi üzletet fog beállítani. Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kiskereskedelemre akar használni. A kiskereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.

1.  Indítsa el a Dynamics 365 műveletek ügyfél.
2.  Kattintson a **kereskedelmi és kereskedelmi**&gt;**központ telepítési**&gt;**paraméterek**&gt;**kiskereskedelmi paraméterek**.
3.  Kattintson az **Inicializálás** lehetőségre.

Az inicializálási a következő alapértelmezett konfigurációs adatokat hozza létre:

-   Kiskereskedelmi tervezés és ütemezés feladatai és alfeladatai
-   Kiskereskedelmi csatornaséma
-   Kiskereskedelmi elosztási ütemezések
-   Alapértelmezett képernyő-elrendezések, beleértve a gombrácsokat, képeket és témákat
-   Időzóna adatai
-   Pénztári (POS) műveletek
-   POS-engedélyek
-   Csatornajelentések
-   Attribútum metaadatai
-   Entitás-ellenőrzési sablonok
-   Kötegelt feladat a Commerce Data Exchange-munkamenet-előzmények törlésére

Ezenfelül naplózást, vagyis kapcsolódó műveletek adatbázis a Dynamics 365 engedélyezett-e a fizetési kártya (PCI) ipar. **Megjegyzés:** Nincs lehetőség a Kiskereskedelmi tervezés és ütemezés külön konfigurálására. Ez az opció lehetővé teszi a Kiskereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra. Az inicializálás befejezése után konfigurálni kell a kiegészítő kiskereskedelmi adatokat. Íme néhány példa:

-   Kiskereskedelmi paraméterek
-   Kiskereskedelmi tervezés és ütemezés paraméterei
-   Kiskereskedelmi csatornák
-   Jegyzékek és eszközök
-   Szortimentek



