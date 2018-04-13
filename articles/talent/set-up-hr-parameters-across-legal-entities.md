---
title: "Több jogi személyre kiterjedő HR-paraméterek beállítása"
description: "A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 25d342272581abb96127d8761b3eac8d4f7695df
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-hr-parameters-across-legal-entities"></a>Több jogi személyre kiterjedő HR-paraméterek beállítása

[!INCLUDE [banner](includes/banner.md)]

A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.

Bizonyos típusú bejegyzések, például a Beosztás bejegyzések több vállalatra is kiterjednek. Ezen bejegyzésekhez megosztott paramétereket kell beállítani. Például a több jogi személyre kiterjedő emberi erőforrásokkal kapcsolatos paraméterek beállításához, használja az **Emberi erőforrások megosztott paraméterei** oldalt. 

Az **Emberi erőforrások megosztott paraméterei** oldalon a paraméterek a funkcióik alapján vannak területileg elkülönítve. 

### <a name="previously-released-functionality"></a>Korábban kiadott funkciók
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Személyzetkezelés** &gt; **Hivatkozások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre. Egy egyszerű kódot és leírást adhat meg. 

### <a name="if-youre-using-dynamics-365-for-talent"></a>Ha Dynamics 365 for Talent rendszert használ
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Emberi erőforrások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre. Egy egyszerű kódot és leírást adhat meg. 

A **Számsorozatok** lapon kiválaszthatja a következő bejegyzésekhez használt számsorozatokat: személyzeti szám, beosztás, felhasználói kérelem azonosítója, I-9 dokumentum, pályázó, vitafórum, juttatásazonosító és személyzeti művelet (ha engedélyezve van ez a bejegyzéstípus). A számsorozat-hivatkozások és a kódok fenntartásához használja a **Számsorozatok** listalapot. Az oldal megtalálásához használja az oldalkeresési funkciót. 

A **Beosztások** lapon adhatja meg hogy alapértelmezés szeriont elérhetők-e új beosztásokhoz hozzárendeléshez:

-   **Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.
-   **Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Ha ezt a lehetőséget választja, akkor meg kell nyitnia a **Beosztás** oldalt minden új beosztásre vonatkozóan, ahogy elérhetővé válik, és adja meg az **Általános lapon** az **Elérhető hozzárendeléshez** dátumot a dolgozó-hozzárendelés engedélyezéséhez.


<a name="see-also"></a>Lásd még
--------

[Vállalatfüggő HR-paraméterek beállítása](set-up-company-specific-hr-parameters.md)




