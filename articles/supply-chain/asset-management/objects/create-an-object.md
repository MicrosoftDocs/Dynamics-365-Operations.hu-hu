---
title: Eszköz létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni egy eszközt az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ab715be3bfdc380f5736fadd901af3ed78d7035
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016304"
---
# <a name="create-an-asset"></a>Eszköz létrehozása

[!include [banner](../../includes/banner.md)]

 

Ez a témakör azt ismerteti, hogyan lehet létrehozni egy eszközt az Eszközkezelésben.

1. Kattintson **az Eszközkezelés** > **– Összes** > **eszköz vagy az** **Aktív eszközök elemre**.
2. Kattintson az **Új** gombra.
3. Az **Eszközök létrehozása** párbeszédpanelen írja be az **Eszközre** vonatkozó adatokat (az eszközazonosítót) és az eszköz nevét. Az eszközhöz válaszon egy dátumot a **Hatályos** mezőben Ettől a dátumtól kezdve telepítheti az eszközt a munkavégzési helyszínre, valamint áthelyezheti és lecserélheti az eszközt egy eszközszerkezetben.
4. Az **Eszköztípus** mezőben válassza ki az eszköz eszköztípusát (kötelező mező). Ha szükséges, válassza az ki az **Eszköz gyártója** és **Eszközmodell** értékeket az eszközhöz. Ha csak egy termék van beállítva, akkor a termék automatikusan ki lesz választva az eszköz gyártójának az **Eszköz gyártója** mezőben. Az **Eszköz gyártója** és **Eszközmodell** mezőben elérhető választási lehetőségek az [Eszköz gyártói és modelljei](../setup-for-objects/product-and-model.md) mező beállításaitól függenek.
5. A **Fölérendelt tárgyieszköz** csoportban az **Eszköz** mező üres. Ha szükséges, kiválaszthat egy fölérendelt eszközt, majd a **Fölérendelt eszköz** csoport összes mezőjét automatikusan kitölti a program.
    >[!NOTE]  
    >A fölérendelt eszköz kiválasztásakor kettő vagy három lap érhető el: a **Saját eszközök** lap azokat a munkavégzési helyszínhez kapcsolódó eszközöket tartalmazza, amelyeket Ön (a rendszerre bejelentkezett karbantartó munkavállaló) eloszthat. Ha a karbantartási dolgozóknál nincs beállítva munkavégzési helyszín a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) képernyőn, akkor a **Saját eszközök** lap nem lesz látható. Az **Aktív eszközök** lap az „Aktív” eszköz-életciklus állapotú eszközök listáját tartalmazza. Az **Eszköznézet** lap a munkavégzési helyszínek és a helyszínekre telepített eszközök fanézetét jeleníti meg.

6. A beállított alapértelmezett munkavégzési helyszínt a rendszer **Tárgyieszközcsoport** > **Munkavégzési helyszín** mezőjében lévő eszközre vonatkozóan javasolja. Szükség esetén válasszon másik munkavégzési helyszínt.

    >[!NOTE]
    >Az eszköz létrehozását követően szükség esetén telepítheti azt egy másik munkavégzési helyszínre. Csak a felső szintű eszközök (aktuális szülőeszköz nélküli eszközök) telepíthetők a munkavégzési helyszínre. Ez azt jelenti, hogy a kijelölt munkavégzési helyszínre a felső színtű és a származtatott eszközöket is telepíti. További információ a tárgyi eszközök munkavégzési helyszínre történő telepítéséről: [A munkavégzési helyszínek bemutatása](../functional-locations/introduction-to-functional-locations.md).

7. Kattintson az **OK** gombra.
8. Válassza ki az eszközt az **Összes eszköz** listából, majd kattintson a **Szerkesztés** gombra, hogy további információkat adjon hozzá az eszközhöz.

## <a name="general-information"></a>Általános információk

Az a munkavégzési helyszín, ahová az eszköz kapcsolódik, a **Munkavégzési helyszín** mezőben látható. Ha az eszköz egy fölérendelt eszköz, akkor az eszközhöz kapcsolódó gyermekek száma a **Gyermekek** mezőben jelenik meg. Ha az eszköz egy meglévő eszköz aleszköze akkor a fölérendelt eszköz azonosítója a **Szülő** mezőben jelenik meg.

