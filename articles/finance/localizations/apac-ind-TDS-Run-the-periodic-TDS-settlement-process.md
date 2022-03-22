---
title: Időszakos TDS-elszámolási folyamat futtatása
description: Ez a témakör elmagyarázza, hogyan kell elszámolni az időszakos forrásnál levont adót (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 05438b11f446da57016ff66f4deafd0c07fd62f32eba6f10c4b08b3f1de88e6b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739929"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Időszakos TDS-elszámolási folyamat futtatása

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan kell elszámolni az időszakos forrásnál levont adót (TDS).

1. Lépjen az **Adó \> Bevallások \> Adóelőleg \> Adóelőleg kifizetése** részhez.

    [![Adóelőleg-kifizetés párbeszédpanel.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. Az **Adóelőleg-fizetési** párbeszédpanel **Adótípus** mezőjében válassza a **TDS** lehetőséget.
3. Az **Adószámlaszám (TAN)** mezőben válassza az Adószámlaszámot (TAN) az elszámolási folyamat futtatásához.
4. Az **Adóelőleg-összetevő csoport** mezőben válassza ki azt a TDS-összetevőcsoportot, amelyhez futtatni szeretné az elszámolási folyamatot.
5. Az **Elszámolási időszak** mezőben válassza ki azt a TDS elszámolási időszakot, amelyhez futtatni szeretné az elszámolási folyamatot.

    > [!NOTE]
    > A TDS elszámolási folyamat a TDS elszámolási időszakára létrehozott valamennyi időszakra fut az **Adóelőleg-elszámolási időszakok** lap **Időszakok** fülén (**Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-elszámolási időszakok**).

6. A **Kezdő dátum** mezőben válassza ki a TDS-elszámolási folyamat futtatásának kezdő dátumát.

    Az elszámolási időszakon belül egy adott időszakra az időszakra meghatározott kezdőnapot kell „kezdő” dátumként tekinteni. A TDS elszámolási időszakának például két időszaka van: 2009. április 1-től április 30-ig, valamint 2009. május 1-től május 31-ig. Ha a **2009.06.04.** (2009. április 6.) dátumot választja kezdő dátumként a **Kezdő dátum** mezőben, az elszámolási folyamat 2009. április 1-jétől folytatódik.

    Ha egy későbbi időszakot a **Kezdő dátum** mezőben ad meg, de az elszámolási időszakon belül nem rendezi az előző időszakot, az elszámolás nem történik meg egyetlen korábbi időszakra sem. A TDS elszámolási időszakának például három időszaka van: 2009. április 1–április 30., 2009. május 1–május 31., 2009. június 1–június 30. Ha a **2009.01.05.** (2009. május 1.) dátumot választja kezdő dátumként a **Kezdő dátum** mezőből, az elszámolási folyamat csak 2009. május 1-től május 31-ig tart. Az elszámolásra nem kerül sor 2009. április 1-április 30-ig.

7. A **Tranzakció dátuma** mezőben válassza ki a TDS-elszámolási tranzakció feladásának dátumát.
8. Az **Adóelőleg-fizetési verzió** mezőben válassza ki a TDS-elszámolás verzióját:

     - **Eredeti** – Ezzel a beállítással először futtatja a TDS-elszámolási folyamatot. Az eredeti fizetési verziót csak egyszer használják a TDS-elszámolási folyamat futtatására a TAN, az adóelőleg-összetevő csoport és az adóelőleg-elszámolási időszak kombinációjához.
    - **Legújabb verziók** – Használja ezt a lehetőséget, ha a TDS-elszámolási folyamat már lefutott a megadott időszakra. Tartalmazza azokat a visszadátumozott tranzakciókat, amelyeket az elszámolási folyamat korábbi időszaka után tettek közzé. Ezzel a beállítással tetszőleges számú alkalommal futtathatja az elszámolási folyamatot.

9. Válassza a **Frissítés** jelölőnégyzetet a TDS-elszámolási folyamat futtatásához, és adja fel az összegeket a főkönyvi számlákra. Ha ez a jelölőnégyzet törlődik, az elszámolási folyamat nem fut, és a pénzügyi bejegyzések nem generálhatók.
10. Válassza az **OK** lehetőséget a TDS-kiegyenlítési folyamat futtatásához és az adóelőleg-fizetési jelentés generálásához. Az elszámolási folyamatban szereplő TDS-tranzakciók állapota **Kiegyenlítettként** jelenik meg az **Elszámolás** lapon (lépjen a **Kötelezettségek \> Kifizetések \> Szállítói fizetési napló** lehetőségre, válassza a **Sorok** lehetőséget, válassza a **Funkciók** lehetőséget, majd válassza az **Elszámolás** lehetőséget).

### <a name="important-points"></a>Fontos pontok

- Ha az elszámolási folyamat során nem jelöl ki adóelőleg-összetevő csoportot, az elszámolás a kiválasztott TAN- és elszámolási időszak összes adóelőleg-összetevő csoportjára történik. A **Nyitott tranzakció szerkesztése** lapon minden adóelőleg-összetevő csoporthoz külön sor jön létre.
- Az elszámolási folyamat az elszámolási időszakra vonatkozó értékelő kategória jellegén alapul. Azokat a tranzakciókat, amelyeknél az értékelő kategória jellege **Vállalat**, kiegyenlítik, és egy sorként jelennek meg a **Nyitott tranzakció szerkesztése** oldalon. Azokat a tranzakciókat, amelyeknél az értékelő kategória jellege **Vállalat**, kiegyenlítik, és egy sorként jelennek meg a **Nyitott tranzakció szerkesztése** oldalon.
- A **Nyitott tranzakció szerkesztése** oldalon az elszámolt TDS tranzakciósorok esedékessége a **Szállítók** oldalon a TDS-hatóság szállítója számára meghatározott fizetési feltételeken alapul. Ha a fizetési feltételek nincsenek meghatározva a TDS-hatóság szállítója számára, az elszámolási időszak utolsó napja jelenik meg az esedékesség napjaként.
