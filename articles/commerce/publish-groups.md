---
title: A közzétételi csoportokkal végzett munka
description: Ez a témakör a Microsoft Dynamics 365 Commerce közzétételi csoportok funkciójával foglalkozik.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d757f34d3e16850e4f5de122f63b2b3342f612e49f07c7cf6585362999f03c02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717672"
---
# <a name="work-with-publish-groups"></a>A közzétételi csoportokkal végzett munka

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce közzétételi csoportok funkciójával foglalkozik.

Az e-kereskedelmi webhelyeket egész évben folyamatosan frissítik új tartalmakkal. A frissítéseket leggyakrabban kötegelve teszik közzé zsúfolt e-kereskedelmi események környékén, mint ünnepek, szezonális marketingkampányok vagy promóciós bevezetések. Ezek a frissítések gyakran megkívánják a webhelytartalmak csoportjainak (példák, képek, töredékek és sablonok) előkészítését, ellenőrzését és közzétételét egyszerre, egyetlen műveletben.

A cikkek logikai halmazokba való csoportosítása, amellyel a cikkek együtt tehetők közzé, és a halmazok saját életciklussal rendelkeznek, számos előnyt biztosíthat a webhelykészítők számára. A Commerce alkalmazásban ezeket a logikai halmazokat közzétételi csoportoknak nevezzük. Ezek segítségével a webhelykészítők a frissítések csoportjait nyomon követhetik, mint saját konfigurálható, tesztelhető és közzétehető entitásokat.

A készítők megtekinthetik a frissítéseket előkészített közzétételi csoportokban anélkül, hogy befolyásolnák az élő webhelyet, vagy más önálló közzétételi csoportokat. A készítők ezután úgy ütemezhetik a közzétételi műveletet, hogy a közzétételi csoportban levő összes cikket egyszerre tegye közzé az élő webhelyre. A közzétételi frissítések csoportosítására, előnézetére és ütemezésére vonatkozó képesség számos nagyvállalati szintű vállalat számára fontos, amelyek az éves bevétel jelentős részét termelik meg az eseményalapú webhelyfrissítési mérföldkövek körül.

A vállalatoknál költségek merülhetnek fel a lassú vagy nem ellenőrzött tartalombevezetések során, amelyek nem zökkenőmentesen történnek. A közzétételi csoportokkal könnyebben garantálható, hogy a bevezetések szervezetten és ellenőrzötten, időben kerülnek közzétételre. Lehetnek nagyok vagy kicsik, a közzétételi csoportok értékes eszközkészletet biztosítanak, amellyel a készítők a rendszerezhetik és egyszerűsíthetik a folyamatos webhelyfrissítési feladatokat.

## <a name="when-to-use-publish-groups"></a>Mikor kell használni a közzétételi csoportokat?

A közzétételi csoportokat bármikor használhatja, amikor több dokumentumot együtt szeretne előkészíteni és közzétenni. Ha például a webhely minden évszakban frissíti a tartalmakat, akkor a szezonális marketingakciókhoz létrehozhat közzétételi csoportokat. Az „Őszi szezonális frissítés” közzétételi csoport tartalmazhat új szezonális képeket és töredékeket, amelyek szezonális marketingüzeneteket tartalmaznak, oldalakat, amelyeken szezonális termékgyűjtemények szerepelnek, vagy más szezonális webhelyfrissítéseket.

A közzétételi csoportok előnye, hogy párhuzamosan több frissítést is létrehozhat. Például röviddel az „Őszi szezonális frissítés” közzétételi csoport frissítése után lehet egy tartalomfrissítés egy specifikus ünnepli hétvégéhez. Ebben az esetben egyidőben előkészítheti az „Őszi szezonális frissítés” közzétételi csoport tartalmát, ahogy előkészíti az azt követő „Őszi ünnepi frissítés” közzétételi csoportot. Minden egyes közzétételi csoport tartalmazza az oldalak, képek, töredékek, sablonok stb. saját halmazát. Ezt a két csoportot egymástól függetlenül, de párhuzamos idővonalon készítheti elő, tekintheti meg előnézetüket és ellenőrizheti őket. Ezután minden egyes közzétételi csoport ütemezhető, így adott napokon és időpontokban közzéteheti őket a webhelyen.

## <a name="turn-on-the-publish-groups-feature"></a>A közzétételi csoportok funkció bekapcsolása

A közzétételi csoportok funkció választható, és be kell kapcsolnia webhelyéhez.