Az **Eszközök gyártója** és **Eszköz modellje** eszközzel kapcsolatos információkat szerkesztheti azon eszközre vonatkozóan, amely használható a cserealkatrészek alternatív cserealkatrészek és feladattípus alapértelmezések kezeléséhez. További tájékoztatás: [Eszköz gyártói és modelljei](../setup-for-objects/product-and-model.md). Szükség esetén a **Modellév** és **Sorozatszám** adatokat is megadhatja.

**Az aktuális életciklus-állapot** határozza meg, hogy az eszköz aktív vagy inaktív-e. Eszköz létrehozásakor az állapot mindig az eszközállapot-csoport első állapotára lesz állítva. Ha készen áll egy eszköz aktiválására, kattintson az **Eszköz állapotának frissítése** lehetőségre, és válassza ki azt az életciklus-állapotot, amelyet „eszközhöz aktívként” határozott meg, majd kattintson az **OK** gombra.

**Megjegyzés:** Ha egy eszköz "inaktív" értékűre van állítva, akkor már nem lehet munkarendeléseket létrehozni az eszközhöz. Inaktív eszközhöz nem ütemezhet megelőző karbantartási feladatokat.

A **Szolgáltatási szint** és **Kiritkusság** mezők az eszközhöz létrehozott munkarendelésekre vonatkoznak. A mezők a tárgyi eszköz aktuális beállításához számított **Szolgáltatási szint** és **Kritikusság** számértékeit jelenítik meg. Ezeknek az értékeknek a beállítása: [Eszköz szolgáltatásszintjei](../setup-for-objects/object-priorities.md) és [Eszközkritikusságok típusai](../setup-for-objects/object-criticalities.md).

## <a name="asset"></a>Eszköz

A tárgyi eszköz **Erőforrását** is ki lehet választani. Az erőforrás-kiválasztása határozza meg, hogy a munkarendelés-ütemezéshez melyik naptárat használja a program. A tárgyi eszközök esetében gyakran használják az erőforrás-beállítást. Az erőforrások és erőforráscsoportokat a **Szervezeti adminisztráció** > **Erőforrások** > **Erőforráscsoportok** vagy **Erőforrások** helyen állíthatja be.

A **Tárgyi eszköz száma** mezőben kiválaszthat egy tárgyi eszközt, amely az eszközhöz kapcsolódik. Erre akkor van szükség, ha az eszköz egy beruházási projekthez kapcsolódik.

- Ha az eszköz egy tárgyi eszközhöz kapcsolódik, akkor létrehozhat egy, a beruházási projekthez kapcsolódó munkarendelésekhez használatos munkarendelés típust. 
- A tárgyi eszközökre vonatkozó információk a **Tárgyi eszközök** modulhoz kapcsolódnak. a Dynamics 365 Supply Chain Management programban. Ez azt jelenti, hogy a **Tárgyi eszközök** > **Tárgyi eszközök** > **Tárgyi eszközök** helyen áttekintést kaphat az tárgyi eszközhoz kapcsolódó Eszközkezelési projektekről, ha kiválasztja a listából az eszközt, és megtekinti a tartalmat a **Kapcsolódó információk** ablaktábla > **Társított projektek** szakaszban.


## <a name="details"></a>Részletek

Az **Aktív állapot kezdete** mezőben az a dátum, amikor a tárgyi eszköz életciklusának állapotát egy aktív állapotra frissítette (lásd [Eszköz életciklus állapotai](../setup-for-objects/object-stages.md) az eszközök életciklusáak beállításával kapcsolatosan) látható. Ha az eszköz már nem aktív, és az eszköz életciklus-állapotát egy inaktív életciklus-állapotra frissítette, akkor az **Aktív állapot vége** mezőben látható az a dátum, amelytől kezdve az eszköz inaktív. Ha szükséges, ezek a dátumok manuálisan módosíthatók.

