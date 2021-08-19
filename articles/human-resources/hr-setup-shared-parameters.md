---
title: Megosztott paraméterek konfigurálása
description: A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66f57c9613ba04ebb3748699105469586c27d66131c062d1af286b24199c4be7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723647"
---
# <a name="configure-shared-parameters"></a>Megosztott paraméterek konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.

Bizonyos típusú bejegyzések, például a Beosztás bejegyzések több vállalatra is kiterjednek. Ezen bejegyzésekhez megosztott paramétereket kell beállítani. Például a több jogi személyre kiterjedő emberi erőforrásokkal kapcsolatos paraméterek beállításához, használja az **Emberi erőforrások megosztott paraméterei** oldalt. 

Az **Emberi erőforrások megosztott paraméterei** oldalon a paraméterek a funkcióik alapján vannak területileg elkülönítve. 

### <a name="settings"></a>Beállítások
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Személyzetkezelés** &gt; **Hivatkozások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre. Egy egyszerű kódot és leírást adhat meg. 

A **Számsorozatok** lapon kiválaszthatja a következő bejegyzésekhez használt számsorozatokat: személyzeti szám, beosztás, felhasználói kérelem azonosítója, I-9 dokumentum, pályázó, vitafórum, juttatásazonosító és személyzeti művelet (ha engedélyezve van ez a bejegyzéstípus). A számsorozat-hivatkozások és a kódok fenntartásához használja a **Számsorozatok** listalapot. Az oldal megtalálásához használja az oldalkeresési funkciót. 

A **Beosztások** lapon adhatja meg hogy alapértelmezés szeriont elérhetők-e új beosztásokhoz hozzárendeléshez:

- **Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.
- **Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Ha ezt a lehetőséget választja, minden új beosztáshoz meg kell nyitnia a **Pozíció** lapot, amint az elérhetővé válik. Ezután az **Általános** lapon adja meg az **Elérhető hozzárendeléshez** dátumot, hogy engedélyezze a dolgozó hozzárendelését.

A **Speciális hozzáférés** lapon korlátozhatja a hozzáférést bizonyos adatokhoz és hivatkozásokhoz:

- **A dolgozói adatokhoz való hozzáférés korlátozása** – akkor kapcsolja be ezt a funkciót, ha a felhasználóknak csak azokkal a jogi személyekkel kapcsolatban kell látniuk az alkalmazotti adatokat, amelyekhez hozzáférésük van, illetve azokra az alkalmazottakra, akiknek van munkaviszonyuk az adott jogi személyeknél.

    Ha be van kapcsolva ez a funkció, a következő lépések szerint kell beállítania a megfelelő engedélyeket minden olyan felhasználóhoz, akinek a nézetét korlátozni kell:

    1. Jelöljön ki egy felhasználót a **Felhasználók** lapon.
    1. Szerepkör kiválasztása a felhasználó számára. Elérhetővé válik a **Szervezetek hozzárendelése** beállítás.
    1. Válassza ki a **Szervezetek hozzárendelése** lehetőséget.
    1. Válassza ki az új lapon a **Megadja a hozzáférést adott szervezetekhez egyenként**, majd válassza ki azokat a szervezeteket, amelyekhez a felhasználónak hozzáférést kell tudnia.
    1. Ismételje meg a 2–4. lépést a felhasználó összes többi szerepkörével, beleértve a rendszer felhasználói szerepkörét is.

    > [!NOTE]
    > A vállalatoknak, amelyekhez a felhasználó hozzáférhet, meg kell egyezniük a felhasználó összes szerepkörére nézve.

- **Vállalatközi kompenzációs nézet engedélyezése** – az alkalmazottak kompenzációja a foglalkoztatás jogi személye szerint van hozzárendelve. Előfordul, hogy egy alkalmazott egyszerre több jogi személynél is alkalmazásban áll. Ha ez a funkció be van kapcsolva, akkor az egyes jogi személyek kompenzációja megjelenik az alkalmazotti önkiszolgáló és a vezetői önkiszolgáló megoldásban anélkül, hogy a jogi személyeket meg kell változtatni. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