Ha be szeretné kapcsolni a webhely közzétételi csoportok funkcióját a Commerce létrehozási eszközökben, hajtsa végre az alábbi lépéseket.

1. A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.
1. A **Webhelybeállítások** részben válassza a **Funkciók** lehetőséget.
1. Állítsa a **Közzétételi csoportok** beállítást **Be** értékre.

## <a name="create-a-publish-group"></a>Közzétételi csoport létrehozása

Ha létre szeretne hozni egy közzétételi csoportot webhelyéhez a Commerce létrehozási eszközökben, hajtsa végre az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Közzétételi csoportok** lehetőséget.
1. A felső parancssávon válassza az **Új** elemet.
1. A **közzétételi csoport létrehozása** párbeszédpanelben a **Közzétételi csoport neve** részben adjon meg egy leíró nevet. Majd kattintson az **OK** lehetőségre.

## <a name="set-the-publish-group-authoring-context"></a>A közzétételi csoport készítői környezetének beállítása

A Commerce szolgáltatásban az alapértelmezett készítői környezete az élő webhelykörnyezet. Az élő webhelykészítési környezet az alapértelmezett nézet, ahol megtekintheti a webhelyet, és közvetlenül módosíthatja közzétételi csoport használata nélkül. Ez a webhely közzétett verziójának legújabb közvetlen frissítéseit képviseli. Ha a bal oldali navigációs panelben található **Közzétételi csoportok** részben szereplő környezetvezérlő az **Élő webhely** nevet mutatja, akkor az élő webhelyszerkesztési környezetben dolgozik. Az **Élő webhely** a környezetvezérlő alapértelmezett neve. Ellenkező esetben a környezetvezérlő megjeleníti a közzétételi csoport nevét.

A közzétételi csoportban való munkához át kell váltania a közzétételi csoport szerzői környezetére. A közzétételi csoport környezetének beállításához kövesse az alábbi lépések egyikét.

- A bal oldali navigációs ablaktáblában jelölje ki közvetlenül a **Közzétételi csoportok** részben szereplő környezetvezérlőt, majd a megjelenő beállításlistában a közzétételi csoport nevét. A környezetvezérlő neve megváltozik, és a közzétételi csoport nevét mutatja.
- A bal oldali navigációs panelben válassza a **Közzétételi csoportok** elemet, majd a **Közzétételi csoportok** részben a közzétételi csoport nevét. A környezetvezérlő neve megváltozik, és a közzétételi csoport nevét mutatja.

A közzétételi csoport szerzői környezetének beállítása után az adott közzétételi csoport környezetében dolgozik, amikor megtekinti és szerkeszti a webhely tartalmát.

Ha vissza szeretne térni az alapértelmezett élő webhelykészítési környezethez, jelölje ki a környezetvezérlőt, majd válassza az **Élő webhely** beállítást.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Oldalak és más elemek hozzáadása egy közzétételi csoporthoz

Miután kiválasztotta a közzétételi csoport szerkesztési környezetét, és a bal oldali navigációs panelben található környezetvezérlő ennek nevét jeleníti meg, akkor pont úgy hozhat létre tartalmakat, mint az alapértelmezett élő webhelykörnyezetben. Más közzétételi csoportokból vagy az élő webhelykörnyezetből is hozzáadhat meglévő oldalakat és más elemeket.

A meglévő oldalak közzétételi csoportba való másolásához hajtsa végre az alábbi lépéseket.

1. Jelölje ki azt a tartalomkészítési környezetet, amelyből másolni szeretne, majd a bal oldali navigációs ablaktáblán jelölje ki az **oldalak** lapot.
1. Jelölje ki a közzétételi csoporthoz hozzáadni kívánt oldalt.
1. A parancssávon válassza a **másolás a közzétételi csoportba** parancsot .
1. A **közzétételi csoport kiválasztása** párbeszédpanelen jelölje ki a közzétételi csoportot, amelyhez az oldalt hozzá szeretné adni, majd kattintson az **OK** gombra.

Ugyanazokat az alapvető lépéseket használhatja testreszabott termékoldalak, URL-címek, sablonok, elrendezések, töredékek és médiatárban lévő eszközök létrehozására, illetve az ilyen típusú meglévő elemek hozzáadására egy közzétételi csoporthoz.

## <a name="validate-a-publish-group"></a>Közzétételi csoport ellenőrzése

