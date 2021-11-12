---
title: Áfakifizetés létrehozása
description: Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.
author: twheeloc
ms.date: 10/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54132ca4775482b4a06ff7e73125e804aff40cb4
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700113"
---
# <a name="create-a-sales-tax-payment"></a>Áfakifizetés létrehozása

[!include [banner](../../includes/banner.md)]

Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.

1. Ugorjon az **Adó > Bevallások > Áfa > Áfa kiegyenlítése és feladása** pontra.
2. A **Kiegyenlítési időszak** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
    - Ha nem választja ki a **Javítások figyelembevétele** opciót a **Főkönyvi paraméterek** lapon, a kiegyenlítés különböző verziókhoz feldolgozhatók. Az eredeti az időszak-intervallum első kiegyenlítése, és a rendszer csak egyszer dolgozza fel az időszak-intervallumban. A legutóbbi korrekciók kiegyenlíti az áfatranzakciókat, amelyeket az eredeti verzió létrehozása után adtak fel.
5. A **Tranzakció dátuma** mezőben adjon meg egy dátumot.
6. Kattintson az **OK** gombra.

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
