---
title: Termékszerkezetek kiadása
description: Ez a témakör azt mutatja be, hogyan lehet a teljes termékszerkezeteket a termékekkel és azok mérnöki verzióikkal együtt kiadni. Így biztosíthatja, hogy a mérnökileg releváns termékadatokat könnyen újra fel lehessen használni a különböző jogi személyekben.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e9cd90d74b92754d4a5432485d5dd59c31e34c61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841985"
---
# <a name="release-product-structures"></a>Termékszerkezetek kiadása

[!include [banner](../includes/banner.md)]

Annak biztosítására, hogy a mérnökileg releváns termékadatok könnyen felhasználhatók legyenek a különböző jogi személyekben, a termékeket a mérnöki verziókkal együtt kell kiadni. Ebből következően a többszintű anyagjegyzék-szerkezeteket (BOM) a szülővel együtt, egyetlen kiadási műveletben kell kiadnia. Ebben az esetben az ANYAGJEGYZÉK és az alacsonyabb szintű termékek is kiadásra kerülnek.

A mérnöki termékeket úgy kell létrehozni és karbantartani, hogy az általuk tervezett minőségi követelményeknek megfeleljenek. A termékeket előállító valamennyi operatív vállalatnak ugyanarra a termékre és mögöttes ANYAGJEGYZÉKRE van szüksége. A gyártólétesítménytől függően előfordulhat, hogy az útvonalat helyileg is létre lehet hozni. Ebben az esetben a termékkel együtt nem fog kiadni útvonalat. Az olyan jogi személyeknél, akik termékeket értékesítenek, de nem gyártják őket, előfordulhat, hogy az ANYAGJEGYZÉK nem kötelező.

A folyamat hatékonyabbá tételéhez az összes mérnökileg releváns adat kiadható a többi operatív vállalat számára egy időben. Ezek az adatok tartalmazzák a termékszerkezetet. A kiadási folyamat során kiválaszthatja, hogy a termék adatainak mely részét kell kiadni.

A mérnöki vállalatokkal és az operatív vállalatokkal kapcsolatos további tudnivalókat lásd a [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md).

Ne felejtse el, hogy szabványos termékeket és mérnöki termékeket is kibocsáthat a kiadási termékszerkezettel együtt. A folyamat során a program kiadja a teljes termékszerkezetet, még azt az ANYAGJEGYZÉKET és útvonalat is, amelyben kiadják a termékeket.

