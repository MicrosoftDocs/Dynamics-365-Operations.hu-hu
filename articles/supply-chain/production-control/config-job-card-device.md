---
title: Feladatkártya konfigurálása az eszközökhöz
description: Ez a témakör a feladatkártya-eszköz konfigurálásával kapcsolatos különféle beállításokat ismerteti.
author: johanhoffmann
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 0f42ad593f59f716fb6cb535d73654d3549ba00e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860725"
---
# <a name="configure-job-card-for-devices"></a>Feladatkártya konfigurálása az eszközökhöz

[!include [banner](../includes/banner.md)]

A feladatkártya eszközt az üzemszinten dolgozók használják a napi munkájuk regisztrálására, például, hogy mikor kezdtek el egy feladatot a feladatokkal kapcsolatos visszajelzésekhez, a közvetett tevékenységek regisztrálására és a távollétek jelentésére. Ezek a regisztrációk alapot biztosítanak a termelési rendelések előrehaladásának és a költségeinek a nyomon követésére és a dolgozók fizetése kiszámításának alapjául szolgálnak. Ez a témakör a feladatkártya-eszközök konfigurálásával kapcsolatos különféle beállításokat ismerteti.

## <a name="enable-new-features-in-feature-management"></a>Új szolgáltatások engedélyezése a szolgáltatások kezelésében

A jelen leírásban leírt beállítások egy része csak akkor érhető el, ha a rendszerben engedélyeztetve vannak. Használja a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lapot a következő funkciók igény szerinti engedélyezéséhez.

### <a name="generate-license-plate"></a>Azonosítótábla előállítása

A funkció elérhetővé tétele érdekében engedélyezze a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (sorrendben):

1. *A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla*<br>(Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)
1. *Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)

### <a name="print-label"></a>Címkenyomtatás

A funkció elérhetővé tétele érdekében engedélyezze a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (sorrendben):

1. *A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla*<br>(Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)
1. *Címke nyomtatása a Feladatkártya eszközéből*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)

### <a name="allow-locking-of-touch-screen"></a>Az érintőképernyő zárolásának engedélyezése

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a feladatkártya-eszköz és a feladatkártya terminálok zárolására szolgáló funkció keresésével kapcsolják be és kapcsolják ki ezt a funkciót, hogy a szolgáltatáskezelés munkaterületén ki- és bekapcsolható legyen a szolgáltatás.

## <a name="manage-your-device-configurations"></a>Eszközkonfigurációk kezelése

Az eszközkonfigurációk beállításához ugorjon a **Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz** elemre. Megnyílik a **Feladatkártya beállítása eszközökhöz** lap, amelyen látható a meglévő konfigurációk listája. Innen az alábbiakra nyílik mód: 

- Kiválaszthatja bal oldali oszlopban felsorolt eszközkonfigurációk bármelyikét, hogy megtekintse és szerkessze azt.
- Új eszközkonfiguráció hozzáadásához listához a műveleti ablaktáblán válassza az **Új** lehetőséget. Adjon meg egy nevet a **Konfiguráció** mezőben, amely lehetővé teszi az új konfiguráció azonosítását. Az itt megadott értéknek egyedinek kell lennie az összes eszköz-konfiguráció között, és később már nem szerkeszthető.

A feladatkártya-eszközök konfigurálásával kapcsolatos további tudnivalókat lásd a következő részekben:.

## <a name="general-settings"></a>Általános beállítások

Az **Általános** gyorslap a kiválasztott eszközkonfigurációhoz rendelkezésre álló beállításokat konfigurálhatja. A következő beállítások állnak rendelkezésre:

