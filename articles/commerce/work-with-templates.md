---
title: Sablonok használata
description: Ez a témakör a sablonokkal végzett munkát mutatja be a Microsoft Dynamics 365 Commerce alkalmazásban.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 96a8cbfd208095833514f374c060bb2d43781913
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793849"
---
# <a name="work-with-templates"></a>Sablonok használata

[!include [banner](includes/banner.md)]

Ez a témakör a sablonokkal végzett munkát mutatja be a Microsoft Dynamics 365 Commerce alkalmazásban.

Ahogyan a [Sablonok és elrendezések áttekintése](templates-layouts-overview.md) szakaszban azt már ismertettük, a sablonok határozzák meg, hogy milyen lehetőségek érhetők el a későbbi szerzők számára. A sablonok több okból is hasznosak a vállalati webfejlesztői csoport számára, és a jól strukturált sablonok a következő célok elérését segítik:

- A tartalomkezelési szerepkörök mindennapi szerzői élményének egyszerűsítése.

    - A modulbeállítások szűrése, hogy csak a megfelelő modulok jelenjenek meg egy adott oldal szakaszhoz. (Például egy sablon marketing szakasza konfigurálható úgy, hogy a lényegtelen modulok, amelyeket sohasem kell használni ebben a kontextusban, és csak akkor bonyolítanák a tartalomszerkesztési feladatokat, ki legyenek szűrve.)
    - A szerkesztési hatékonyság javítása érdekében konfigurálhatja az alapértelmezett modulbeállítást.
    - A szerkesztési hatékonyság javítása érdekében határozza meg az alapértelmezett laptöredékeket. (Például egy sablon fejléc-és lábléc-töredékei automatikusan megjelennek minden alsóbb szintű oldalon.)

- Az vállalti weboldalak márkaarculatának megtartása a jóváhagyott modulelrendezési és konfigurációs beállítások definiálásával.

    > [!TIP] 
    > A sikeres e-kereskedelmi webhelyeken a vevők ismerős, megismételhető és a márkának megfelelő felhasználói élménnyel (UX) és tervezési mintákkal találkoznak. A sablonok segítségével felügyelheti a webhely konzisztenciáját.

- Tökéletesítheti a keresőmotor optimalizálási (SEO) pontszámokat azáltal, hogy megismételhető és programozott módon meghatározott oldaldefiníciókat és metaadatokat biztosít.

> [!NOTE]
> Bár a sablonokat úgy tervezték, hogy a webhely konzisztenciáját felügyelni tudják, elméletileg konfigurálhatók úgy, hogy ne követeljék meg a konzisztenciát. A márkák és a webhelyek rendszergazdái bármilyen szintű változtathatóságot meghatározhatnak a webhely oldalain. Egy sablon például teljes egészében nyitott maradhat, így a tartalmi szerzők bármilyen általuk kiválasztott látványtervet létrehozhatnak. Ebben az esetben az előző listában szereplő előnyök egyike sem érvényes.

## <a name="modify-a-template"></a>Sablon módosítása

A sablonok a sablonszerkesztővel módosíthatók.

A sablonszerkesztő megnyitásához hajtsa végre a következő lépések valamelyikét:

- A webhely navigációs ablakában válassza ki a **Sablonok** lehetőséget, majd válassza ki a módosítani kívánt sablont.
- Egy meglévő lap lapszerkesztőjében válassza ki a felső csomópontot a bal oldali vázlatfában. Ezt követően a jobb oldali tulajdonságlapon válassza a **Sablon szerkesztése** elemet.

A bal oldali vázlatfa nézet a származtatott elrendezések és lapok számára elérhető modulbeállításokat és struktúrákat jeleníti meg. Amikor kiválaszt egy modult a vázlatában, a jobb oldalon látható tulajdonságlapon megtekintheti a kiválasztott modulhoz tartozó sablontulajdonságokat. Ezeknek a tulajdonságoknak egy része egyedi a sablon szerkesztéséhez. Az alábbi táblázatban található ezeknek a tulajdonságoknak az ismertetése.

