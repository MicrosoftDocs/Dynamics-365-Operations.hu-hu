---
title: Készletfeladási profilok
description: Ez a témakör áttekintést nyújt a készletfeladási profilokról.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28e3a3051978f921e01a929496e96909e6c32429
ms.sourcegitcommit: 00b39900d3cbdbc9ca1ab3145265007f5dc98a3f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2022
ms.locfileid: "8806386"
---
# <a name="inventory-posting-profiles"></a>Készletfeladási profilok

[!include [banner](../includes/banner.md)]

A készletfeladási profilok a készletaggetlen tranzakciók főkönyvbe való feladását szabályják. A készletacél-tranzakciók több **modulból is generálhatók, például az Értékesítés és marketing**, a **Beszerzés és forrás**, **a Gyártásvezérlés** stb. modulból. A készletaggetlen tranzakciók akkor is feladhatóak, amikor egy cikket értékesítési vagy beszerzési rendelésben használnak fel. 

További készletaggodri tranzakció feladása lehetséges:
- Dokumentum minden egyes frissítésekor.
- Értékesítési rendelés csomagjegyzékének vagy számlájának feladásakor.
- Amikor termékbevételezés vagy számla jön létre a beszerzési rendeléshez.

A további tudnivalókat a Készlet ajkára vonatkozó tranzakcióknál lehet megszanálni.

## <a name="inventory-transaction-overview"></a>Készlettranzakció áttekintése

Minden egyes készletatípus-tranzakció a következő elemeket tartalmazza:
 - Mennyiség 
 - Ár 
 - Webhely 
 - Raktár 
 - Helyszín 

A készletalagos tranzakciók két bejegyzést hoznak létre a főkönyvben a tényleges és a pénzügyi feladás során. További tájékoztatás a Fizikai és [pénzügyi frissítéseknél található](/supply-chain/cost-management/physical-financial-updates.md).
A következő példa egy háromsoros beszerzési rendelés. Ebben a példában tegyük fel, hogy a teljes rendelés egyetlen telephelyre és raktárra vonatkozik. Minden beszerzésirendelés-sorhoz egyetlen kapcsolódó InventTrans rekord – más néven készlettranzakció – kapcsolódik, és minden sor 10 mennyiségű. A következő ábra bemutatja egy beszerzési rendelés fejlécének és három beszerzésirendelés-sornak a viszonyát, mindegyik egy InventTrans rekordhoz.

![Három sort és egy InventTrans rekordot kapcsolati diagram egy beszerzési rendeléshez.](./media/InventTransRelationship.PNG)

Az első beszerzésirendelés-sorhoz 5 mennyiség érkezik. A második sor teljes mennyisége, a beszerzési rendelés harmadik sorában nem bevételelt mennyiség. Ezzel egy másik készlettranzakció is kapcsolódik az első beszerzésirendelés-sorhoz. A második beszerzésirendelés-sor **tranzakciója** Beérkezettre módosul, és a harmadik tranzakció változatlan marad. A következő ábra bemutatja a kapcsolatot az 1. beszerzésirendelés-sor további InventTrans rekordja között.

![Háromsoros beszerzési rendelés kapcsolati diagramja. Egy sor részlegesen beérkezett, és két InventTrans rekordot mutat.](./media/InventTransRelationshipPartialReceipt.PNG)

Ebben a példában egy bizonylat lesz feladva a főkönyvbe; ez a tényleges bizonylat. A cikkmodellcsoport úgy van beállítva, hogy tényleges készletet ad fel, és minden cikk ugyanazt a cikkmodellcsoportot használja. A készletfeladási profil egyetlen fő számlát használ. Egyetlen bizonylat jön létre, és az InventTrans rekord összekapcsolja az InventTrans 1-et és az InventTrans 2-t ugyanannak a bizonylatnak.

Ezután a program az 1. és a 2. sorban kapott mennyiségről számlát kap. A főkönyvben létrejön egy másik bizonylat; ez a pénzügyi bizonylat. A cikkmodellcsoport úgy van beállítva, hogy pénzügyi készletet adjanak fel. Az új második bizonylat az InventTrans 1 és az InventTrans 2 értékhez kapcsolódik.