Ha meg szeretné győződni arról, hogy a közzétételi csoport tartalmának összes függősége teljesül-e, és hogy minden ellenőrzésnek megfelel-e, akkor az ellenőrzés futtatásával azonosíthatja azokat a problémákat, amelyeket a közzétételi művelet ütemezése előtt meg kell oldani.

A közzétételi csoport ütemezés előtti ellenőrzéséhez kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Közzétételi csoportok** lehetőséget.
1. Jelölje ki az ellenőrizni kívánt közzétételi csoportot.
1. A felső parancssávon válassza az **Ellenőrzés** elemet.

Az ellenőrzést a közzétételi csoport összes tartalmán futtatva lesz. Minden olyan probléma, amely megakadályozza a sikeres közzétételi műveletet, a jobb felső sarokban megjelenő értesítési mezőben jelenik meg.

> [!NOTE]
> Az ellenőrzés a közzétételi csoportok ütemezésekor mindig automatikusan fut. Azonban a parancssávban található **Ellenőrzés** gomb azért hasznos, mert segít azonosítani azokat a problémákat, amelyeket ki kell javítani, mielőtt egy közzétételi csoportot ütemezhetne az élő közzétételhez.

## <a name="schedule-a-publish-group-to-go-live"></a>Közzétételi csoport ütemezése éles közzétételre

Az alábbi lépéseket követve ütemezhet egy közzétételi csoportot éles közzétételre a webhelyén.

1. A bal oldali navigációs ablakban válassza ki a **Közzétételi csoportok** lehetőséget.
1. A **Közzétételi csoportok** alatt válassza ki az ütemezni kívánt közzétételi csoportot.
1. A felső parancssávon válassza az **Ütemezés szerkesztése** elemet. Megjelenik az **Ütemezés szerkesztése** párbeszédpanel.
1. Válassza ki azt a dátumot és időpontot, amikor a közzétételi csoportnak élesen kell indulnia, majd kattintson az **OK** gombra.

A közzétételi csoport ütemezésének törléséhez kövesse ugyanezeket a lépéseket, de válassza a **Közzétételi csoport ütemezésének törlése** lehetőséget az **Ütemezés szerkesztése** párbeszédpanelen.

> [!NOTE]
> Nagyon nagy közzétételi csoportok esetében a közzététel egy-két percig is eltarthat, amikor elérik az ütemezett időt. Ne feledje, hogy a közzétételi művelet nem azonnali, és a kisebb közzétételi csoportok gyorsabban közzétehetők.

## <a name="publish-groups-faq"></a>Közzétételi csoport GYIK

**Hány elem lehet egy közzétételi csoportban?**

Jelenleg közzétételi csoportonként 2 000 cikkes korlát van érvényben. Ne feledje, hogy nagyon nagy közzétételi csoportok esetében a közzététel több percig is eltarthat, amikor elérik az ütemezett időt.

**A közzétételi csoportok olyanok mint a kód „ágai” a szoftverfejlesztési terminológiában?**

Igen és nem. A közzétételi csoportok felfoghatók a webhely elágazott verzióiként. Ebben a tekintetben ágakként funkcionálnak. Azonban az egyesítés fogalma hiányzik az egyes tételek szintjén. Az utolsó közzétett elem csak felülírja a korábban létezőt, és a legutóbbi közzététel művelet mindig hatálytalanítja a korábbi közzétételi műveleteket.

**Lehet-e egyszerre két közzétételi csoportot ütemezni?**

Szám Teljesítmény- és ütközési szempontok miatt a rendszer arra kényszeríti, hogy szakaszosan ütemezze a közzétételi csoportokat, legalább öt perc különbséggel.

**Használhatók a közzétételi csoportok omnicsatorna háttérirodai cikkek, például kedvezmények és termékfrissítések ütemezésére?**

Jelenleg, a közzétételi csoportok funkció csak webhelytartalmat támogat. A Microsoft azonban tisztában van azzal, hogy a háttérirodai értékesítési forgatókönyvekkel való integráció értékes lehet az omnicsatorna-kampánybemutatók koordinálásához és automatizálásához.

## <a name="additional-resources"></a>További erőforrások

[A tartalom hozzáadásának módjai](add-manage-content.md)

[Oldal modellszószedete](page-elements-overview.md)

[Állapotok és életciklus-dokumentálás](document-states-overview.md)

[Csatornaközi megosztás engedélyezése és használata](cross-channel-sharing.md)

[Modulok használata](work-with-modules.md)

[Töredékek használata](work-with-fragments.md)

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Webhely-navigáció testreszabása](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
