---
title: ER - Célok konfigurálása
description: Ez az eljárás bemutatja, hogy hogyan lehet a különböző helyeket beállítani és használnia az Elektronikus jelentés (ER) kimeneti összetevőire, például egy mappára vagy egy fájlra vonatkozóan.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
ms.openlocfilehash: 3c8d03e9783013183fbe76cb36014fa9e1e1cbed
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291054"
---
# <a name="er-configure-destinations"></a>ER - Célok konfigurálása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet a különböző helyeket beállítani és használnia az Elektronikus jelentés (ER) kimeneti összetevőire, például egy mappára vagy egy fájlra vonatkozóan. Ez az eljárás az DEMF bemutatócéget használja. Németország a jogi személy elsődleges címének országa\régiója, de ezen eljárás bármely jogi személyét használhatja. 

Ezen példa formátuma az ISO20022 Jóváírás átvitele, de bármilyen formátumot használat, amelyet már importált. Ne feledje, hogy ez az eljárás egyetlen fájl és egyetlen cél beállítás példája. Az elektronikus jelentési célok kezelésével kapcsolatos további információk a Dynamics 365 Pénzügyi súgóban találhatók.

1. Ugorjon a Szervezeti adminisztráció > Elektronikus jelentéskészítés > Elektronikus jelentéskészítési cél pontra.
2. Kattintson az Új lehetőségre az új célkészlet létrehozásához a formátumra vonatkozóan.
3. Válassza ki a Hivatkozás mezőben azt a formátumot, amelyre vonatkozóan konfigurálni kívánja a célokat.
    * Ha nem rendelkezik értékkel a kiválasztáshoz, az azt jelenti, hogy nem importált egyetlen Elektronikus jelentési formátum konfigurációt sem. Importálnia kell a formátum konfigurációt a rendeltetések beállítása előtt.  
4. Kattintson az Új lehetőségre az új fájlcél létrehozásához.
    * Vegye figyelembe, hogy egy fájl célját ugyanazon formátum, például egy mappa vagy egy fájl minden egyes kimeneti összetevőjére vonatkozóan létrehozhatja. Lehetővé válik a rendeltetések külön történő engedélyezés és letiltása a beállításokban.  
5. A Név mezőben adja meg a kimeneti összetevő közérthető nevét.
    * Azt javasoljuk, hogy használjon felismerhető nevet, például a „Fizetési fájl” vagy az „Ellenőrzési jelentés” nevet. Ezek a nevek a felhasználóknál jelennek meg a konfigurációs futásidőben a célok beállítása mellett.  
6. Válasszon ki egy fájlt vagy egy mappát a Fájlnévben, amely jellemző a formátumra.
7. Kattintson a Beállítások lehetőségre.
8. Válassza ki az Igen lehetőséget az Engedélyezve mezőben.
    * Az egyes lapokon található Engedélyezett jelölőnégyzet az egyes célokat külön-külön engedélyezi és letiltja. Ebben a példában engedélyezi a kimeneti fájl egy levél címzett számára történő küldését a fájl létrehozásakor.  
9. Kattintson a Szerkesztés lehetőségre az e-mail-címzettek beállításához.
10. Kattintson a Hozzáadás gombra.
11. Kattintson a Kezelési e-mail nyomtatása lehetőségre.
12. Válasszon ki egy lehetőséget az Üzenetforrás mezőben.
    * Választhat a különböző e-mail-forrástípusok közül, például a vevő vagy a szállító típus közül. Ez azon argumentum típusát adja meg, amelyet az E-mail forrás számla képlet visszaküld. A következő lépésekben meghatározott E-mail forrás számla képlet azt a helyet jelenti, ahol üzenetforrást köt. Válassza ki a Szállítót, ha a képlet egy szállítói számlát jelenít meg. Használja a Szállítót, ha az ISO 20022 Jóváírás átvitele konfigurációs példát használja.  
13. Kattintson az Üzenetforrás kötése lehetőségre.
14. A Képletben adja meg a dokumentum-specifikus hivatkozást a korábban kiválasztott féltípushoz.
    * A beírás helyett megkeresheti azon adatforrás-csomópontokat, amelyek a felek számláját jelölik, és az Adatforrás hozzáadása gombra kattinthat a képlet frissítéséhez. Ha például az ISO 20022 Jóváírás átvitele konfigurációt használja, a szállítói számlát jelölő csomópont a „$PaymentsForCoveringLetter”.Creditor.Identification.SourceID. Ellenkező esetben bármilyen karakterlánc típusú értéket megadhat, például a „DE-001” értéket a képlet mentéséhez.  
15. Kattintson a Mentés gombra.
16. Zárja be a lapot.
17. Kattintson a Szerkesztés gombra a fél kapcsolattartói adatainak beállításához.
18. Válassza ki az Igen lehetőséget az Elsődleges kapcsolattartó mezőben.
    * Különböző beállítások segítségével jelezheti, hogy a fél milyen kapcsolattípusát kell a cél e-mail-címeként használni. Ebben a példában az elsődleges kapcsolattartót használjuk.  
19. Kattintson az OK gombra.
20. Kattintson az OK gombra.
21. Írjon be egy értéket a Tárgy mezőbe.
22. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
