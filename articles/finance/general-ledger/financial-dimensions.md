---
title: Pénzügyi dimenziók
description: Ez a témakör ismerteti a különböző típusú pénzügyi dimenziókat és azok beállítását.
author: aprilolson
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: adfa2c1164550e32b07da25de0d96aa82430b980
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799626"
---
# <a name="financial-dimensions"></a>Pénzügyi dimenziók

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a pénzügyi dimenziók különböző típusait és a dimenziók beállításának a típusát.

Használja a **Pénzügyi dimenziók** oldalt pénzügyi dimenziók létrehozásához, melyeket számlaszegmensként használhat számlatükrökhöz. Kétféle pénzügyi dimenzió van: egyéni és entitás által támogatott dimenzió. Az egyéni dimenziók jogi entitások között oszlanak meg, és az értékeket a felhasználók adják meg és tartják karban. Az entitás által támogatott dimenziók értéke a rendszerben máshol van meghatározva, például a Vevők vagy Üzletek entitásoknál. Néhány entitás által támogatott dimenzió megoszlik a jogi személyek között, míg néhány más entitás által támogatott dimenzió vállalatspecifikus.

A pénzügyi dimenziók létrehozása után használja a **Pénzügyi dimenzióértékek** oldalt, és rendeljen hozzá további tulajdonságokat az egyes pénzügyi dimenziókhoz.

A pénzügyi dimenziók segítségével jogi személyek képezhetők le. Nem kell létrehoznia a jogi személyeket a Dynamics 365 Pénzügyben. Ugyanakkor a pénzügyi dimenziókat nem a jogi személyek üzemi vagy üzleti követelményeinek teljesítésére tervezték. Az egységközi könyvelési funkció a Finance programban csak az egyes tranzakciók által létrehozott könyvelési tételek megoldását szolgálja.

Jogi személyiséggel rendelkező pénzügyi dimenziók beállítása előtt a következő területeken értékelje ki az üzleti folyamatait annak meghatározására, hogy ez a beállítás működik-e a szervezete esetében:

- Készlet
- Értékesítések és beszerzések üzleti dimenziók és jogi személyek között
- Áfa számítás és jelentés
- Üzemi jelentés

Az alábbiakban a limitációk közül sorolunk fel néhányat:

- Az áfa funkciók csak jogi személyekhez használhatók, a pénzügyi dimenziókhoz pedig nem.
- Egyes jelentésekben nem szerepelnek a pénzügyi dimenziók. Ezért pénzügyi dimenziók szerinti jelentéskészítésnél előfordulhat, hogy módosítani kell a jelentéseket.

## <a name="custom-dimensions"></a>Egyéni dimenziók

A felhasználó által definiált pénzügyi dimenziók létrehozásához az **Értékek használata innen** mezőben jelölje be az **Egyéni dimenzió** lehetőséget.

