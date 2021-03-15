---
title: Megosztott paraméterek konfigurálása
description: A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a7b399e0e8972a15837648d7ae6ec0eaacb5196b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130423"
---
# <a name="configure-shared-parameters"></a>Megosztott paraméterek konfigurálása

A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.

Bizonyos típusú bejegyzések, például a Beosztás bejegyzések több vállalatra is kiterjednek. Ezen bejegyzésekhez megosztott paramétereket kell beállítani. Például a több jogi személyre kiterjedő emberi erőforrásokkal kapcsolatos paraméterek beállításához, használja az **Emberi erőforrások megosztott paraméterei** oldalt. 

Az **Emberi erőforrások megosztott paraméterei** oldalon a paraméterek a funkcióik alapján vannak területileg elkülönítve. 

### <a name="previously-released-functionality"></a>Korábban kiadott funkciók
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Személyzetkezelés** &gt; **Hivatkozások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre. Egy egyszerű kódot és leírást adhat meg. 

### <a name="if-youre-using-dynamics-365-human-resources"></a>A Dynamics 365 Human Resources használata esetén
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Emberi erőforrások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre. Egy egyszerű kódot és leírást adhat meg. 

A **Számsorozatok** lapon kiválaszthatja a következő bejegyzésekhez használt számsorozatokat: személyzeti szám, beosztás, felhasználói kérelem azonosítója, I-9 dokumentum, pályázó, vitafórum, juttatásazonosító és személyzeti művelet (ha engedélyezve van ez a bejegyzéstípus). A számsorozat-hivatkozások és a kódok fenntartásához használja a **Számsorozatok** listalapot. Az oldal megtalálásához használja az oldalkeresési funkciót. 

A **Beosztások** lapon adhatja meg hogy alapértelmezés szeriont elérhetők-e új beosztásokhoz hozzárendeléshez:

-   **Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.
-   **Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Ha ezt a lehetőséget választja, akkor meg kell nyitnia a **Beosztás** oldalt minden új beosztásre vonatkozóan, ahogy elérhetővé válik, és adja meg az **Általános lapon** az **Elérhető hozzárendeléshez** dátumot a dolgozó-hozzárendelés engedélyezéséhez.


[!INCLUDE[footer-include](../includes/footer-banner.md)]