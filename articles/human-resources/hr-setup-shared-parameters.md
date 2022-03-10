---
title: Megosztott paraméterek konfigurálása
description: Ez a témakör bemutatja az emberi erőforrások paramétereinek jogi személyek közötti beállítását.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 039d8e2100824921d568c013fe3e113e1b091979
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7729099"
---
# <a name="configure-shared-parameters"></a>Megosztott paraméterek konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A több vállalat között megosztott rekordokra vonatkozó megosztott paramétereket is be kell állítania, például a **·** Pozíciórekordok beállítását. Ez a témakör bemutatja az emberi erőforrások paramétereinek jogi személyek közötti beállítását.

Bizonyos típusú rekordok, például a **·** pozíciórekordok, vállalatok között meg vannak osztva. Ezen bejegyzésekhez megosztott paramétereket kell beállítani. Például az Emberi erőforrások megosztott paraméterei lap használatával lehet beállítani az emberi erőforrások paramétereit **·** a jogi személyek között. 

Az **Emberi erőforrások megosztott paraméterei** oldalon a paraméterek a funkcióik alapján vannak területileg elkülönítve. 

### <a name="settings"></a>Beállítások
Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat. Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania. A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani. Új azonosítási típus meghatározásához vagy a meglévő típusok listájának ellenőrzéséhez kattintson a Személyzeti kezelés – **·** &gt; **·** &gt; **·** &gt; **Beállításazonosító típusok** gombra. Egy egyszerű kódot és leírást adhat meg. 

A Számsorozatok lapon kiválaszthatja a következő rekordokhoz használt számsorozatokat: Személyzeti szám, Beosztás, Felhasználói kérelem **·** **·** **·** **·** azonosítója, **I-9** dokumentum, **Pályázó,** **·** **·** **·** Vitafórum, Juttatásazonosító és Személyzeti művelet (ha ez a rekordtípus engedélyezve van). A számsorozat-hivatkozások és a kódok fenntartásához használja a **Számsorozatok** listalapot. Az oldal megtalálásához használja az oldalkeresési funkciót. 

A **Beosztások** lapon adhatja meg hogy alapértelmezés szeriont elérhetők-e új beosztásokhoz hozzárendeléshez:

- **Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.
- **Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Ha ezt a lehetőséget választja, minden új beosztáshoz meg kell nyitnia a **Pozíció** lapot, amint az elérhetővé válik. Ezután az **Általános** lapon adja meg az **Elérhető hozzárendeléshez** dátumot, hogy engedélyezze a dolgozó hozzárendelését.

A **Speciális hozzáférés** lapon korlátozhatja a hozzáférést bizonyos adatokhoz és hivatkozásokhoz:

- **A dolgozói adatokhoz való hozzáférés korlátozása – akkor válassza ezt a funkciót, ha a felhasználóknak csak azoknak a jogi személyeknek az alkalmazotti adatait kell megtekinteniük, amelyekhez hozzáférésük van, illetve azoknak az alkalmazottaknak az esetében, akiknek van munkaviszonyuk az adott** jogi személyeknél.

    A funkció kiválasztása után kövesse az alábbi lépéseket annak érdekében, hogy beállítsa a megfelelő engedélyeket minden olyan felhasználóhoz, akinek nézetét korlátozni kell:

    1. Jelöljön ki egy felhasználót a **Felhasználók** lapon.
    1. Szerepkör kiválasztása a felhasználó számára. Elérhetővé válik a **Szervezetek hozzárendelése** beállítás.
    1. Válassza ki a **Szervezetek hozzárendelése** lehetőséget.
    1. Válassza ki az új lapon a **Megadja a hozzáférést adott szervezetekhez egyenként**, majd válassza ki azokat a szervezeteket, amelyekhez a felhasználónak hozzáférést kell tudnia.
    1. Ismételje meg a 2–4. lépést a felhasználó összes további szerepkörével, beleértve a rendszer felhasználói szerepkörét is.

    > [!NOTE]
    > A vállalatoknak, amelyekhez a felhasználó hozzáférhet, meg kell egyezniük a felhasználó összes szerepkörére nézve.

- **Vállalatközi kompenzációs nézet engedélyezése** – az alkalmazottak kompenzációja a foglalkoztatás jogi személye szerint van hozzárendelve. Előfordul, hogy egy alkalmazott egyszerre több jogi személynél is alkalmazásban áll. Ha ez a funkció be van jelölve, az egyes jogi személyek kompenzációja megjelenik az Alkalmazotti önkiszolgáló és a Vezető önkiszolgáló szolgáltatásban, anélkül, hogy a jogi személyeket **·** meg kell **·** változtatni. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