A termék kiadásával kapcsolatos példát a következő témakörben talál: [Mérnöki termék kiadása egy helyi vállalatnak](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>A termék kiadott adatai, amikor a kiadási termék szerkezetét használják

A következő adatok szerepelnek a mérnöki termékek kiadásában:

- **Termékadatok** – Új kiadott termék jön létre.
- **Mérnöki verzió adatai** – A mérnöki verzió és az adatok létrehozása vagy frissítése. Ne feledje, hogy ha ugyanazt a mérnöki verziót adja ki egy operatív vállalathoz, akkor a mérnöki adatok felül lesznek írva.
- **Mérnöki attribútumok** – A mérnöki attribútumok és értékeik létrehozása vagy frissítése.
- **Mérnöki anyagjegyzék** – A mérnöki anyagjegyzék és annak sorainak létrehozása vagy frissítése. Az adatok tulajdonjogával kapcsolatos további tudnivalókat lásd a [Terméktulajdonosok](product-owner.md) részben.
- **Mérnöki útvonalak** – A mérnöki útvonalak és műveletek létrehozhatók vagy frissíthetők. Az adatok tulajdonjogával kapcsolatos további tudnivalókat lásd a [Terméktulajdonosok](product-owner.md) részben.
- **Mérnöki dokumentumok** – A mérnöki verzióhoz kapcsolódó mérnöki dokumentumok létrehozása vagy frissítése.

Amikor bekapcsolja a mérnöki változtatáskezelést a rendszerben, elérhetővé válik a kiadási termék szerkezete. Ezenkívül a szabványos termékek a kiadáskor tartalmazzák az ANYAGJEGYZÉKEKET és az útvonalakat is.

## <a name="product-acceptance"></a>Termék elfogadása

**A termék elfogadása** kulcsfontosságú paraméter, amely befolyásolja a kiadási folyamatot. Ezt a paramétert minden vállalatnál beállíthatja úgy, hogy a **Mérnöki változtatások kezelése \> Beállítás \> Mérnöki változtatások kezelési paraméterei** részbe lép. További tájékoztatást a [Mérnöki változtatások kezelési paraméterei](engineering-parameters.md) részben talál.

### <a name="automatic-product-acceptance"></a>Automatikus termékelfogadás

A mérnöki termékek mindegyik kiadása akkor indul el, amikor a mérnöki vállalatból valaki kiválasztja a kiadási terméket. Ha a **Termékelfogadás** paraméter *Automatikus* értékre van állítva, akkor a mérnöki vállalatnál a felhasználó dönti el, hogy melyik termék adatait kell automatikusan kiadni az operatív vállalatoknak. A termék automatikusan ki lesz adva a kiadás varázslóban kiválasztott vállalatoknak.

### <a name="manual-product-acceptance"></a>Manuális termékelfogadás

A mérnöki termékek mindegyik kiadása akkor indul el, amikor a mérnöki vállalatból valaki kiválasztja a kiadási terméket. Ha a **Termékelfogadás** paraméter *Manuális* értékre van állítva, akkor a mérnöki vállalatnál a felhasználó dönti el, hogy melyik termék adatait kell kiadni az operatív vállalatoknak. Ezután az egyes operatív vállalatok felhasználói áttekintik a termék adatait, és eldönti, hogy elfogadja-e a kiadást. Az operatív vállalatnál a felhasználó a következő beállításokat állíthatja be az adatok beérkezésekor:

- Ha a termék (frissítések) nem relevánsak az operatív vállalatnál, akkor a felhasználó dönthet úgy, hogy nem fogadja el a kiadást.
- A felhasználó módosíthatja az új termékekhez tartozó cikksablont.
- A felhasználó megadhatja, hogy a terméket ki kell-e adni az anyagjegyzékekkel és/vagy útvonalakkal együtt, illetve hogy a jóváhagyottként vagy aktívként kell-e kiadni őket.
- A felhasználó módosíthatja a termékek érvényességének kezdő dátumát.

A termék elfogadásával kapcsolatos példát a következő témakörben találja: [A termék áttekintése és elfogadása a helyi vállalatban történő kiadás előtt](engineering-scenarios.md#accept).

> [!NOTE]
> A szabványos termékek esetében bármilyen jogi személy bármilyen másik jogi személynek kiadhatja. A mérnöki termékek esetében a mérnöki vállalat az egyetlen jogi személy, akitől kiadhat.

## <a name="release-policies"></a>Kiadási irányelvek

Nem minden operatív vállalatnak van szüksége ugyanarra a termékadatokra. Általában a mérnöki termékeket előállító operatív vállalatok ANYAGJEGYZÉKET igényelnek, míg a mérnöki termékeket csak forgalmazó vállalatok nem igényelnek ANYAGJEGYZÉKET. A kiadási irányelvek segítségével lehet létrehozni a termékek kiadásához használt paramétereket.

A mérnöki termékkategóriákkal kapcsolatos további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

A kiadási folyamat során befolyásolhatja a beállításokat.

## <a name="create-and-manage-product-release-policies"></a>A termék kiadási irányelveinek létrehozása és kezelése

A termék kiadási irányelveivel való munkavégzéshez menjen a **Mérnöki változtatások kezelése \> Beállítás \> termékkiadási irányelvek** lehetőségre. Majd tegye a következők egyikét.

- Új irányelv létrehozásához válassza az **Új** lehetőséget a Művelet ablakon, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő irányelv szerkesztéséhez jelölje ki azt a listaablaktáblán, válassza a Művelet ablak **Szerkesztés** parancsát, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő irányelv törléséhez jelölje ki a listaablaktáblán, válassza a **Szerkesztés** parancsot a Művelet ablaktáblán, majd győződjön meg arról, hogy az **Általános** gyorslapon az **Aktív** beállítás *Nem* értékre van állítva. A Műveletpanelen válassza ezután a **Törlés** elemet.

### <a name="header"></a>Fejléc

Állítsa be a következő mezőket egy termék kiadási irányelv fejlécében.

| Mező | Leírás |
|---|---|
| Név | Adja meg az irányelv nevét. |
| Leírás | Adja meg az irányelv leírását. |

### <a name="general-fasttab"></a>Általános gyorslap

Állítsa be a következő mezőket egy termék kiadási irányelv **Általános** gyorslapján.

| Mező | Leírás |
|---|---|
| Terméktípus | Válassza ki, hogy az irányelv a *Cikk* vagy a *Szolgáltatás* típusának termékeit érinti-e. A rekord mentése után a beállítás nem módosítható. |
| Sablonok alkalmazása | Válassza ki a következő lehetőségek egyikét, és adja meg, hogy a kiadási sablonokat milyen módon kell alkalmazni az irányelv használatakor:<ul><li>**Mindig** – A sablon kiadott terméket mindig kiadásokhoz kell használni. Ha ezt a lehetőséget választja, akkor a **Minden termék** gyorslap segítségével megadhatja az egyes vállalatokhoz használt sablont. Ha a **Minden termék** gyorslapon felsorolt vállalatok esetében nem ad meg sablont, akkor hibaüzenet jelenik meg az irányelv mentésekor.</li><li>**Nem kötelező** – Ha egy sablonban kiadott termék van megadva egy olyan vállalathoz, amely a **Minden termék** gyorslapon szerepel, akkor a program a vállalatnak történő kiadáskor fogja használni a sablont. Ellenkező esetben a program nem használ sablont. Ha ezt a lehetőséget választja, akkor mentheti az irányelvet, anélkül, hogy sablonokat rendelne minden vállalathoz. (Figyelmeztetés nem fog megjelenni.)</li><li>**Soha** – Semmilyen sablon kiadott terméket nem fognak használni a vállalatokhoz, amelyeknek kiad, még akkor sem, ha a sablon meg van adva a **Minden termék** gyorslapon. A sablon oszlopai nem lesznek elérhetők.</li></ul> |
| Aktív | Ezzel a beállítással lehet karbantartani a kiadási irányelveket. Az összes használt kiadási irányelv esetében állítsa *Igen* értékre. *Nem* értékre állításával inaktívként jelölheti meg a kiadási irányelvet, ha nincsen használatban. Ne feledje, hogy nem lehet inaktiválni egy mérnöki termékkategória számára hozzárendelt kiadási irányelvet, és csak az inaktív kiadási irányelveket lehet törölni. |

### <a name="all-products-fasttab"></a>Minden termék gyorslapja

A **Minden termék** gyorslapon adjon hozzá egy sort minden olyan operatív vállalathoz, amelyhez ezt az irányelvet szeretné használni a kiadáshoz. A **Minden termék** gyorslap gombjaival lehet a szükséges sorokat hozzáadni és eltávolítani. Minden egyes hozzáadott sorhoz állítsa be a következő mezőket.

> [!NOTE]
> A **Minden termék** gyorslap beállításai mind a mérnöki termékre, mind a szabványos termékekre érvényesek.

| Mező | Leírás |
|---|---|
| Vállalati számlák azonosítója | Válassza ki azt a vállalatot, amelyre a sor vonatkozik. A sor paraméterei akkor lesznek érvényesek, ha a termékeket a vállalatnak adták ki. |
| Kiadott termék sablonja | Sablon megadása a termékhez. |
| Anyagjegyzék-jóváhagyás másolása | Jelölje be ezt a jelölőnégyzetet, ha az ANYAGJEGYZÉK-JÓVÁHAGYÁS állapotát át szeretné másolni a fogadó vállalatnak. |
| Darabjegyzék-aktiválás másolása | Jelölje be ezt a jelölőnégyzetet, ha az ANYAGJEGYZÉK-AKTIVÁCIÓ állapotát át szeretné másolni a fogadó vállalatnak. |
| Útvonal-jóváhagyás másolása | Jelölje be ezt a jelölőnégyzetet, ha az útvonaljóváhagyás állapotát át szeretné másolni a fogadó vállalatnak.|
| Az útvonal-aktiváció másolása | Jelölje be ezt a jelölőnégyzetet, ha az útvonalaktiválás állapotát át szeretné másolni a fogadó vállalatnak. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Beállítási paraméterek a mérnöki termékek gyorslaphoz

Minden alkalommal, amikor egy sort ad hozzá a **Minden termék** gyorslaphoz, a **Vállalati számlák azonosítója** érték is létrejön a **Beállítási paraméterek a mérnöki termékek** gyorslapon. Majd amikor egy sort ad eltávolít a **Minden termék** gyorslapról, a **Vállalati számlák azonosítója** érték is el lesz távolítva a **Beállítási paraméterek a mérnöki termékek** gyorslapról.

A **Beállítási paraméterek a mérnöki termékek** gyorslaphoz a következő mezőket kell megadnia.

> [!NOTE]
> A **Beállítási paraméterek a mérnöki termékek** gyorslap csak a mérnöki termékekre vonatkozik.

| Mező | Leírás |
|---|---|
| Sablonanyagjegyzék | Ha egy ANYAGJEGYZÉKET tartalmazó termék ki van adva, akkor a program a megadott sablon ANYAGJEGYZÉK sorait adja hozzá. Ez a mező a helyi összetevők, például a csomagolás vagy a helyi nyelvű utasítások hozzáadására használható. |
| Sablon útvonala | Ha egy útvonalat tartalmazó termék ki van adva, akkor a program a megadott sablont hozzáadja. |
| Másolás érvényessége | Válassza ki, hogy a termékek kiadásakor be kell-e másolni az érvényesség dátumait a mérnöki vállalatból az operatív vállalatba. |
| Automatikus hozzáadás a kiadási javaslathoz | Azokhoz a termékekhez jelölje be ezt a jelölőnégyzetet, amelyeket automatikusan ki kell adni a mérnöki módosítási rendelésen. Így az ezt a kiadási irányelvet használó mérnöki termékkategóriák automatikusan kiadhatóak azon vállalatoknak, amelyeknél ez a beállítás van kiválasztva. (További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.)

### <a name="review-each-product-when-you-release-it"></a>Minden terméket ellenőrizzen a kiadáskor

Amikor az ANYAGJEGYZÉKEKET vagy útvonalakat tartalmazó mérnöki termékeket kiadják, a paraméterek az alapértelmezett értékre lesznek állítva, a kiadási irányelvben foglaltaknak megfelelően. Felhasználóként a kiadási termék szerkezete alapján befolyásolhatja ezt a viselkedést a kiadási oldalon.

A mérnöki termékek kiadásához jelölje ki a kiadni kívánt termékeket a **Kiadott termékek** lapon, majd válassza ki a **Kiadási termék szerkezete** lehetőséget a kiadási varázsló megnyitásához. A **Mérnöki termékek kiválasztása kiadásra** oldalon találja a termékeket. Válasszon ki egy terméket, majd válassza ki a **Kiadási részletek** lehetőséget a termék kiadási részleteinek áttekintéséhez.

A **Kiiadási részletek** oldalon módosíthatja a **Fogadó AJ**, az **Anyagjegyzék-jóváhagyás másolása**, az **Anyagjegyzék-aktiválás másolása**, az **Anyagjegyzék fogadása**, az **Útvonaljóváhagyás másolása** és az **Útvonalaktiválás másolása** mezők értékét. A push-pull forgatókönyvben a fogadó oldalon ugyanazokat a mezőket lehet módosítani, feltéve, hogy az ANYAGJEGYZÉK és az útvonal ki van adva.

## <a name="product-owners-and-product-releases"></a>A termék tulajdonosai és a termék kiadásai

Mivel a termék tulajdonosai tudják, hogy mely jogi személyeknek van szüksége a termékekre, a termékeket csak a terméktulajdonos csoportj tagjai adhatják ki. Más felhasználók nem adhatnak ki olyan termékeket, amelyeknek nem ők a tulajdonosai.

Ez a viselkedés csak akkor érvényes, ha a termék közvetlenül van kiválasztva kiadásra. Azok a termékek, amelyek egy ANYAGJEGYZÉKEN keresztül egy másik termék szerkezetében szerepelnek *kiadhatók* a nem tulajdonos felhasználók által is a szülő termék kiadásakor, feltéve, hogy a szülő termék az ő tulajdonuk.

Az X termék például a *Design kabinetek* terméktulajdonosi csoportjához vannak hozzárendelve. Az X termék az Y termék AJ része is, amely a *Design hangszórók* terméktulajdonosi csoportjához van hozzárendelve. Ha egy felhasználó a *Design hangszórók* terméktulajdonosi csoporttól kiadja az Y terméket és annak anyagjegyzékét, akkor az X termék az Y termékkel együtt fog megjelenni.

További információ: [Terméktulajdonosok](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
