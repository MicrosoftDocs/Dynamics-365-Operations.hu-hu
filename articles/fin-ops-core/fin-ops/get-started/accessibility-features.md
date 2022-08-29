---
title: Kisegítő lehetőségek funkciói
description: Ez a témakör a különböző fogyatékkal élőknek nyújt segítséget nyújtó funkciókat ismerteti.
author: jasongre
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 4e6a077cc7848448233ed5f94f9b1ba5b385c3fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284023"
---
# <a name="accessibility-features"></a>Kisegítő lehetőségek funkciói

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek segítik a különböző fogyatékkal élőket az alkalmazás használatában. Bizonyos funkciók például azokat segítik, akik olyan, gyengénlátóknak kifejlesztett technológiákat használnak, mint a Microsoft Windows Narrátor.

## <a name="windows-narrator-and-keyboard-only-access"></a>A Windows Narrátor, és csak a billentyűzet elérése

Minden mező és vezérlő rendelkezik címkével, és a megfelelő parancsikonok leírásával. A képernyőolvasó képes a címke és a leírás felolvasására.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Billentyűparancsok a gyakran elvégzett műveletekhez

A legtöbb felhasználó számára a mindennapi rendszerhasználatnak része a rengeteg adatbevitel és billentyűzethasználat. A felhasználói élmény fokozása érdekében billentyűparancsokat hoztunk létre, amelyek segítenek „ugrálni” a képernyőn, valamint a speciális műveletekhez is létrehoztunk billentyűparancsokat. További információ: [Billentyűparancsok](shortcut-keys.md).

## <a name="navigation-search"></a>Navigációs keresés

A navigációs ablak menüből (a bal szélső ablak) elérhető lapok egyben a **Keresés** dobozban is elérhetők. Nyomja le az Alt + G billentyűkombinációt a fókusz áthelyezéséhez a **Keresés** mezőre, majd adja meg az oldal leírását vagy nevét.

![„Bankszámlák” megadva a Keresés mezőben](media/6d08b0be32808221023e2aa92d69fd70.png "„bankszámlák” megadva a Keresés mezőben")

További információ: [Navigációs keresés](navigation-search.md).

> [!NOTE]
> Közvetlenül csak a legfelső szintű lapokra léphet. A másodlagos lapok a szülő lap adataira vagy kontextusára támaszkodnak.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Művelet keresése csak a billentyűzetet használó felhasználók számára vagy legördülő adatbevitelhez

Az oldalon megadott minden művelet elérhető a billentyűzetről, a TAB-sorrenden keresztül. A lapsorozatról később ebben a cikkben olvashat tájékoztatást. A műveletek közvetlenebb futtatásához használhatja a műveletkeresési funkciót.

### <a name="example"></a>Példa

Szeretné futtatni az **E-mail értesítési napló** műveletet, amely az **E-mail értesítés** csoportban jelenik meg az **Értékesítési rendelés** lapon a Művelet ablakban.

![E-mail-értesítési napló művelete a Művelet panelen.](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "„E-mail-értesítési napló” művelete a Művelet panelen")

Az egyik lehetőség a billentyűzet használata. Nyomja le a Ctrl+F6 billentyűkombinációt a fókusz Művelet ablakra állításához, és nyomja le a TAB gombot többször a váltáshoz a lapok és a műveletek között, amíg az **E-mail értesítési napló** műveletre nem kerül a fókusz.

