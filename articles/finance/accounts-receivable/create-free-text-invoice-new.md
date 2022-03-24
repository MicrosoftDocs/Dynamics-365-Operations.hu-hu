---
title: Szabadszöveges számla létrehozása
description: Ez a témakör bemutatja, hogyan lehet szabadszöveges számlákat létrehozni.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6e9578d9b2d61f241ab5e92fc9740b88b80969f6
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392885"
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
    * Be **lehet** **állítani** a szabadszöveges számla feladását, ha hiba történik a Kinnlevőségek paraméterei lap Frissítések lapján (**Kinnlevőségek > Kinnlevőségek > Kinnlevőségek paramétereinek beállítása).** Válassza **az Igen** **lehetőséget** a szabadszöveges számlák feladásának megállítása az első hibaparaméteren, ha hiba esetén leállítja a szabadszöveges számlák feladását. Ha kötegelt feladást ad fel, **a** hiba leállítja a feladást, és a köteg állapota Hiba lesz. Ha ez a beállítás nincs bejelölve, akkor a feladási folyamat kihagy egy feladási hibát jelzett számlát, és folytatja a további számlák feladását. Kötegelt feladás esetén a feladási hiba nem akadályozza meg a többi számla feladását. A köteg állapota Véget **ér**. A részletes feladási folyamat jelentés elérhető lesz ellenőrzésre a kötegelt feladatok előzményeiben.
    * Állítsa ezt az opciót **Igen** értékre a számla nyomtatásához.
    * Állítsa ezt az opciót **Igen** értékre a számla feladásához. Feladás nélkül is kinyomtathatja a számlát.

19. Válassza ki az **OK** lehetőséget.

## <a name="copy-lines"></a>Sorok másolása
A szabadszöveges számlán szereplő sorok másolásához kiválaszthat egy vagy több sort, majd válassza a **Kiválasztott sorok másolása** lehetőséget. Megadhatja a létrehozni kívánt másolatok számát, és a jegyzeteket és a mellékleteket is másolhatja. A felosztás másolhatók, vagy engedélyezheti újra létrehozásukat a könyveléskor.

A sorok másolása után módosíthatja az adatokat, szükség szerint.

## <a name="create-a-free-text-invoice-from-a-template"></a>Szabadszöveges számla sablonól létrehozása
Szabadszöveges számla sablonól létrehozása is lehetséges. Az **Új sablonból** kiválasztásakor a **Számla** lapon ki lehet választani a sablon nevét és az új szabadszöveges számlához kapcsolódó vevőszámlát. Alapértelmezett értékek, például a fizetési feltételek és a fizetési mód kitölthető a vevőtől, vagy a sablonnal mentett értékek is használhatók.

Ekkor létrejön a szabadszöveges számla, és igény szerint szerkesztheti az értékeket.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>A szabadszöveges számlákra vonatkozó munkafolyamat állapotának helyreállítása Helyreállíthatatlan állapotról Tervezet állapotra
A helyreállíthatatlan hiba miatt leállított munkafolyamat-példány **Helyreállíthatatlan** munkafolyamat-állapotot kap. Ha egy szabadszöveges **vevői** számla munkafolyamatának állapota nem állítható vissza, **·** **a** Munkafolyamat-műveletek visszahívása lehetőség választásával visszaállíthatja Vázlat állapotúra. Ezután szerkesztheti a vevői szabadszöveges számlát. Ez a funkció akkor használható, **·** **ha** a Szolgáltatáskezelési lapon be van kapcsolva a Szabadszöveges számlák munkafolyamat-állapotának visszaállítása Helyreállíthatatlan értékről Vázlat paraméterre.

A **Munkafolyamat-előzmények** oldal segítségével visszaállíthatja a munkafolyamat állapotát **Tervezet** értékre. Ezt a lapot a Szabadszöveges **számla** **vagy a Munkafolyamat > Lekérdezések > megnyithatja.** A munkafolyamat állapotának **Tervezet** értékre való visszaállításához válassza ki a **Visszahívás** lehetőséget. A munkafolyamat állapotát **Vázlat** **·** **·** **állapotra** is visszaállíthatja, ha a Szabadszöveges számla lapon vagy a Minden szabadszöveges számla lapon a Visszahívás műveletet válassza. Miután a munkafolyamat állapota visszaáll **a** Vázlat állapotra, elérhetővé válik szerkesztésre **a Szabadszöveges számla oldalon**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
