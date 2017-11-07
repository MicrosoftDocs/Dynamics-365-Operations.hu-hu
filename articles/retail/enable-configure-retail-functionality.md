---
title: "A kiindulási adatok inicializálása új Retail-környezetben"
description: "A cikk a Microsoft Dynamics 365 for Retail inicializálási folyamatának részeként létrehozott adatokat ismerteti."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ac4f651cd7e5df912ea2535eafd5e54c11377253
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>A kiindulási adatok inicializálása új Retail-környezetben

[!include[banner](includes/banner.md)]


A cikk a Microsoft Dynamics 365 for Retail inicializálási folyamatának részeként létrehozott adatokat ismerteti.

Miután megtörtént a Kiskereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kiskereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok. **Fontos:** A kiskereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kiskereskedelmi üzletet fog beállítani. Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kiskereskedelemre akar használni. A kiskereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.

1.  Indítsa el a Dynamics 365 for Retail klienst.
2.  Kattintson a **Kiskereskedelem** &gt; **Központ beállítása** &gt; **Paraméterek** &gt; **Kiskereskedelmi paraméterek** lehetőségre.
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

Továbbá, a fizetésikártya-iparághoz (PCI) kapcsolódó naplózás engedélyezett a Dynamics 365 for Retail adatbázis esetében. **Megjegyzés:** Nincs lehetőség a Kiskereskedelmi tervezés és ütemezés külön konfigurálására. Ez az opció lehetővé teszi a Kiskereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra. Az inicializálás befejezése után konfigurálni kell a kiegészítő kiskereskedelmi adatokat. Íme néhány példa:

-   Kiskereskedelmi paraméterek
-   Kiskereskedelmi tervezés és ütemezés paraméterei
-   Kiskereskedelmi csatornák
-   Jegyzékek és eszközök
-   Szortimentek