A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát. Megadhat olyan karaktereket, például betűket vagy kötőjelet (-), amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (\#) vagy és-jelet (&) olyan karakterek helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (\#) a számok, míg az és-jel (&) a betűk helyőrzője. Ez a mező a formátummaszkhoz csak akkor érhető el, ha az **Egyéni dimenzió** opciót választja ki az **Értékek használata innen** mezőből.

**Példa**

Ha például a dimenzióértéket két „C” betűre és három számra szeretné korlátozni, formátummaszkként a **CC-\#\#\#** értéket adja meg.

## <a name="entity-backed-dimensions"></a>Entitás által támogatott dimenziók

Entitás által támogatott pénzügyi dimenzió létrehozásához az **Értékek használata innen** mezőben válasszon ki egy a pénzügyi dimenzió alapjául szolgáló rendszer által definiált entitást. A kijelölés alapján létrejönnek a pénzügyi dimenzióértékek az érintett entitásból. Például projektek dimenzióértékeinek létrehozásához jelölje ki a **Projekteket**. A rendszer ekkor minden projektnévhez létrehozza a dimenzióértéket. A **Pénzügyi dimenzióértékek** lap jeleníti meg az entitás értékeit. Ha ezek az értékek vállalatspecifikusak, a lapon a vállalat is szerepel.

## <a name="activating-dimensions"></a>Dimenziók aktiválása

Amikor aktivál egy pénzügyi dimenziót, a tábla frissül, hogy a pénzügyi dimenzió nevét is tartalmazza. A törölt dimenziók törlődnek. A pénzügyi dimenzió aktiválása előtt dimenzióértékeket adhat meg. Azonban a pénzügyi dimenzió sehol sem használható fel, amíg nincs aktiválva. Például nem adhat hozzá pénzügyi dimenziót számlastruktúrához, amíg nem aktiválódik a pénzügyi dimenzió. Amikor kiválasztja az **Aktiválás** lehetőséget, az összes dimenzió frissül, és megjelennek az állapotváltozások.

## <a name="translations"></a>Fordítások

A **Szöveg fordítása** lapon a kijelölt pénzügyi dimenzióhoz különböző nyelveken lehet szöveget beírni. A **Fő számla** lapon a fő számlához különböző nyelveken lehet szöveget beírni. 

## <a name="legal-entity-overrides"></a>Jogi személy felülbírálásai

Nem minden dimenzió érvényes minden jogi személyhez. Ezenkívül néhány dimenzió csak egy adott időszakra vonatkozhat. Ezekben az esetekben a **Jogi személy felülbírálása** szakasz használható annak a megadására, hogy mely vállalatok számára kell felfüggeszteni a dimenziót, ki a tulajdonos, és mely időszakban aktív a dimenzió.

## <a name="deleting-financial-dimensions"></a>Pénzügyi dimenziók törlése

Az adatok hivatkozási integritásának fenntartása érdekében a pénzügyi dimenziók ritkán törölhetők. Ha megpróbálja törölni a pénzügyi dimenziót, a következő feltételek értékelése történik meg:

- Használták a pénzügyi dimenziót bármely feladatlan vagy feladott tranzakcióban, vagy bármilyen típusú dimenzióérték-kombinációban?
- Használták a pénzügyi dimenziót bármilyen aktív számlastruktúrában, speciális szabálystruktúrában vagy pénzügyidimenzió-készletben?
- Része a pénzügyi dimenzió az alapértelmezett pénzügyidimenzió-integrációs formátumnak?
- A pénzügyi dimenzió be van állítva alapértelmezés szerinti dimenzióként?
- Ki lett választva a pénzügyi dimenzió a Pénzügyi jelentés beállítása beállításból? 

Ha a feltételek bármelyike teljesül, a pénzügyi dimenzió nem törölhető.

> [!NOTE]
> A Pénzügyi verzió 10.0.27-es verziójától kezdve a pénzügyi dimenziók a létrehozáskor nem lesznek automatikusan kiválasztva a pénzügyi jelentési beállítások között.

## <a name="default-dimension-values"></a>Alapértelmezett dimenzióértékek

Az új dimenziók alapértelmezett értékeiként használhatja a törzsrekordok értékeit, például az ügyfelek és a szállítók értékeit. Az új dimenziók létrehozásakor a törzsrekordazonosító szerepel a dimenzióértékekben a törzsrekordoknál. Amikor például új ügyfelet hoz létre, az ügyfél-azonosító beírása az ügyféldimenzióba történik. Értékesítési rendelések, számlák vagy más olyan dokumentumok létrehozásakor, amelyek vevői azonosítót igényelnek, a meglévő alapértelmezési szabályok érvényesek, és a vevői azonosító hozzáadódik a dokumentumhoz.

Ezt a funkciót a dimenzió egyik beállítása szabályozza. A beállítás neve **Értékek másolása ehhez a dimenzióhoz minden egy létrehozott új DimensionName esetén**, ahol **DimensionName** a dimenzió neve. Alapértelmezés szerint a funkció ki van kapcsolva. Azonban bármikor bekapcsolható.

Ha már léteznek rekordok a dimenziónál, a törszrekordok a funkció bekapcsolásakor frissülnek. A meglévő bizonylatok és tranzakciók azonban nem frissülnek.

Ha sablont használ a fő rekord létrehozásához, ellenőrizze, hogy a sablon értéke a fő dimenzióhoz üres legyen. Például ha sablon alapján hoz létre vevőket, győződjön meg arról, hogy a vevő dimenziója a sablonban üres. Az új vevő létrehozásakor a vevői dimenzió értéke alapértelmezetten az új ügyfélszámból jön létre.  

## <a name="derived-dimensions"></a>Származtatott dimenziók

Beállítható egy dimenzió úgy, hogy a többi dimenzió információi automatikusan bekerüljenek olyankor, amikor Ön megadja az adott dimenziót egy dokumentumban. Ha például a költséghely értékeként a 10-et adja meg, akkor a rendszer a **20** értéket automatikusan beírhatja a részleg dimenzióhoz.

A származtatott értékeket a dimenziók lapon állíthatja be.

1. Válasszon ki egy dimenziót, majd válassza a **Származtatott dimenziók** lehetőséget.

    A **Származtatott dimenziók** lap tartalmaz egy rácsot. A kiválasztott dimenziószegmens a rács első oszlopa.

2. Adja meg a származtatni kívánt szegmenseket. Minden szegmens oszlopként jelenik meg.

Adja meg azokat a dimenziókombinációkat, amelyeket az első oszlopban lévő dimenzióból kell származtatni. Ha például a költséghelyet szeretné használni, mint a dimenziót, amelyből a részleget és a helyet származtatni kívánja, adja meg a 10 értéket költséghelyként, a 20-at részlegként és a 30-at helyként. Ha ezt követően megadja a 10-es költséghelyet egy tözsrekordban vagy egy tranzakciólapon, akkor a rendszer automatikusan beviszi a 20-as részleget és a 30-as helyet alapértelmezés szerint.

### <a name="overriding-existing-values-with-derived-dimensions"></a>Meglévő értékek felülírása származtatott dimenziókkal
 
Alapértelmezetten a származtatott dimenzió folyamata nem bírálja felül a meglévő értékeket a származtatott dimenzióknál. Ha például a 10-es költséghelyet ír be, és nincs megadva másik dimenzió, akkor a rendszer automatikusan beviszi a 20-as részleget és a 30-as helyet alapértelmezés szerint. Ha azonban módosítja a költséghelyet, a korábban beállított értékek nem változnak. Így megadhatja az alapértelmezett dimenziókat a törzsrekordokon, de ezeket a dimenziókat nem módosítják a származtatott dimenziók.

Ha módosítani szeretné a származtatott dimenziók viselkedését a meglévő értékek felülírására, módosítsa a **Meglévő dimenzióértékek lecserélése származtatott értékekre** a jelölőnégyzetet a **Származtatott dimenziók** lapon. Ha ez a mező be van jelölve, megadhat egy dimenziót származtatott dimenzióértékkel, és ezek a származtatott dimenzióértékek az összes már meglévő értéket felülbírálják. Az előző példában, ha a 10-es költséghelyet írja be, és nincs megadva másik dimenzió, akkor a rendszer automatikusan beviszi a 20-as részleget és a 30-as helyet alapértelmezés szerint. Azonban ha az érték már az 50-es részleg és a 60-as hely volt, az értékek módosulnak a 20-as részlegre és a 30-as helyre.
 
Azt ilyen beállítású származtatott dimenziók nem helyettesítik automatikusan a meglévő alapértelmezett dimenzióértékeket, ha alapértelmezett dimenzióértékek vannak. A dimenzióértékeket csak akkor lehet felülbírálni, ha egy lapon új dimenzióértéket ad meg, és ehhez a dimenzióhoz az oldalon már léteznek a származtatott értékek.

### <a name="preventing-changes-with-derived-dimensions"></a>Származtatott dimenziókkal módosítások megakadályozása
 
A **Szegmens hozzáadása** használata esetén a **Származtatott dimenziók lapon** szegmens hozzáadására származtatott dimenzióként, egy lehetőség van a **Szegmens hozzáadása** lap alján, amely lehetővé teszi a dimenzió módosításának megakadályozását, amikor egy weblapon származtatva van. Az alapértelmezett beállítás ki van kapcsolva, így nem akadályozza meg a származtatott dimenzióértékek változását. Ha meg szeretné **akadályozni**, hogy a dimenzió a származtatás után módosult, módosítsa Igen beállításra. Például a Részleg dimenzió értéke a Költséghely dimenzió értékének származtatottja, a Szervezeti egység értéke nem módosítható, ha a **Módosításának megakadályozása** értéke **Igen**. 
 
A beállítás nem akadályozza meg módosításokat, ha a dimenzióérték érvényes, de nem szerepel a származtatott dimenziók listájában. Például ha a 20-as osztály a 10-es költségközpont származtatottja, és beírja a 10-es költséghelyet, majd nem lesz szerkeszthető a 20-as részleg. Ugyanakkor ha megadja a 20-as költséghelyet, és nem szerepel a Költséghely származtatott dimenzióinak listáján, módosíthatja a Részleg értéket. 
 
Minden esetben a számlaértéket és minden dimenzióértéket a program továbbra is összeveti a számlastruktúrákkal a származtatott dimenzióérték alkalmazása után. Ha származtatott dimenziókat használ, és az ellenőrzés során elbuknak egy lapon, módosítania kell a származtatott dimenzióértéket a származtatott dimenziók lapon a használatuk előtt a tranzakciókban. 
 
A dimenziók változásakor a **Pénzügyi dimenziók** gyorslapon, nem lesz szerkeszthető az a dimenzió, amely be van jelölve a módosítások megakadályozására. Egy számlát és dimenziókat rögzít a szegmentált bejegyzés vezérlőelembe egy lapon, a dimenziók szerkeszthetők. Azonban ha a kijelölést elviszi a szegmentált bejegyzés vezérlőelemből, és egy másik mezőbe áthelyezi vagy műveletet végez, a fiókot és a dimenziókat a program összeveti a származtatott dimenziók listájával és a számlastruktúrákkal annak biztosítására, hogy valóban a megfelelő értékeket vigye be. 

### <a name="derived-dimensions-and-entities"></a>Származtatott dimenziók és entitások

Entitások használatával beállíthatja a származtatott dimenziók szegmenseit és értékeit.

- A Származtatott dimenziók entitás beállítja az irányadó dimenziókat és az adott dimenzióknál használt szegmenseket.
- A származtatott dimenzió értéke entitással importálhatja azokat az értékeket, amelyeket az egyes irányadó dimenzióknál származtatni kell.

Ha egy adott entitás révén importálja az adatokat, akkor amennyiben az adott entitás dimenziókat importál, akkor a származtatott dimenziószabályokat alkalmazza a rendszer az importálás során, kivéve, ha az entitás kifejezetten felülbírálja az adott dimenziókat.

## <a name="financial-dimension-service"></a>Pénzügyi dimenzió szolgáltatás

A Pénzügyi dimenzió szolgáltatás bővítménye elérhető a Microsoft Dynamics Lifecycle Services környezetben. Jobb teljesítményt nyújt, amikor az adatkezelési keretrendszert nagy számú sorból származó napló importálására használja. A szolgáltatás csak akkor használható, ha engedélyezni **szeretné azt a Pénzügyi dimenzió szolgáltatás paraméterei oldalon** . Jelenleg a szolgáltatás csak olyan importált naplókban működik, amelyekben 500 sor vagy több van. Emellett jelenleg csak olyan főkönyvi **naplókat** dolgoz fel, amelyekben a főkönyvi számlatípus be van állítva a naplósorok között. A naplósorok egyéb számlatípusai, **például** a Vevő, **·** **a Szállító és a Bank**, jelenleg nem támogatottak. A szolgáltatás nem hívható meg, ha származtatott dimenziók vannak beállítva a rendszerben.

A Pénzügyi dimenzió szolgáltatás jobb teljesítményt nyújt, amikor naplókat importálnak egy olyan új szolgáltatás használatával, amely párhuzamosan fut az adatimportmal. A program csak a fő számla és a pénzügyi dimenzió adatait futtatja a naplóban, és létrehozza a naplósorok főkönyviszámla-karakterlánc mezőjében megadott dimenziókombinációkat. A feldolgozás ezt a karakterláncot olyan strukturált adattárolóvá alakítja, amely a pénzügyi dimenzió keretrendszere a termék többi részében érvényesítésre, összefoglaló jelentésre és lekérdezésre használ. A pénzügyi dimenzióadatok összegző jelentésekkel kapcsolatos további tudnivalókat lásd [: Pénzügyi dimenziókészletek](financial-dimension-sets.md).

További információért tekintse át az alábbi témaköröket:

- [Pénzügyi dimenziók meghatározása](tasks/define-financial-dimensions.md)
- [Pénzügyi dimenzió alapértelmezett sablonjainak karbantartása](tasks/maintain-financial-dimension-default-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