A költségszámítási modelltől függően előfordulhat, hogy létezik egy harmadik főkönyvi feladás a készlet aggtártranzakcióihoz, amelyek a készlet lezárásával és kiegyenlítésével kapcsolatosak. További tájékoztatás: Készletzárás [...](/supply-chain/cost-management/inventory-close.md). Az összes készlettranzakció **részletes** > **adatait a Készletkezelés – Lekérdezések és jelentések – lekérdezések és jelentések által lehet** > **megtekinteni**.

>[!Important]
> A készlettranzakciókat felosztja a rendszer a készletdimenziók minden egyedi kombinációjához és minden egyes részleges frissítéshez. Ez a részleges módosításokra vonatkozó előző példában látható.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Készlet felosztása készletdimenzió alapján – példa

A példában a 3. beszerzésirendelés-sor egy szerializált cikk. A bevételi folyamat során tíz sorozatszám van regisztrálva a beszerzési rendeléshez. A készlettranzakció 10 készlettranzakcióra lesz felosztva. A következő ábra bemutatja a 3. beszerzésirendelés-sorhoz kapcsolódó, saját sorozatszámmal összefüggő viszonyt és további készlettranzakciókat.

![Háromsoros beszerzési rendelés kapcsolati diagramja. Egy sor szerializálódik, és további InventTrans rekordokat mutat.](./media/InventTransRelationshipSerialNumber.PNG)

A fenti példában ha minden sorozatszám egyetlen termékbevételezésen érkezik, akkor egy további bizonylat jön létre. A fizikai bizonylat mező minden sorozatszámhoz csatolva lesz. Ugyanez igaz a beszerzési rendelés számlázásakor a pénzügyi frissítésre is.

## <a name="inventory-transactions"></a>Készlettranzakciók

A készlettranzakciókat a Készlettranzakciók **lapon** lehet megtekinteni a Készlet **- és raktárkezelés vagy** a **Költséggazdálkodás alatt**. Egy adott **forrásdokumentumsorhoz** – például beszerzésirendelés-sorhoz vagy értékesítésirendelés-sorhoz – kapcsolódó készlettranzakciókat is meg lehet tekinteni a Készlet lehetőség kiválasztásával, majd a Tranzakciók **lehetőség választásával**. 

A **Készlettranzakciók** lap a következő mezőket tartalmazza.