| Tulajdonság neve | Leírás |
|---|---|
| Előfordulások minimális száma | Ez a tulajdonság határozza meg a kiválasztott modul előfordulásainak minimális számát. Ha például az érték **1-re** van állítva, akkor a későbbi szerzőknél a modul kötelező, míg ha az érték **0** (nulla), akkor a modul használata nem kötelező. |
| Előfordulások maximális száma | Ez a tulajdonság határozza meg a kiválasztott modul előfordulásainak maximális számát. Ha például az érték **1-re** van állítva, akkor a modul csak egyszerl adható hozzá. |
| Min. modulszám (tárolók) | A más modulokat tartalmazó modulok (azaz a *konténermodulok*) esetében ez a tulajdonság határozza meg, hogy a minimálisan hány modul legyen felvéve származtatott modulként. Egy körhinta modul esetében például ez az érték 1-nél nagyobb számra állítható be. |
| Max. modulszám (tárolók) | A tároló modulok esetében ez a tulajdonság határozza meg, hogy legfeljebb hány modul adható hozzá származtatottként. Egy körhinta modul esetében például ez az érték 10-nél kisebb számra állítható be. |
| Zárolva | A alapmodul összes tulajdonsága mellett megjelenik egy **Zárolt** logikai vezérlő. Ez lehetővé teszi azt, hogy a sablon szerzője zároljon egy modulbeállítást a sablonban. Egy zárolt modulbeállítást nem lehet felülbírálni a származtatott elrendezésekben vagy oldalakon. Ez egy központilag szerkeszthető tulajdonságérték lesz a sablont használó összes elrendezés és oldal számára. |

## <a name="create-a-new-template"></a>Új sablon létrehozása

Új sablon létrehozásához kövesse az alábbi lépéseket.

1. A webhely navigációs ablakában válassza ki a **Sablonok** lehetőséget a vizsgáló nézet megnyitásához
1. Válassza az **Új sablon** lehetőséget.
1. A sablon létrehozása párbeszédpanelen adja meg a sablon nevét és leírását. A megadott értékek megjelennek a szerzők számára új lapok létrehozásakor. Ennek megfelelően a szerzők számára hasznos metaadatokat adjon meg. Például írja be, hogy **Általános marketing lapokat marketingoldalakat hozzon létre ezzel a sablonnal** leírásként. Ezek a metaadatok később szerkeszthetők.
1. Kattintson az **OK** gombra az új sablon létrehozásához és a sablonszerkesztő megnyitásához. A sablon-szerkesztő bal oldalon egy fastruktúrát, a jobb oldalon pedig egy tulajdonság ablaktáblát jelenít meg.
1. A fastruktúrában bontsa ki a csomópontokat, majd válassza ki a **HTML-fejléc** tárolóhelyét.
1. Ha még nincsenek modulok ezen a helyen válassza a három pont gombot (**…**), majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza az **Alapértelmezett lapösszegzés** elemet, majd kattintson az **OK** gombra.
1. A fastruktúrában jelölje ki az új modult, majd a tulajdonság ablaktáblájában adja meg a sablon összes származtatott oldalához automatikusan konfigurálandó alapértelmezett beállításokat. Ha nem szeretne alapértelmezett beállításokat alkalmazni, hagyja üresen az értékeket.
1. A Vázlatablak válassza ki a **Törzs** helyét, válassza a három pont majd válassza a **Modul hozzáadása** elemet.
1. Válassza ki a lap tárolójának modulját (lehet, hogy csak egy lehetőség érhető el), majd válassza az **OK** gombot.

Az új oldal tároló modulban egy új bővítőhelykészlet látható (**Fejléc**, **Fő** stb.). Itt megadhatja és beállíthatja a szerzők számára elérhető modul-beállításokat, amikor ebből a sablonból lapokat hoznak létre. Ha egy bővítőhelyhez nem ad hozzá modult, akkor a rendszer alapértelmezés szerint az adott helyhez használható összes modultípust támogatja.

A sablon most technikailag érvényes, elmenthető, bejelölhető és az új lapok létrehozásához használható. A következő három szakasz azonban leírja azokat az alapértelmezett beállításokat, amelyeket előbb konfigurálni érdemes.

## <a name="add-a-header-and-a-footer"></a>Fejléc és lábléc felvétele

Ha a webhelyhez már tartozik fejléctöredék, akkor az alábbi lépésekkel lehet fejlécet és láblécet hozzáadni egy sablonhoz.

1. A fastruktúrában bontsa ki a **Szövegtörzs** helyet és származtatott lapmodulját.
1. Válassza ki **Fejléc** helyet.
1. Válassza ki a **Fejléc** helyhez tartozó három pont gombot, majd válassza a **Töredék hozzáadása** elemet.
1. Keresse meg és válassza ki a webhely fejléctöredékét, majd kattintson az **OK** gombra.