Azonban a műveletet közvetlenebből is futtathatja. A lap tetszőleges pontján nyomja le a Ctrl+aposztróf (') kombinációt a műveletek keresőmezőjének megjelenítéséhez.

![Műveletek keresőmezője.](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Műveletek keresőmezője")

A keresőmezőbe írja be a szöveget, amely leírja a műveletet. A művelet ekkor elérhetővé válik, és közvetlenül futtatható. Például az **e-mail**, az **értes** (részleges szó) vagy **napló** beírásával az E-mail értesítési naplóhoz „ugorhat”.

![„E-mail” megadva a keresőmezőben](media/image4.png "„e-mail” megadva a keresőmezőben")

![„Értes” megadva a keresőmezőben](media/image5.png "„értes” megadva a keresőmezőben")

![„Napló” megadva a keresőmezőben](media/image6.png "„napló” megadva a keresőmezőben")

Amikor elkészült, ismét megnyomhatja a Ctrl+aposztróf kombinációt, és a fókusz visszatér a mezőre, amellyel a műveletkeresés futtatása előtt dolgozott.

További információ: [Műveletkeresés](action-search.md).

## <a name="tab-sequence"></a>TAB-sorrend

Nem minden mezőre van szükség a mindennapi rendszerhasználat során annak érdekében, hogy végrehajtsa a tipikus feladatokat. Ezért alapértelmezés szerint a sorozat „optimalizált”. A tabulátor csak azokon a mezőkön áll meg, amelyek elengedhetetlenek a tipikus esetekhez.

Előfordulhat azonban, hogy egyes, feladatai végrehajtásához gyakran használt mezők nem szerepelnek az alapértelmezett TAB-sorrendben. Ebben az esetben, ha a Windows Narrátort használja, a Windows Narrátor billentyűzetműveletei segítségével érheti el ezeket a mezőket, és vizsgálhatja meg a tartalmukkal. Azt is megteheti, hogy bekapcsolja a **Továbbfejlesztett TAB-sorrend** beállítást a **Beállítások** lapon. A beállítás minden szerkeszthető és csak olvasható mezőt a TAB-sorrend részévé tesz. Ezt követően a lap személyre szabását használhatja egyéni sorrend létrehozásához, és kihagyhatja a mezőket, amelyeknek nem kell a TAB-sorrend részének lenniük. A személyre szabással kapcsolatos további tudnivalókat lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

![„Továbbfejlesztett TAB-sorrend” beállítás](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "„Továbbfejlesztett TAB-sorrend” beállítás")

## <a name="form-patterns"></a>Űrlapminták

Az alkalmazás lapjainak közel 90%-a minták kis készletére alapul. Ezeket a mintákat nevezik *űrlapmintáknak*. Minden űrlapminta azoknak a műveleteknek a megadására szolgál, amelyeket az oldalon a leggyakrabban hajtanak végre. Az űrlapminta segít garantálni az ismerősséget és a könnyű érthetőséget, mivel a gyakran használt műveletek és adatok mindig ugyanazon a helyen jelennek meg a különböző lapokon. Az űrlapminták kis száma miatt a felhasználók egyszerűen tanulhatják meg a rendszer működését, függetlenül attól, hogy hány oldalt tartalmaz, és magabiztosan használhatják, miután felismerik az űrlapmintákat.

Az űrlapmintákkal kapcsolatos további tudnivalókért lásd: [Stílusok és minták formázása](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Igényekre reagáló elrendezés

A terméket úgy tervezték, hogy különböző eszközökön és képernyőméretek mellett is működjön, a legkisebb képernyőtől a legnagyobb, legnagyobb felbontású képernyőkig. Az igényekre reagáló elrendezési motornak köszönhetően a felhasználók akár a 200%-os nagyítást is választhatják (bizonyos esetekben több mint 200%-os nagyítás is lehetséges).

Okostelefonokon és más kis képernyővel rendelkező eszközökön a vezérlőelemek és az űrlap elrendezése reszponzívan igazodik, hogy biztosítsa az alapadatok elsőbbségét. Ezek a rugalmas viselkedések magukban foglalhatják a csoportokban és lapokon lévő oszlopok számának csökkentését is egyetlen oszlopra, a rendszerhéj elemeinek elrejtésérét és a műveleti panel összecsukását.

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Útmutatás a fejlesztők és a vevők számára a könnyű kezelhetőség koncepciójának beépítéséhez a testreszabásaikba

A kisegítő lehetőségekkel kapcsolatos legjobb Microsoft-gyakorlatokkal kapcsolatos további tudnivalókért lásd: [Űrlapok, termékek és vezérlők hozzáférhetősége](../../dev-itpro/user-interface/enable-accessibility.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