| Mező            | Leírás                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Cikkszám      | A tranzakcióhoz kapcsolódó cikkszám.                                                                  |
| Tényleges dátum    | Az a dátum, amikor a készlet megérkezik a raktárba, elhagyja a raktárt, felhasználják a termelésben, vagy legyártásra kerül. Például a feladási dátum
Az értékesítési rendeléshez vagy a beszerzési rendelés termékbevételezésének feladására vonatkozó csomagjegyzék-feladás.                             |
| Pénzügyi dátum   | Az a dátum, amikor a készlettranzakciót lezárják, és a költséget rögzítik a főkönyvben. Például a számlára könyvelt feladási dátum 
Generálása értékesítési vagy beszerzési rendeléshez. A pénzügyi dátum kitöltve van, és a hivatkozási dokumentum frissítése nem engedélyezett. |
| Hivatkozás        | A tranzakció forrását **és a Szám mezőben megjelenített dokumentum típusát** jelzi. Például értékesítési rendelés, beszerzési rendelés vagy át rendelés bevételezése.                                                 |
| Szám           | A tranzakció hivatkozási azonosítójának jelzése. Ha például a **Hivatkozás** mező értékesítési rendelést jelez, **a Szám** mezőben az értékesítési rendelés száma is adhatja meg.                                                       |
| Bevételezés (állapot) | Bevételezés típusú készlettranzakciók esetén ez a mező jelzi a bevételezés állapotát. Például a beszerzési rendelés bevételezés, és az állapot Megrendelve **vagy** Megrendelve **lehet**.                                                            |
| Kiadás (állapot)   | A kiadással kapcsolatos készlettranzakciók esetében ez a mező jelzi a kiadás állapotát. Például az értékesítési rendelés kiadás, **·** **és az állapot Megrendelt vagy Eladva lehet.**                         |
| Mennyiség         | A készlettranzakció mennyisége. A pozitív számok a készletre való bevételezéskor, míg a negatív számok a készletből való bevételezésre használhatók.                                                                                                                          |
| Egység             | A mennyiség kifejezésére vonatkozó mértékegység.                                                                                   |
| Tényleges súly szerinti mennyiség      | A tranzakció tényleges súlyának mennyisége. További tájékoztatás a cikkekkel [kapcsolatban tartalmaz további tájékoztatást](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Tényleges súly egysége          | A tényleges súly mértékegysége, amely a tényleges súly mennyiségét kifejezi.                                                         |
| Költség összege      | A készlettranzakció végleges költsége. Ezt a mezőt a tranzakció pénzügyi frissítése esetén tölti ki a rendszer. A költségszámítási módszertantól függően előfordulhat, hogy a készletzárási és -korrekciós folyamat frissíti ezt a mezőt.                            |

## <a name="inventory-status"></a>Készlet állapota

Mindegyik készlettranzakció állapota **vagy** **a Bevételezés, vagy a Kiadás mezőben látható.** A használt mező a készlettranzakciók típusától függ. A bevételezések olyan tranzakciók, amelyek növelik a készletet. Például egy pozitív mennyiséget vagy egy értékesítési rendelés visszáruját negatív mennyiséggel. A problémák olyan készlettranzakciók, amelyek csökkentették a készletet. Például egy pozitív mennyiséget vagy egy beszerzési rendelés visszáruját negatív mennyiséggel.

### <a name="receipt-status"></a>Bevételezés állapota

A következő táblázat a Bevételezés állapotot **írja** le.

| **Bevételezés állapota** | **Leírás**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Megrendelve            | Minden bevételezést képviselő készlettranzakció kezdeti állapota. Ebbe beletartoznak a pozitív mennyiséget tartalmazó beszerzési rendelések, a termelési rendelések vagy az értékesítési rendelések negatív mennyiséget tartalmazó beszerzési rendelések is.                                                   |
| Regisztrálva         | Ez az állapot akkor használatos, amikor egy két lépésből áll a bevételi folyamat, vagy amikor a cikk érkezése jelzi, hogy a termék megérkezett. Akkor használja a program, amikor a köteg- vagy sorozatszámok ki vannak osztva, vagy regisztrálva vannak a rendelésre. A cikkérkezésről az Érkezés áttekintésében olvashat [bővebben](/supply-chain/inventory/arrival-overview.md). |
| Bevételezve           | Ezt az állapotot a tranzakció fizikai frissítése esetén használja a rendszer. Beszerzési rendelés esetén a termékbevételezés feladása történik. Értékesítési rendelés visszáruja csak akkor történik meg, ha fel van adva a csomagjegyzék.                                                                            |
| Megvásárolva          | Ezt az állapotot használja a rendszer a tranzakció pénzügyi frissítése során. Beszerzési rendelés vagy értékesítési rendelés visszáruja esetén a számla generálása történik.                                                                                             |

### <a name="issue-status"></a>Kiadás állapota

A következő táblázat leírja a kiadás **állapotát**.

| **Kiadás állapota**  | **Leírás**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Megrendelt          | Bármely kiadást képviselő készlettranzakciók kezdeti állapota. Ebbe beletartoznak a pozitív mennyiséget tartalmazó értékesítési rendelések, a termelési rendelések anyagjegyzék- vagy receptúrasorai, illetve negatív mennyiséggel visszahozott beszerzési rendelések.                                             |
| Foglalt rendelt  | Ez a készletállapot azt jelzi, hogy a készlet foglalása egy már létrehozott, de a készletben ténylegesen még nem beérkezett rendeléshez van fenntartva. A készlet beérkezett állapota automatikusan Foglalt **tényleges állapotra frissül**. További tájékoztatás a foglalásokkal kapcsolatban: Készletmennyiségek [foglalása](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Foglalt tényleges | Ez az állapot azt jelzi, hogy a készlet fel van osztva vagy le van foglalva egy adott rendeléshez. A készlet foglalt példánya nem érhető el ténylegesen más rendelésekhez.                                 |
| Kitárolva         | Ez azt jelzi, hogy a készletet a raktárból választották ki. A készlet fizikailag még mindig a raktárban van, nincs eltávolítva, de más rendeléseknél nem érhető el.  |
| Kiszállított          | Ezt az állapotot a tranzakció fizikai frissítése esetén használja a rendszer. Értékesítési rendelésre vonatkozó beállítások a csomagjegyzék feladott időpontjai; – a beszerzési rendelés visszáruja esetén, ez akkor történik, amikor a termékbevételezés fel van adva.                                                                      |
| Eladva              | Ez az az állapot, amely a tranzakció pénzügyi frissítése során használatos. Beszerzési rendelés vagy értékesítési rendelés esetén ez történik a számla generálása esetén.|

A készlettranzakciókról a Készlettranzakciók [részletei oldalon található további tájékoztatás](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Készletfeladási profil konfigurálása

A készletfeladási profilok konfigurálása a következő lépésekkel lehet:

1.  Készletkezelés-beállítás **feladási** > **·** > **feladásának** > **megnyitása**
2.  Válassza ki a tranzakciótípus lapját. Válassza például a Beszerzési **rendelés lehetőséget**.
3.  Jelölje ki a feladási típus választógombját. Válassza ki például a kiadás **beszerzési kiadását**.
4.  Válassza az **Új** lehetőséget.
5.  A Cikkkód mezőben válasszon egy **táblára**, csoportra **,** mindre **vagy** kategóriára vonatkozó **beállítást**.**·** Ha például egy adott cikkcsoport feladási profilját is beállítja, válassza a Csoport **lehetőséget**.
     - Ha az **5**. lépésben a Táblát választotta, **a Cikkkapcsolat mezőben válassza ki a feladási profilhoz a cikkszámot**.
     - Ha az **5**. lépésben a Csoport lehetőséget választotta, **·** **akkor a Cikk-kapcsolat mezőben válassza ki a feladási profil cikkcsoportját**.
     - Ha az **5**. lépésben a Mind beállítást választotta, a Cikk-kapcsolat **mező** üresen marad.
     - Ha az 5. lépésben a **Kategóriát** választotta, a Cikk-kapcsolat **mező** üresen marad. A Kategóriakapcsolat **mező** segítségével válassza ki azt a kategóriát, amelybe a feladási profil vonatkozik.

6.  A Számlakód mezőben válasszon egy **táblára**, **csoportra vagy** mindre vonatkozó **beállítást**.**·** Ha például a feladási profilt az összes szállítóra alkalmazni, válassza az Összes **lehetőséget**.
     - Ha az **5**. lépésben a Táblát választotta, **a Számlakapcsolat mezőben válassza ki a feladási profilhoz a konkrét szállítószámot**.
     - Ha az **5**. lépésben a Csoport lehetőséget választotta, **a Számlakapcsolat mezőben válassza ki a feladási profilhoz kapcsolódó szállítócsoportot**.
     - Ha az **5**. lépésben a Mind beállítást választotta, **a Számlakapcsolat** mező üresen marad.

7.  Ha egy olyan áfacsoportot kell társítani, amelybe a feladási típus van bejelölve, akkor válasszon egy **áfacsoportot**. Ha a mező üres, a feladási típus az összes meglévő adócsoportra vonatkozik. Az adócsoportokhoz megadott feladás csak értékesítési és beszerzési tranzakciókra vonatkozik.
8.  Adja meg a számlatípusnak a **Fő számla mezőbe való feladott számlaszámát**. Ha nincs létrehozva számlaszám könyvelési típusként való használatra, létrehozhat egy új számlát. Új számlát a Főkönyv modul **Fő számla részletei** lapján hozhat létre.

## <a name="additional-resources"></a>További erőforrások

A készletfeladási profil **oldalának** minden lapja kapcsolatban van a következőben található aggtárgátorokkal:Dynamics 365 Supply Chain Management További tájékoztatás:
-   [Értékesítési rendelés feladása](sales-order-posting.md)
-   [Beszerzési rendelés feladása](purchase-order-posting.md)
-   [Készlet feladása](inventory-posting.md)
-   [Gyártásvezérlés feladása](production-posting.md)
-   [Elszámoló költségeltérés feladása](standard-cost-variance-posting.md)
