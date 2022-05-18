---
title: Áfakifizetés létrehozása
description: Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.
author: twheeloc
ms.date: 01/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c388a8f98cd4581abe2ec13d8922e232321e4039
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735865"
---
# <a name="create-a-sales-tax-payment"></a>Áfakifizetés létrehozása

[!include [banner](../../includes/banner.md)]

Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.

1. Ugorjon az **Adó > Bevallások > Áfa > Áfa kiegyenlítése és feladása** pontra.
2. A Kiegyenlítési **időszak mezőben** kattintson a legördülő gombra a keresés megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Adjon meg egy dátumot a **Kezdő dátum** mezőben. Ha nem választja ki a **Javítások figyelembevétele** opciót a **Főkönyvi paraméterek** lapon, a kiegyenlítés különböző verziókhoz feldolgozhatók. **Az** eredeti egy időszak első kiegyenlítése, amely egy időszak-intervallumban csak egyszer feldolgozható. A legutolsó korrekciók az eredeti verzió létrehozása után feladott áfatranzakciókat egyenlítik ki.
5. A **Tranzakció dátuma** mezőben adjon meg egy dátumot.
6. Válassza ki az **OK** lehetőséget. Az **áfakifizetések jelentés** nyomtatása az időszak kiegyenlített áfatranzakcióinak áttekintésére.

A Pénzügy 10.0.24-es verziójától kezdve ki lehet választani azt az áfakifizetési jelentést, amely közvetlenül azután jön létre, **·** **·** **·** **hogy** a Funkciókezelés munkaterületének Külön áfakifizetési jelentés létrehozása funkciójának Az áfakifizetések kiegyenlítése funkció külön megvalósítása után kerül sor az Áfakifizetések kiegyenlítése műveletre.

Ha a funkció engedélyezve van, a kiegyenlítési folyamat befejezése után a program nem nyomtat áfajelentést. Ehelyett a következő üzenet jelenik meg: "Az áfa kiegyenlítése és feladása befejeződött. Az 'xxxx, m/e/évyy' bizonylat feladva."

Az áfakifizetési **jelentést továbbra is manuálisan futtathatja a TaxInquiries** > **és reportsSales** > **taxnquiriesSales** > **adókifizetések** által.

## <a name="performance-consideration"></a>Teljesítménnyel kapcsolatos észrevételek

Az áfafizetési eljárás elvégzése hosszú időt vehet igénybe. Az eljárás teljesítményét befolyásoló fő tényezők a számlák száma a kiegyenlítési időszakban, illetve az áfafizetési bizonylaton feladandó bejegyzések száma. A jobb teljesítmény érdekében ki lehet kerülni a folyamatban nem szükséges funkciókat.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Engedélyezze az Áfafizetési teljesítmény javítása funkciót

Az **Áfafizetési teljesítmény javítása** funkció a könyvelési pénznem összegének és a jelentési pénznem összegének összesítésével javíthatja az áfafizetési eljárás teljesítményét, ahol a bizonylatsorok azonos fő számlával, főkönyvi dimenzióval és pénznemmel rendelkezik.

1. Válassza a **Rendszerfelügyelet** \> **Munkaterületek** \> **Funkciókezelés** elemet.
2. A **Mind** lapon keresse meg és válassza ki az **Áfafizetési teljesítmény javítása** lehetőséget.
3. Válassza az **Engedélyezés** lehetőséget.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Az ellenoldali adótranzakciók generálásának megakadályozása

Alapértelmezés szerint az áfafizetési bizonylat az áfafizetési eljárásban kiegyenlített minden egyes áfatranzakció ellenoldali adótranzakcióját adja fel. Ezek az ellenoldali áfatranzakciók szerepelnek az **Áfa/főkönyvi egyeztetés** jelentésben. Az időszakban ki nem egyenlített áfatranzakciók fennmaradó egyenlegét mutatják.

Az ellenoldali áfatranzakciók ugyanakkor megnövelik az áfafizetési eljárás terhelését. Ezért igény szerint aktiválható egy **TaxReportGenOffsetTaxTransPerRecordSetFlighting** nevű tesztelés. Az ilyen teszteléssel javítható Thaiföld, Lengyelország, Magyarország, Malajzia, India, Olaszország, Oroszország, Csehország, Észt Köztársaság és Lettország kivételével az egyes országokban és régiókban generált ellenoldali áfatranzakciók teljesítménye.

> [!NOTE]
> Ha az adótranzakciós tábla egyedi mezőket tartalmaz, akkor a tesztelést nem lehet aktiválni.

Mivel az **Áfa/főkönyvi egyeztetési** jelentést általában csak belső ellenőrzési célokra használják, és sok adóügylethez nincs szükség rá, dönthet úgy, hogy nem hoz létre ellenoldali áfatranzakciókat az áfafizetési bizonylaton.

1. Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfa kiegyenlítési periódusok** elemre.
2. Válassza ki a kifizetési időszakot.
3. Az **Általános** gyorslapon állítsa **Az ellenoldali adótranzakciók létrehozásának megakadályozása** beállítást **Igen** értékre.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
