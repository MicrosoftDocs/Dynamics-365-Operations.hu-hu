---
title: Formátumok módosítása Excel-sablonok újbóli alkalmazásával
description: Az alábbi lépések végrehajtásához először hajtsa végre az „ER-konfiguráció létrehozása az OPENXML formátumban létrejövő jelentésekre vonatkozóan” eljárás lépéseit.
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e66a2e24d3b1e77d5c790d2f3b7cfdce98fc4cca6e3734ad8b87ac7714192853
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749656"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>Formátumok módosítása Excel-sablonok újbóli alkalmazásával

[!include [banner](../../includes/banner.md)]

Az alábbi lépések végrehajtásához először hajtsa végre az „ER-konfiguráció létrehozása az OPENXML formátumban létrejövő jelentésekre vonatkozóan” eljárás lépéseit.

Ez az eljárás azt ismerteti, hogyan módosíthatja egy elektronikus jelentési (ER) formátum konfigurációját egy módosított Microsoft Excel-sablon ismételt alkalmazásával. Ebben az eljárásban egy módosított Excel-sablont importálunk az ER-formátum konfigurációkba, amelyeket a Litware, Inc. mintavállalathoz hoztak létre, és ezután elvégezzük az elektronikus dokumentumok létrehozását. Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült. A lépések a GBSI-adathalmazzal hajthatók végre. A kezdés előtt töltse le és mentse a SampleVendPaymWsReport2.xlsx fájlt, amely a Elektronikus jelentéskészítési formátum módosítása egy Microsoft Excel-sablon ismételt alkalmazásával súgótémakörben szerepel (modify-electronic-reporting-format-reapply-excel-template/).

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  

## <a name="select-the-er-format"></a>Az ER-formátum kiválasztása
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
2. A fában bontsa ki a „Payment model” elemet.
3. A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.
4. Kattintson a Mellékletek lehetőségre.
    * Vegye figyelembe, hogy jelenleg az SampleVendPaymWsReport.xlsx Excel-fájl van használatban sablonként a fizetési napló feldolgozásához.   
5. Kattintson a Megnyitás gombra.
    * Kattintson a Megnyitás elemre az Excel-sablon elrendezésének megtekintéséhez.  
    * Végezze el a sablon felülvizsgálatát. Megjegyzés: jelenleg a következő adatokat tartalmazza minden kifizetési sorhoz: szállító számlaszáma, szállító neve, bank, bank regisztrációs azonosítója, számlaszám, tartozik, követel és pénznem. Ebben a példában ki szeretnénk bővíteni a listát a fizetési dátum részletes adatainak hozzáadásával.   
6. Zárja be a lapot.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Új Excel-sablon újbóli alkalmazása az ER-formátumra
1. Kattintson a Tervező pontra.
    * Nyissa meg szerkesztésre kijelölt ER-formátum piszkozatverzióját.  
2. A Művelet panelen kattintson az Importálás gombra.
3. Kattintson a Frissítés az Excel programból lehetőségre.
    * Kattintson a 'Sablon frissítése' lehetőségre, és jelölje ki a SampleVendPaymWsReport2.xlsx fájlt.  
    * Kattintson a Sablon frissítése lehetőségre, és tallózással keresse meg a korábban letöltött SampleVendPaymWsReport2.xlsx fájlt.  
4. Kattintson az OK gombra.
    * A SampleVendPaymWsReport2.xlsx sablont alkalmazza a program. A rendszer szinkronizálja az ER-formátum struktúráját a sablon tartalmával, amelynek az elemei hozzáadódnak az ER-formátumhoz. Bármely meglévő elem az ER-formátumban, amely nem szerepel a sablonban, törlődik a formátum definíciójából.  
5. A fastruktúrában válassza ki ezt: 'Excel'.
    * Vegye figyelembe, hogy a Sablon mező most már az új sablonra mutató hivatkozást tartalmaz.   
6. Kattintson a Mellékletek lehetőségre.
7. Kattintson a Megnyitás gombra.
    * Kattintson a Megnyitás elemre a módosított Excel-sablon elrendezésének megtekintéséhez.  
    * Végezze el a sablon felülvizsgálatát. Vegye figyelembe, hogy most már tartalmaz egy sort a fizetési dátumnak.   
8. Zárja be a lapot.
9. A fastruktúrában bontsa ki ezt: „Excel”.
10. A fában bontsa ki az „Excel\PaymLines” elemet.
11. A fastruktúrában válassza ki ezt: „Excel\PaymLines\PaymDate”.
    * Megjegyzendő, hogy az ER-formátum most eggyel több elemet tartalmaz. A cella PaymDate cella hozzá lett adva az Excel-sablonhoz.  
12. Kattintson a Hozzárendelés fülre.
13. A fában bontsa ki a „model” elemet.
14. A fában bontsa ki a „model\Payments” elemet.
15. A fán válassza ki a „model\Payments= Transactions\Transaction date(TransactionDate)” pontot.
16. Kattintson a Kötés gombra.
    * Adja meg, hogy milyen adatok lesznek hozzáadva az új cellához futásidőben.  
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Az ER-formátum módosított piszkozatverziójának engedélyezése a fizetési napló feldolgozásának használatához
1. Kattintson a Konfigurációk lehetőségre a Művelet Panelen.
2. Kattintson a Felhasználói paraméterek lehetőségre.
3. Válassza az Igen lehetőséget a Beállítások futtatása mezőben.
4. Kattintson az OK gombra.
5. Kattintson a Szerkesztés lehetőségre.
6. Válassza az Igen lehetőséget a Vázlat futtatása mezőben.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Az ER-formátum módosított piszkozatverziójának használata a fizetési napló feldolgozásához

Tekintse át a létrehozott munkalapot, beleértve a fizetési sorok új adatát, a fizetési dátumot.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]