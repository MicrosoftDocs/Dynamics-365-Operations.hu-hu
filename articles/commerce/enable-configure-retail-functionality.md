---
title: Kiindulási adatok inicializálása új Commerce-környezetben
description: A cikk a Dynamics 365 Commerce inicializálási folyamatának részeként létrehozott adatokat ismerteti.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a12bd7a178d8d40db8c919410a00fbf021625f50
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238750"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a>Kiindulási adatok inicializálása új Commerce-környezetben

[!include [banner](includes/banner.md)]

A cikk a Dynamics 365 Commerce inicializálási folyamatának részeként létrehozott adatokat ismerteti.

Miután megtörtént a Kereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok.

> [!IMPORTANT]
> A kereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kereskedelmi üzletet fog beállítani. Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kereskedelemre akar használni.

A kereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.

1. Indítsa el a Commerce ügyfelet.
2. Kattintson a **Kiskereskedelem és kereskedelem** &gt; **Központ beállítása** &gt; **Paraméterek** &gt; **Kiskereskedelmi paraméterek** lehetőségre.
3. Kattintson az **Inicializálás** lehetőségre.

Az inicializálási a következő alapértelmezett konfigurációs adatokat hozza létre:

- Kereskedelmi tervezés és ütemezés feladatai és alfeladatai
- Kereskedelmi csatorna sémája
- Kereskedelmi ütemezések konfigurálása
- Alapértelmezett képernyő-elrendezések, beleértve a gombrácsokat, képeket és témákat
- Időzóna adatai
- Pénztári (POS) műveletek
- POS-engedélyek
- Csatornajelentések
- Attribútum metaadatai
- Entitás-ellenőrzési sablonok
- Kötegelt feladat a Commerce Data Exchange munkamenet-előzményeinek törlésére

Továbbá, a fizetésikártya-iparághoz (PCI) kapcsolódó naplózás engedélyezett a Commerce adatbázisa esetében.

> [!NOTE]
> Nincs lehetőség a Kereskedelmi tervezés és ütemezés külön konfigurálására. Ez az opció lehetővé teszi a Kereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra.

Az inicializálás befejezése után konfigurálni kell a kiegészítő kereskedelmi adatokat. Íme néhány példa:

- Kereskedelmi paraméterek
- Kereskedelmi ütemezés paraméterei
- Kereskedelmi csatornák
- Jegyzékek és eszközök
- Szortimentek


[!INCLUDE[footer-include](../includes/footer-banner.md)]