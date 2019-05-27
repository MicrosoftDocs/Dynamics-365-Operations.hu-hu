---
title: Kisegítő lehetőségek funkciói
description: Ez a témakör azokat a funkciókat mutatja be, amelyek a különböző fogyatékkal élő felhasználókat segítik a Dynamics 365 for Finance and Operations, Dynamics 365 for Retail és Dynamics 365 for Talent szolgáltatások használatában.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: f88b485b0bdbf66532adff530e399bdd9d5b0ed5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565230"
---
# <a name="accessibility-features"></a>Hozzáférhetőségi funkciók

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat mutatja be, amelyek a különböző fogyatékkal élő felhasználókat segítik a Dynamics 365 for Finance and Operations, Dynamics 365 for Retail és Dynamics 365 for Talent szolgáltatások használatában. Bizonyos funkciók például azokat segítik, akik olyan, gyengénlátóknak kifejlesztett technológiákat használnak, mint a Microsoft Windows Narrátor.

## <a name="windows-narrator-and-keyboard-only-access"></a>A Windows Narrátor, és csak a billentyűzet elérése

Minden mező és vezérlő rendelkezik címkével, és a megfelelő parancsikonok leírásával. A képernyőolvasó képes a címke és a leírás felolvasására.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Billentyűparancsok a gyakran elvégzett műveletekhez

A legtöbb felhasználó számára a mindennapi rendszerhasználatnak része a rengeteg adatbevitel és billentyűzethasználat. A felhasználói élmény fokozása érdekében billentyűparancsokat hoztunk létre, amelyek segítenek „ugrálni” a képernyőn, valamint a speciális műveletekhez is létrehoztunk billentyűparancsokat. További információ: [Billentyűparancsok](shortcut-keys.md).

## <a name="navigation-search"></a>Navigációs keresés

A navigációs ablak menüből (a bal szélső ablak) elérhető lapok egyben a **Keresés** dobozban is elérhetők. Nyomja le az Alt + G billentyűkombinációt a fókusz áthelyezéséhez a **Keresés** mezőre, majd adja meg az oldal leírását vagy nevét.

![A keresési mezőbe beírt „bankszámlák”](media/6d08b0be32808221023e2aa92d69fd70.png "A keresési mezőbe beírt „bankszámlák”")

További információ: [Navigációs keresés](navigation-search.md).

> [!NOTE]
> Közvetlenül csak a legfelső szintű lapokra léphet. A másodlagos lapok a szülő lap adataira vagy kontextusára támaszkodnak.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Művelet keresése csak a billentyűzetet használó felhasználók számára vagy legördülő adatbevitelhez

Az oldalon megadott minden művelet elérhető a billentyűzetről, a TAB-sorrenden keresztül. A TAB-sorrenddel kapcsolatos információk a témakör későbbi részében találhatók. A műveletek közvetlenebb futtatásához használhatja a műveletkeresési funkciót.

### <a name="example"></a>Példa

Szeretné futtatni az **E-mail értesítési napló** műveletet, amely az **E-mail értesítés** csoportban jelenik meg az **Értékesítési rendelés** lapon a Művelet ablakban.

![E-mail értesítési napló művelete a műveleti ablakban](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "E-mail értesítési napló művelete a műveleti ablakban")

Az egyik lehetőség a billentyűzet használata. Nyomja le a Ctrl+F6 billentyűkombinációt a fókusz Művelet ablakra állításához, és nyomja le a TAB gombot többször a váltáshoz a lapok és a műveletek között, amíg az **E-mail értesítési napló** műveletre nem kerül a fókusz.