Ha szükséges, beszúrhat egy várt dátumot az eszköz helyettesítésére a **Helyettesítés dátuma** mezőben. A **Helyettesítő érték** mezőbe be lehet szúrni az eszköz helyettesítésére szolgáló becsült értéket. Példa: A helyettesítési információkkal összehasonlítja azt egy eszköz fenntartásának költségeivel, és döntést hozhat egy új eszköz megvásárlásáról, ha egy meglévő eszköz karbantartási költségei gyorsan növekednek.

## <a name="notes"></a>Megjegyzések

A **Megjegyzések** gyorslapon a tárgyi eszközhöz kapcsolódó megjegyzések is hozzáadhatók. Kattintson az **Időpecsét hozzáadása** gombra, mielőtt megírná a megjegyzést, ha szeretne felhasználói információkat és egy dátum-/időpecsétet is hozzáadni.

## <a name="attributes"></a>Attribútumok

Ezen a gyorslapon beállíthatja az eszközattribútumok értékeit. Ezekkel az attribútumokkal lehet leírni az eszközhöz tartozó tulajdonságokat és jellemzőket, például a méretet, a súlyt vagy a gépek konfigurációját.

Kattintson a **Sor hozzáadása** lehetőségre, és jelölje ki az attribútumtípust. Ezután szúrja be az attribútumtípushoz kapcsolódó **Értéket**, és mentse a rekordot.

>[!NOTE] 
>Áttekintést kaphat az eszközattribútumok típusairól, valamint azok kapcsolatáról az **Eszközattribútum** és **Eszközattribútum-áttekintés** eszközeivel. További információért tekintse meg az [Eszközattribútum áttekintése](../objects/object-specification-overview.md) című részt.

## <a name="vendor"></a>Szállító

A **Szállító** gyorslapon válassza ki az eszköz szállítói partnerét. Illetve, van szállítói garancia, akkor itt be lehet szúrni jótállási adatokat.

## <a name="address"></a>Cím

A **Cím** gyorslapon be lehet szúrni a berendezés címét. Ha az eszközhöz nincs megadva cím, akkor az eszköz a szülő eszköz címét használja, ha a szülő eszköznek van címe. Ha a tárgyi eszközhöz vagy a tárgyi eszközhöz tartozó bármely szülőhöz nem tartozik cím, akkor a munkavégzési helyszínnek az a címe használható, amelyre az eszköz telepítve van. Ha ez a munkavégzési helyszín nem rendelkezik kapcsolt címmel, akkor a program a szülő munkavégzési helyszín címét használja az eszközhöz.

## <a name="asset-management-plans"></a>Eszközkezelési tervek

A karbantartási tervek a megelőző karbantartási feladatok ütemezésére használhatók rendszeres időközönként a tárgyi eszközhöz. Ezen a gyorslapon a kiválasztott tárgyi eszközhöz beállíthatja a karbantartási terv sorait. A karbantartási köröket különböző eszközökhöz lehet beállítani, amelyekhez rendszeres időközönként hasonló feladatot kell végrehajtani. A **Funkcionális hely karbantartási tervei** lapon megtekintheti a munkavégzési helyszínhez kapcsolódó karbantartási terveket, amelyre az eszköz telepítve van.

>[!NOTE]
>Ha egy tárgyi eszközhöz kapcsolódó karbantartási terv sort vagy karbantartási kört töröl az **Összes eszköz** részben, akkor automatikusan törli a karbantartási terv vagy karbantartási kör alapján létrehozott összes "létrehozott" állapotú karbantartási ütemezést is.

## <a name="functional-location-maintenance-plans"></a>Munkavégzési helyszín karbantartási tervei

Ezen a gyorslapon megtekintheti a munkavégzési helyszínhez kapcsolódó karbantartási terveket, amelyre az eszköz telepítve van.

## <a name="maintenance-rounds"></a>Karbantartási körök

Ezen a gyorslapon a tárgyi eszközhöz kapcsolódó karbantartási köröket lehet hozzáadni és eltávolítani.

## <a name="financial-dimensions"></a>Pénzügyi dimenziók

Kiválaszthat pénzügyi dimenziókat is az eszközhöz.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]