- **Mennyisége jelentése távozáskori blokkoláskor** – Ezt állítsa **Igen** értékre megkérheti a dolgozókat, hogy adják meg a folyamatban lévő munkák visszajelzéseit a távozáskori blokkoláskor. Ha **Nem** értékre van állítva, akkor a dolgozók nem lesznek figyelmeztetve.
- **Alkalmazott zárolása** – Ha ez a beállítás **Nem** értékre van állítva, akkor a rendszer egy regisztrációt (például új feladat regisztrációja) követően azonnal kijelentkeztet minden dolgozót, majd az eszköz visszatér a bejelentkezési lapra. Ha ez a beállítás **Igen** értékre van állítva , akkor minden dolgozó bejelentkezve marad a feladatkártya-eszközbe. Ugyanakkor a dolgozónak továbbra is lehetősége van a manuális kijelentkezésre ,hogy egy másik dolgozó bejelentkezhessen úgy, hogy az eszköz ugyanabban a rendszerfelhasználói fiókban marad. A fiókok típusairól a [Hozzárendelt felhasználók](#assigned-users) című témakörben olvashat bővebben.
- **Vonalkódolvasó** - Állítsa ezt a beállítást **Igenre**, hogy a munkakártya-eszközön legyen egy olyan lehetőség, amely lehetővé teszi a dolgozók számára, hogy egy vonalkód beolvasásával regisztrálják egy új munka kezdetét.
- **A regisztráció tényleges időpontjának használata** – Ezt a beállítást **Igen** értékre állíthatja, ha azt szeretné, hogy az egyes új regisztrációk időpontja a dolgozó által benyújtott regisztráció pontos időpontjával egyezzen meg. A **Nem** értékre állításával a bejelentkezési időt használhatja helyette. Ezt a beállítást általában **Igen** értékre kell állítani , ha engedélyezve van az **Alkalmazott zárolása** és/vagy az **Egy dolgozó** beállítás, aminek következtében a dolgozók általában hosszabb ideig bejelentkezve maradnak.
- **Egyetlen dolgozó** – Állítsa ezt a beállítást **Igen** értékre ha csak egy dolgozó használja a feladatkártya-eszközt, ha ez a konfiguráció aktív. Ha ez a beállítás be van jelölve, akkor az **Alkalmazott zárolása** beállítás automatikusan **Igen** értékre van állítva. Ezenkívül ez a beállítás eltávolítja a dolgozónak a belépőkártya-azonosító (vagy hasonló) használatával történő bejelentkezésre vonatkozó követelményét (és képességét). Ehelyett a dolgozó a Supply Chain Management alkalmazásba egy olyan rendszerfelhasználói fiókkal jelentkezik be, amely egy *időregisztrált dolgozóhoz* van társítva (a *dolgozók* táblából), és dolgozóval egyidőben bejelentkezik a feladatkártya eszközbe.  A fiókok típusairól a [Hozzárendelt felhasználók](#assigned-users) című témakörben olvashat bővebben.
- **Személyes szűrők beállításának engedélyezése a dolgozóknak** – Ezt a beállítást **Igen** értékre állítva a dolgozók szűrhetik az eszközön számukra megjelenített feladatokat. A dolgozó módosíthatja következő három szűrési feltétel bármely értékeit: **Termelési egység**, **Erőforráscsoport** és **Erőforrás**. Csak a kiválasztott szűrési feltételeknek megfelelő erőforrásokra ütemezett feladatok jelennek meg az eszközön. A feltételek bármelyikéhez vagy mindegyikéhez rendelhet hozzárendelhet alapértelmezett értékeket is, és azok akkor is alkalmazva lesznek, ha ez a beállítás nincs kiválasztva.
- **Az érintőképernyő zárolásának engedélyezése** – Ezt a beállítást **Igen** értékre engedélyezheti a dolgozók számára, hogy zárolják a feladatkártya-eszközt képernyőjét, hogy fertőtleníthessék azt. Ha engedélyezve van, akkor a **Képernyő zárolása fertőtlenítéshez** gomb eszköz bejelentkezési oldalára kerül. Amikor egy dolgozó kiválasztja ezt a gombot, az érintőképernyő ideiglenesen zárolva lesz a véletlen bevitel elkerüléséhez, és megjelenik egy időzítő. A dolgozó most már biztonságosan megtisztíthatja a készüléket és a képernyőt. Amikor a visszaszámlálás befejeződött, az érintőképernyő automatikusan fel lesz oldva.
- **Képernyő zárolásának időtartama** – Ha **Képernyő zárolásának engedélyezése** beállítás engedélyezve van, akkor ezzel a beállítással adja meg, hogy hány másodpercig kell zárolni az érintőképernyőt a fertőtlenítéshez. Az időtartamnak 5 és 120 másodperc között kell lennie.
- **Termelési egység** – Válassza ki azt a termelési egységet, amelyet a dolgozóknak megjelenített feladatlista alapértelmezett szűrési feltételeként kell alkalmazni. Kezdetben az eszköz csak a kiválasztott termelési egység alá csoportosított erőforrásokhoz ütemezett feladatokat jeleníti meg. Ha a **Személyes szűrők beállításának engedélyezése a dolgozók számára** lehetősége engedélyezve van, akkor a dolgozók szerkeszthetik ezt az értéket, máskülönben ez a szűrő mindig alkalmazva lesz, amikor ez az eszközkonfiguráció aktív.
- **Erőforráscsoport** – Válassza ki azt az erőforráscsoportot amelyet a dolgozóknak megjelenített feladatlista alapértelmezett szűrési feltételeként kell alkalmazni. Kezdetben az eszköz csak a kiválasztott erőforráscsoport alá csoportosított erőforrásokhoz ütemezett feladatokat jeleníti meg. Ha a **Személyes szűrők beállításának engedélyezése a dolgozók számára** lehetősége engedélyezve van, akkor a dolgozók szerkeszthetik ezt az értéket, máskülönben ez a szűrő mindig alkalmazva lesz, amikor ez az eszközkonfiguráció aktív.
- **Erőforrás** – Válassza ki azt az erőforrást amelyet a dolgozóknak megjelenített feladatlista alapértelmezett szűrési feltételeként kell alkalmazni. Kezdetben az eszköz csak a kiválasztott erőforrásokhoz ütemezett feladatokat jeleníti meg. Ha a **Személyes szűrők beállításának engedélyezése a dolgozók számára** lehetősége engedélyezve van, akkor a dolgozók szerkeszthetik ezt az értéket, máskülönben ez a szűrő mindig alkalmazva lesz, amikor ez az eszközkonfiguráció aktív.
- **Azonosítótábla előállítása** – Ezt a lehetőséget **Igen** értékre állítsa új azonosítótábla előállításához minden alkalommal, amikor a dolgozó a feladatkártya eszközt készre jelentéshez használja. Az azonosítótábla a **Raktárkezelési paraméterek** lapon beállított számsorozatból jön létre. Ha **Nem** értékre van állítva, akkor a dolgozóknak a készként való jelentéskor meg kell határozniuk egy meglévő azonosítótáblát.
- **Címke nyomtatása** – Ez a lehetőséget állítsa **Igen** értékre egy azonosítótábla-címke nyomtatásához, amikor a dolgozó a feladatkártya eszközt használja készre jelentéshez. A címke konfigurációja a dokumentumirányításban van beállítva, a [Dokumentumirányítási elrendezés azonosítótábla-címkékhez](../warehousing/document-routing-layout-for-license-plates.md) részben leírtak szerint.

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Hozzárendelt felhasználók

A **Hozzárendelt felhasználók** gyorslap egy vagy több rendszerfelhasználó társítására használható az aktuális eszközkonfigurációhoz. Minden rendszerfelhasználóhoz csak egy munkaeszköz-konfiguráció tartozhat.

Eszköz beállításakor az informatikai dolgozó általában egy rendszerfelhasználói fiókkal jelentkezik be a Supply Chain Management alkalmazásba. Ezt követően az adott rendszerfelhasználóhoz társított munkaeszköz-konfiguráció mindaddig érvényes, amíg a rendszerfelhasználó továbbra is be van jelentkezve. Ezek a rendszerfelhasználói fiókok általában csak a feladatkártya-eszköz lapjának elérésére vannak korlátozva a Supply Chain Management többi részéhez nem biztosítanak hozzáférést.

Miután bejelentkezett a rendszerfelhasználó, és a munkaeszköz konfigurációja be van töltve, a dolgozók a feladatkártya eszközbe bejelentkezhetnek a *időregisztrált dolgozói* fiókjukkal (például egy vonalkód beolvasásával a saját belépőkártyájukról), hogy új munkát kezdjenek, és más típusú regisztrációkat hozzanak létre. A különböző dolgozók a nap folyamán be-és kiléphetnek, miközben ugyanaz az eszközkonfiguráció marad érvényben a gépen, mivel a rendszerszintű felhasználó egész nap bejelentkezve marad a Supply Chain Management alkalmazásba.

Azonban, ahogy korábban már említettük, amikor egy eszköz konfigurációját az **Egyetlen dolgozó** lehetőséggel használják, maguk a dolgozók általában a Supply Chain Management alkalmazásba egy rendszerfelhasználóval jelentkeznek be, ami a saját *időregisztrált munkás* fiókjukhoz van kapcsolva, tehát egyszerre betöltik a rendszerkonfigurációt és bejelentkeznek dolgozóként a feladatkártya eszközre.

## <a name="additional-resources"></a>További erőforrások

[Jelentés befejezettként a feladatkártya eszközből](report-finished-job-device.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]