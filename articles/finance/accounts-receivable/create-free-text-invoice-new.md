---
title: Szabadszöveges számla létrehozása
description: Ez a témakör bemutatja, hogyan lehet szabadszöveges számlákat létrehozni.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 726d4979059417871a00626c55da32fa4286cb53
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991117"
---
# <a name="create-a-free-text-invoice"></a>Szabadszöveges számla létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet szabadszöveges számlákat létrehozni. Ez az eljárás az **USMF** bemutatócéget használja.

## <a name="create-a-free-text-invoice"></a>Szabadszöveges számla létrehozása

1. Ugorjon a következőre: **Kinnlévőségek (vagy Értékesítési főkönyv) \> Számlák \> Kizárólag szabadszöveges számlák**.
2. Válassza az **Új** lehetőséget.
3. Válasszon egy értéket a **Vevői számla** mezőnek.

    * Alapértelmezett esetben a vevői számlához kiválasztott számla lesz pénzügyi adatnak használva
    * A könyvelési állapot **Folyamatban** állapottal kezdődik, ha a számla nincs feladva.
    * A számlaszám a számla feladásakor kerül hozzárendelésre.
    * SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program, ha a vevői számla lehetőséget választja.

4. A **Leírás** mezőben adjon meg egy értéket.
5. A **Fő számla** mezőben adja meg egy számlaszámot, amelynek nincsenek dimenziói. A dimenziók megadását az útmutató később ismerteti.

    Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számla megtalálásához.

6. Válassza ki a **Soradatok** gyorslapot hogy hozzáadhasson dimenziókat a fő számlához.
7. Válassza ki a **Pénzügyi dimenziók** lapot.

    * A dimenziók kizárólag a kijelölt sorra vonatkoznak.
    * Az áfacsoport a vevőtől származik. Ha a vevő nem rendelkezik áfacsoporttal, akkor a rendszer a fő számla áfacsoportját használja.
    * A cikkek áfacsoportja a fő számla alapján kerül megadásra. Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben meghatározott cikk áfacsoport használatos.

8. Opcionális: Adjon meg egy számot a **Mennyiség** mezőben.
9. Opcionális: Adjon meg egy számot az **Egységár** mezőben.

    Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra. Ugyanakkor felülírhatja a számítást, ha bevisz egy összeget.

10. Válassza az **Áfa** lehetőséget a számla számított áfájának megtekintéséhez.

    Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a **Kiigazítás** lapon.

11. Válassza ki az **OK** lehetőséget.
12. Válassza a **Költségek** lehetőséget, ha szeretne költségeket adni a számlához.
13. Írjon be értéket a **Költsgékód** mezőbe.
14. Adjon meg egy számot az **Költségek értéke** mezőben.
15. Zárja be a lapot.
16. Kattintson az **Összeg** lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.
17. Válassza **Bezárás** lehetőséget.
18. Adja fel a számlát a **Feladás** gombot választva. Tényleges feladás előtt még van lehetősége a visszavonásra.

    * A számla nyomtatásának időpontját megváltoztathatja. Válassza ki a **Jelenlegi** lehetőséget az egyes számlák frissítéskori kinyomtatásához. Válassza ki az **Után** lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.
    * Annak módosításához, hogy a vevő hitelkerete hogyan legyen ellenőrizve a számla feladása előtt, módosítsa az értéket a **Hitelkeret típusa** mezőben.
    * Állítsa ezt az opciót **Igen** értékre a számla nyomtatásához.
    * Állítsa ezt az opciót **Igen** értékre a számla feladásához. Feladás nélkül is kinyomtathatja a számlát.

19. Válassza ki az **OK** lehetőséget.

## <a name="copy-lines"></a>Sorok másolása
A szabadszöveges számlán szereplő sorok másolásához kiválaszthat egy vagy több sort, majd válassza a **Kiválasztott sorok másolása** lehetőséget. Megadhatja a létrehozni kívánt másolatok számát, és a jegyzeteket és a mellékleteket is másolhatja. A felosztás másolhatók, vagy engedélyezheti újra létrehozásukat a könyveléskor.

A sorok másolása után módosíthatja az adatokat, szükség szerint.

## <a name="create-a-free-text-invoice-from-a-template"></a>Szabadszöveges számla sablonól létrehozása
Szabadszöveges számla sablonól létrehozása is lehetséges. Az **Új sablonból** kiválasztásakor a **Számla** lapon ki lehet választani a sablon nevét és az új szabadszöveges számlához kapcsolódó vevőszámlát. Alapértelmezett értékek, például a fizetési feltételek és a fizetési mód kitölthető a vevőtől, vagy a sablonnal mentett értékek is használhatók.

Ekkor létrejön a szabadszöveges számla, és igény szerint szerkesztheti az értékeket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]