Azonban a műveletet közvetlenebből is futtathatja. A lap tetszőleges pontján nyomja le a Ctrl+aposztróf (') kombinációt a műveletek keresőmezőjének megjelenítéséhez.

![Keresőmező műveletekhez](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Keresőmező műveletekhez")

A keresőmezőbe írja be a szöveget, amely leírja a műveletet. A művelet ekkor elérhetővé válik, és közvetlenül futtatható. Például az **e-mail**, az **értes** (részleges szó) vagy **napló** beírásával az E-mail értesítési naplóhoz „ugorhat”.

![A keresési mezőbe beírt „e-mail”](media/image4.png "A keresési mezőbe beírt „e-mail”")

![A keresési mezőbe beírt „notific”](media/image5.png "A keresési mezőbe beírt „notific”")

![A keresési mezőbe beírt „napló”](media/image6.png "A keresési mezőbe beírt „napló”")

Amikor elkészült, ismét megnyomhatja a Ctrl+aposztróf kombinációt, és a fókusz visszatér a mezőre, amellyel a műveletkeresés futtatása előtt dolgozott.

További információ: [Műveletkeresés](action-search.md).

## <a name="tab-sequence"></a>TAB-sorrend

Nem minden mezőre van szükség a mindennapi rendszerhasználat során annak érdekében, hogy végrehajtsa a tipikus feladatokat. Ezért alapértelmezés szerint a sorozat „optimalizált”. A tabulátor csak azokon a mezőkön áll meg, amelyek elengedhetetlenek a tipikus esetekhez.

Előfordulhat azonban, hogy egyes, feladatai végrehajtásához gyakran használt mezők nem szerepelnek az alapértelmezett TAB-sorrendben. Ebben az esetben, ha a Windows Narrátort használja, a Windows Narrátor billentyűzetműveletei segítségével érheti el ezeket a mezőket, és vizsgálhatja meg a tartalmukkal. Azt is megteheti, hogy bekapcsolja a **Továbbfejlesztett TAB-sorrend** beállítást a **Beállítások** lapon. A beállítás minden szerkeszthető és csak olvasható mezőt a TAB-sorrend részévé tesz. Ezt követően a lap személyre szabását használhatja egyéni sorrend létrehozásához, és kihagyhatja a mezőket, amelyeknek nem kell a TAB-sorrend részének lenniük. A személyre szabással kapcsolatos további tudnivalókat lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

![„Továbbfejlesztett lapsorozat” beállítás](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "„Továbbfejlesztett lapsorozat” beállítás")

## <a name="form-patterns"></a>Űrlapminták

A termék lapjainak közel 90%-a minták kis készletére alapul. Ezeket a mintákat nevezik *űrlapmintáknak*. Minden űrlapminta azoknak a műveleteknek a megadására szolgál, amelyeket az oldalon a leggyakrabban hajtanak végre. Az űrlapminta segít garantálni az ismerősséget és a könnyű érthetőséget, mivel a gyakran használt műveletek és adatok mindig ugyanazon a helyen jelennek meg a különböző lapokon. Az űrlapminták kis száma miatt a felhasználók egyszerűen tanulhatják meg a rendszer működését, függetlenül attól, hogy hány oldalt tartalmaz, és magabiztosan használhatják, miután felismerik az űrlapmintákat.

Az űrlapmintákkal kapcsolatos további tudnivalókért lásd: [Stílusok és minták formázása](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Igényekre reagáló elrendezés

A terméket úgy tervezték, hogy különböző eszközökön és képernyőméretek mellett is működjön, a legkisebb képernyőtől a legnagyobb, legnagyobb felbontású képernyőkig. Az igényekre reagáló elrendezési motornak köszönhetően a felhasználók akár a 200%-os nagyítást is választhatják (bizonyos esetekben több mint 200%-os nagyítás is lehetséges).

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Útmutatás a fejlesztők és a vevők számára a könnyű kezelhetőség koncepciójának beépítéséhez a testreszabásaikba

A kisegítő lehetőségekkel kapcsolatos legjobb Microsoft-gyakorlatokkal kapcsolatos további tudnivalókért lásd: [Űrlapok, termékek és vezérlők hozzáférhetősége](../../dev-itpro/user-interface/enable-accessibility.md).
