---
title: Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése
description: Ez a cikk azt ismerteti, hogyan lehet kezelni a Dynamics 365 Pénzügy elektronikus jelentéskészítési (ER) konfigurációinak életciklusát.
author: kfend
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 0209679c9882d87edab68d043fba9e7b3400a2a2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337263"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése

[!include [banner](../includes/banner.md)]

Ez a cikk azt ismerteti, hogyan [lehet](general-electronic-reporting.md) kezelni a Dynamics 365 Pénzügy elektronikus jelentéskészítési (ER) [konfigurációinak](general-electronic-reporting.md#Configuration) életciklusát.

## <a name="overview"></a>Áttekintés

Az Elektronikus jelentés (ER) felel a jogszabályokban követelményként előírt és országspecifikus dokumentumok támogatásáért. Általánosságban az ER feltételezi, hogy az alábbi feladatok elvégezhetők egyetlen elektronikus dokumentumhoz. További részletekért lásd: [Elektronikus jelentés (ER) – áttekintés](general-electronic-reporting.md).

- Sablon tervezése elektronikus dokumentumhoz:

    - Határozza meg a dokumentumban feltüntethető adatokhoz szükséges forrásokat:

        - Másodlagos adatok, például adattáblák, adatentitások és osztályok.
        - Folyamat-specifikus tulajdonságok (végrehajtási dátum és idő, valamint időzóna).
        - Felhasználó által megadott paraméterek (futásidőben, végfelhasználó által megadott).

    - Definiálja a szükséges dokumentum elemeinek, valamint ezen elemeknek a végső dokumentum formátumának meghatározásához használt topológiát.
    - A dokumentum elemeinek (adatforrás kötéssel a dokumentumformátum komponenséhez), valamint a folyamatvezérlő logika meghatározásához konfigurálja a kívánt adatfolyamot a kiválasztott adatforrásokból.

- Tegyen elérhetővé egy sablont, ezáltal használhatóvá válnak más példányokban:

    - Alakítson át egy, a Dynamics AX-ben készült dokumentumot ER konfigurációvá. Ezt követően exportálja a jelenlegi alkalmazáspéldányból helyileg, illetve Lifecycle Servicesben (LCS) tárolható XML csomagként.
    - Alakítson át ER konfigurációt alkalmazás-dokumentumsablonná.
    - Importáljon egy helyben, vagy LCS-ben tárolt XML csomagot a példányába.

- Egy elektronikus dokumentum sablonjának testreszabása:

    - Egy sablon ER-konfigurációként importálása az aktuális példányba az LCS-ből.
    - Egy ER-konfiguráció testreszabott verziójának megtervezése, hivatkozást biztosítva az alapverzióhoz.

- Integráljon egy bizonyos üzleti folyamattal rendelkező sablont, hogy az elérhető legyen az alkalmazásban:

    - Ha hivatkozik a folyamathoz kapcsolódó paraméteren belüli konfigurációra, akkor beállíthatja, hogy az alkalmazás elkezdje használni az ER-konfigurációt. Például hivatkozzon egy ER konfigurációra egy megadott Kötelezettségek fizetése módban, hogy elektronikus fizetési üzenetet hozzon létre a feldolgozás alatt lévő számlákhoz.

- Egy sablon használata egy meghatározott üzleti folyamatban:

    - Futtasson ER-konfigurációt egy meghatározott üzleti folyamatban. Például hozzon létre számlafeldolgozással kapcsolatos elektronikus fizetési üzenetet, amikor egy ER-konfigurációra mutató hivatkozást használó fizetési módszer van kiválasztva

## <a name="concepts"></a>Koncepció
A következő szerepkörök és a kapcsolódó tevékenységek társítva vannak az ER-konfigurációk életciklusához.

| Szerep                                       | Tevékenységek                                                      | Leírás |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Elektronikus jelentések funkcióival foglalkozó konzulens | Hozzon létre és kezeljen egy ER komponenst (modellek és formátumok).           | Egy üzleti személy, aki az ER tartomány-specifikus adatmodelleket tervezi, fogja megfelelően hozzákötni és megtervezni az elektronikus dokumentumokhoz szükséges sablonokat. |
| Elektronikus jelentések fejlesztője             | Adatmodell hozzárendelések létrehozása és kezelése.                          | Egy szakember, aki kiválasztja a szükséges Finance adatforrásokat és hozzáköti azokat az ER tartomány-specifikus adatmodellekhez. |
| Számviteli felügyelő                      | Az ER műtermékre hivatkozó folyamathoz kapcsolódó beállítás konfigurálása. | Például egy **Számviteli felügyelő** szerepkör, ami engedélyezi, hogy az ER konfiguráció beállításai használhatóak legyenek egy megadott Kötelezettségek fizetése módban, a feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozásánál. |
| Kötelezettségkifizetési adminisztrátor            | Egy ER műtermék használata egy meghatározott üzleti folyamatban.                | Például egy **Kötelezettségkifizetési adminisztrátor** szerepkör, ami engedélyezi a megszabott fizetési módhoz konfigurált ER formátumon alapuló, feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozását. |

## <a name="er-configuration-development-lifecycle"></a>ER konfiguráció fejlesztési életciklusa
Az ER-kiszolgálóval kapcsolatos következő okok miatt javasoljuk, hogy az ER-konfigurációkat a fejlesztési környezetben, a pénzügyek és a műveletek különálló példányaként tervezza meg:

- Az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók szerkeszthetik a konfigurációkat is futtathatják azokat tesztelés céljából. Olyan osztályok és táblázatok módszereit hívhatja meg, amelyek esetleg károsak lehetnek az üzleti adatokra és a példány használati hatékonyságára nézve.
- A belépési pontok és naplózott vállalati tartalmak nem korlátozzák az osztály- és táblázatmódszerek ER-konfigurációkhoz tartozó ER-adatforrásokként történő hívását. Tehát a bizalmas üzleti adatokhoz hozzáférnek az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók.

A fejlesztői környezetben megtervezett ER-konfigurációk [feltölthetők](#data-persistence-consideration) a tesztkörnyezetbe a konfiguráció kiértékelése (megfelelő folyamatintegrálás, eredményhelyesség, teljesítmény), illetve a minőségbiztosítás (például szerepkörtől függő hozzáférési jogok helyessége, feladatkörök szétválasztása) céljából. Azok a funkciók használhatóak erre a célra, amelyek engedélyezik az ER konfiguráció adatcseréjét. Az igazoltan helyes ER-konfigurációk feltölthetők az LCS-be megosztásra a szolgáltatás előfizetőivel, vagy [importálhatók](#data-persistence-consideration) az éles környezetbe belső használatra.

![ER-konfigurációs életciklus.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Adatperzisztencia figyelembe vétele

Az ER-konfiguráció [különböző](tasks/er-import-configuration-lifecycle-services.md) verzióit egyenként importálhatja a [Pénzügyi](general-electronic-reporting.md#Configuration) példányba. Az ER-konfiguráció új verziójának importálása esetén a rendszer szabályozza ennek a konfigurációnak a vázlatverzióját:

- Ha az importált verzió alacsonyabb, mint a jelenlegi Finance példány konfigurációjának legmagasabb verziója, akkor a konfiguráció vázlatverziójának tartalma változatlan marad.
- Ha az importált verzió magasabb, mint a jelenlegi Finance példány konfigurációjának bármely más verziója, akkor a program átmásolja az importált verzió tartalmát ennek a konfigurációnak a vázlatverzióba, hogy folytatható legyen a legutóbbi befejeződött verzió szerkesztése.

Ha a konfiguráció tulajdonosa az aktuálisan aktivált konfigurációs [szolgáltató](general-electronic-reporting.md#Provider), akkor ennek a konfigurációnak a vázlatverziója látható a **Konfigurációk** lap **Verziók** gyorslapján (**Szervezet felügyelete** > **Elektronikus jelentés** > **Konfigurációk**). A megfelelő ER tervezővel kiválaszthatja a konfiguráció vázlatverzióját, és [módosíthatja](er-quick-start2-customize-report.md#ConfigureDerivedFormat) a tartalmát. Ha szerkesztette az ER-konfiguráció vázlatverzióját, akkor a tartalma már nem egyezik meg a jelenlegi Finance példány konfigurációjának legmagasabb verziójával. A módosítások elvesztésének megakadályozása érdekében a rendszer hibát jelenít meg azzal, hogy az importálás nem folytatható, mert a konfiguráció verziója magasabb, mint a konfigurációnak a jelenlegi Finance példányban érvényes legmagasabb verziója. Ilyen esetben például az **X** formátumkonfigurációnál, ez a hiba jelenik meg: **Az „X” formátum verziója nem fejeződött be**.

A vázlatverzióban bevezetett módosítások visszavonásához válassza ki a Finance eszközben az ER-konfiguráció legmagasabb befejeződött vagy megosztott verzióját a **Verziók** gyorslapon, majd válassza a **Verzió beszerzése** lehetőséget. A kiválasztott verzió tartalmát a program a vázlatverzióba másolja.

## <a name="applicability-consideration"></a>Alkalmazhatósági megfontolás

Amikor egy ER-konfiguráció új verzióját tervezi, meghatározhatja annak más szoftverkomponensektől való [függőségét](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md). Ez a lépés előfeltétele annak, hogy a konfiguráció verziójának ER-adattárból vagy külső XML-fájlból történő letöltését ellenőrizze, valamint a verziót később is használja. Amikor megpróbálja importálni egy ER-konfiguráció új verzióját, a rendszer a konfigurált előfeltételek alapján ellenőrzi, hogy a verzió importálható-e.

Bizonyos esetekben megkövetelheti, hogy a rendszer figyelmen kívül hagyja a konfigurált előfeltételeket, amikor az ER-konfigurációk új verzióit importálja. Ha szeretné, hogy a rendszer az importálás során figyelmen kívül hagyja az előfeltételeket, kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. Állítsa a **Termékfrissítések és verzió-előfeltételek ellenőrzésének kihagyása importálás közben** opciót **Igen** értékre.

    > [!NOTE]
    > Ez a paraméter a felhasználó- és a vállalatspecifikus.

## <a name="dependencies-on-other-components"></a>Más összetevőktől való függőségek

Az ER-konfigurációk más [konfigurációktól](er-download-configurations-global-repo.md#import-filtered-configurations) függenek. [Például](er-download-configurations-global-repo.md) importálhat egy ER-adatmodell-konfigurációt [...](er-overview-components.md#data-model-component)[a globális tárházból a Microsoft Regulatory Configuration Services (RCS)](../../../finance/localizations/rcs-overview.md) vagy a Dynamics 365 Pénzügy példányba, majd létrehozhat egy új ER-formátumkonfigurációt [...](er-overview-components.md#format-component)[...](er-quick-start2-customize-report.md#DeriveProvidedFormat), amely az importált ER adatmodell-konfigurációból származik. A származtatott ER-formátum konfigurációja az alap ER adatmodell-konfigurációtól függ.

![Származtatott ER formátumkonfiguráció a Konfigurációk lapon.](./media/ger-configuration-lifecycle-img1.png)

Amikor befejezte a formátum megtervezését, az ER-formátumkonfiguráció **kezdeti** verziójának állapotát Vázlat állapotról Készre **változtathatja**. Ezt követően a globális tárházban való közzétételével megoszthatja az ER-formátumkonfiguráció [kész](../../../finance/localizations/rcs-global-repo-upload.md) verzióját. Ezután bármely RCS vagy Pénzügyi felhőpéldányból hozzáfér a globális tárházhoz. Ezt követően importálhatja az alkalmazásra vonatkozó ER-konfigurációs verziót a globális tárházból ebbe az alkalmazásba.

![Közzétett ER-formátumkonfiguráció a konfigurációs tárház oldalon.](./media/ger-configuration-lifecycle-img2.png)

A konfigurációfüggőség alapján, amikor a globális tárházban az ER-formátum konfigurációját választja az újonnan telepített RCS vagy Pénzügy példányba történő importáláshoz, az alap ER adatmodell konfigurációja automatikusan megjelenik a globális tárházban, és a kiválasztott ER-formátumkonfigurációval együtt importálja azt.

Exportálhatja az ER-formátum konfigurációverzióját az aktuális RCS- vagy pénzügyi példányból is, és helyileg XML-fájlként tárolhatja.

![ER formátumkonfigurációs verzió exportálása XML-formátumban a Konfigurációs lapon](./media/ger-configuration-lifecycle-img3.png)

**A Pénzügy rendszer 10.0.29 verzió előtti verzióiban amikor az ADOTT XML-fájlból vagy a globális tárháztól különböző tárházból próbálja meg importálni az ER-formátumkonfigurációs** verziót egy újonnan telepített RCS vagy Pénzügyi példányba, amely még nem tartalmaz ER-konfigurációt, a következő kivétel fog megnyílni, és arról tájékoztat, hogy az alapkonfigurációt nem lehet behozni:

> Feloldatlan hivatkozás maradt<br>
Nem lehet hivatkozni a\<imported configuration name\>"" objektumra az "Alap" (\<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>) objektumra.

![Az ER-formátum konfigurációs verziójának importálása a Konfigurációs tárház oldalon.](./media/ger-configuration-lifecycle-img4.gif)

**A 10.0.29-es** és újabb verzióban, amikor ugyanezt a konfigurációs importálást próbálja meg használni, ha nem található alapkonfiguráció az aktuális alkalmazáspéldányban vagy a jelenleg használt forrástárházban (ha van), az ER keretrendszer automatikusan megpróbálja megtalálni a hiányzó alapkonfiguráció nevét a globális tárház-gyorsítótárban. Ezt követően a hiányzó alapkonfiguráció nevét és globálisan egyedi azonosítóját (GUID) a létrehozott kivétel szövegében mutatja.

> Feloldatlan hivatkozás maradt<br>
Nem lehet hivatkozni a\<imported configuration name\> "Base"\<name of the missed base configuration\>\<globally unique identifier of the missed base configuration\> objektumra (,\<version of the missed base configuration\>)

![Kivétel van a Konfigurációs tárház oldalon, ha nem található az alapkonfiguráció.](./media/ger-configuration-lifecycle-img5.png)

A megadott névvel megkeresheti az alapkonfigurációt, majd manuálisan importálhatja.

> [!NOTE]
> Ez az új lehetőség csak akkor működik, ha [legalább](er-download-configurations-global-repo.md#open-configurations-repository)[egy](er-extended-format-lookup.md) felhasználó már bejelentkezett a globális tárházba a Konfigurációs tárház lap vagy az aktuális Pénzügyi példány globális tárház-keresési mezőinek valamelyikének használatával, és ha a globális tárház tartalmát gyorsítótárazták.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Az ER-konfigurációk függőségének meghatározása más összetevőknél](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