A sablont használó összes lap automatikusan örökli ezt a fejléctöredéket.

Ha a webhely még nem tartalmaz fejléctöredéket, akkor tekintse meg a [Töredék létrehozása](work-with-fragments.md#create-a-fragment) töredékek létrehozásával kapcsolatos további tudnivalókért, majd végezze el az előző eljárást.

## <a name="change-the-template-theme"></a>A sablontéma módosítása

A sablont használó összes lap alapértelmezett témájának beállításához hajtsa végre az alábbi lépéseket.

1. A bal oldali fastruktúrán bontsa ki a **Törzs** helyét.
1. Válassza ki a **Törzs** helyen a lap tárolóját (például **Alapértelmezett lap**).
1. Válasszon ki egy témát a jobb oldali tulajdonságok ablaktáblán a **Téma** mezőben.

Alapértelmezés szerint az összes új lap a kiválasztott témát fogja használni. Ha meg szeretné akadályozni, hogy az oldalak az elrendezés vagy a lap szintjén felülbírálják ezt a beállítást, állítsa a **Zárolt** logikai vezérlőelemet **Igaz** értékre.

## <a name="add-a-script-to-a-template"></a>Parancsfájl hozzáadása sablonhoz

A JavaScript-elemeket tartalmazó HTML **&lt;parancsfájlokat&gt;** is felvehet a sablonba. Ily módon alapértelmezett parancsfájl-viselkedéseket adhat meg a lapok HTML-fejléce, a szövegtörzs kezdete és a szövegtörzs vége számára.

Parancs hozzáadásához a sablonhoz tegye a következőket:

1. A bal oldali fastruktúrában válassza ki azt a helyet, amelyhez hozzá szeretné adni a **&lt;parancsfájl&gt;** elemét (például a HTML-fejléc, a törzs kezdete vagy a törzs vége).
1. Válassza ki a helyhez tartozó három pont gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válasszon ki egy parancsfájl-modult (Például **Külső parancsfájl** vagy **Beágyazott parancsfájl**).
1. Adja meg a parancsfájlt a jobb oldali tulajdonságok ablaktáblán a megfelelő parancsfájl-tulajdonság vezérlőnél (például **Beágyazott parancsfájl** vagy **Parancsfájl-címkék**), majd adja meg a parancsot.
1. A tulajdonságok ablaktáblában adja meg a konfigurálni kívánt egyéb választható beállításokat.

> [!TIP]
> Ha más sablonokhoz bármilyen parancsfájl-modult újra fel szeretne használni, akkor a töredékekké konvertálhatja őket. Ily módon hatékonyabbá teheti a szerkesztési folyamatot, illetve központosíthatja a frissítési folyamatot. Egy parancsfájlmodul töredékké történő konvertálásával kapcsolatos tudnivalókat lásd: [Meglévő modul-konfiguráció mentése töredékként](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Sablon mentése, beadása, előnézete és közzététele

Egy sablonként mentéséhez és beadásához kövesse az alábbi lépéseket.

1. A sablonszerkesztő felső részén válassza a **Mentés** parancsot. A mentett módosítások nem érintik az alsóbb szintű lapokat mindaddig, amíg nincsenek beadva.
1. Válassza a **Szerkesztés befejezése** lehetőséget. A módosítások most már felderíthetők az alsóbb szintű munkafolyamatok számára.

A módosítások előnézetéhez nyisson meg egy a sablont használó meglévő lapot, vagy hozzon létre egy új lapot a sablonból.

Miután megtekintette a sablon módosításainak előnézetét, kövesse az alábbi lépések egyikét, és tegye közzé a sablont az élő webhelyen:

* Nyissa meg a **Sablonokat** elemet, válasszon ki egy sablont, majd válassza a **Közzététel** parancsot.
* Az elrendezésszerkesztő megnyitásához válassza ki az elrendezés nevét, majd válassza a **Közzététel** lehetőséget.
* Egy nem közzétett sablonra hivatkozó lap közzététele. A sablon automatikusan közzé lesz téve.

> [!WARNING]
> Amikor a közzé lett téve egy sablon vagy más tartalomkezelő rendszer (CMS) elem, az az interneten felderíthető. Ne tegyen közzé dokumentumokat vagy eszközöket mindaddig, amíg készen nem áll azok nyilvánossá tételére. A mentett és beadott, de a nem közzétett dokumentumváltotok csak a hitelesített rendszerfelhasználók számára érhetők el.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Előre beállított elrendezések használata](work-with-layouts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
