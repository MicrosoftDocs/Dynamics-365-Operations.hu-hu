---
title: Díjszabási funkciók a pénztárban
description: Ez a cikk a pénztár Microsoft Dynamics 365 Commerce alkalmazás különböző ár- és engedményfunkcióit ismerteti.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473687"
---
# <a name="pricing-functions-in-pos"></a>Díjszabási funkciók a pénztárban

[!include [banner](includes/banner.md)]

Ez a cikk a pénztár Microsoft Dynamics 365 Commerce alkalmazás különböző ár- és engedményfunkcióit ismerteti.

A Dynamics 365 Commerce POS alkalmazás olyan funkciókat kínál, amelyek lehetővé teszik az első sorban dolgozó alkalmazottak számára az üzleti tevékenységek elvégzését. Az alábbi táblázat bemutatja az alkalmazásban jelenleg elérhető ár- és engedményfunkciókat.

| Függvény                       | Pénztári műveletek |
|--------------------------------|----------------|
| Árak megtekintése                    | [Árkeresés](#price-check) |
| Engedmények megtekintése                 | [Összes engedmény megtekintése](#view-all-discounts)<br>[Rendelkezésre álló engedmények megtekintése](#view-available-discounts) |
| Árak felülbírálása                | [Ár felülbírálása](#price-override) |
| Engedmények alkalmazása vagy eltávolítása      | [Sorengedmény összege](#line-discount-amount)<br>[Sorengedmény százaléka](#line-discount-percent)<br>[Teljes engedmény összege](#total-discount-amount)<br>[Teljes engedmény (százalék)](#total-discount-percent)<br>[Rendszerengedmények eltávolítása a tranzakcióból](#remove-system-discounts-from-transaction)<br>[Rendszerengedmények újbóli alkalmazása](#reapply-system-discounts) |
| Utalványok alkalmazása vagy eltávolítása        | [Utalványkód hozzáadása](#add-coupon-code)<br>[Utalványkód eltávolítása](#remove-coupon-code) |
| Árak és engedmények számítása | [Újraszámítás](#recalculate) |

Az előző műveletek pos-alkalmazásban történő konfigurálásával és az offline [mód támogatásával kapcsolatos tudnivalókat lásd az Online és offline point of sale (POS) műveletekben](pos-operations.md).

## <a name="price-check"></a>Árkeresés

Az **Árellenőrzés** művelet lehetővé teszi a POS-felhasználók számára, hogy meghatározott termék előre beállított árait keressenek.

## <a name="view-all-discounts"></a>Összes engedmény megtekintése

Az **"Összes engedmény megtekintése** " művelet lehetővé teszi a POS-felhasználók számára, hogy ki keressenek minden olyan hatályos promóciót, amely jelenleg az üzlet csatornájában fut. Ez a művelet különösen az alábbi feltételeknek megfelelő engedményeket sorolja fel:

- Az engedmény árcsoportja megfelel az üzlet árcsoportjának.
- A kedvezményhez tartozó árcsoport hozzá van rendelve egy fiók- vagy hűségprogramhoz.
- Az engedmény árcsoportja az üzlethez társított egy katalógushoz van rendelve.

Az **Összes engedmény megtekintése** művelet csak azokat az engedményeket mutatja, amelyek nem versenyzők a már alkalmazott engedményekkel. Ez a viselkedés segít abban, hogy ha egy értékesítési munkatárs értesíti a vevőt a kedvezményről, és a vevő a szükséges lépést hajtja végre (például a vevő még egy cikket vásárol, hogy 10% kedvezményt kapjon), akkor az engedmény alkalmazva legyen a tranzakcióra. Az utalvány alapú engedmények csak akkor jelennek meg, ha **az Alkalmazás az** utalványkód nélkül paraméter be van kapcsolva.

A POS-felhasználók az összes **engedmény** megtekintése műveleten belül név és leírás szerint kereshetnek engedményeket, és az engedményeket annak alapján szűrhetik, hogy kell-e engedményt igényelni.

## <a name="view-available-discounts"></a>Rendelkezésre álló engedmények megtekintése

Az **Elérhető engedmények** megtekintése művelet lehetővé teszi a POS-felhasználók számára, hogy megtekintsék a tranzakció egy kiválasztott sorában vagy a teljes tranzakcióban érvényes összes engedményt. A kiválasztott sorra vonatkozó engedmények tartalmazzák a már alkalmazott engedményeket és az olyan engedményeket, amelyek még nincsenek alkalmazva, de alkalmazhatók (például a kombinációs engedmények, amelyek további cikkeket igényelnek). **Ha** egy olyan utalványhoz kapcsolódik alkalmazható engedmény, amelyben be van kapcsolva az Alkalmazás az utalványkód nélkül paraméter, a POS **felhasználó** az utalvány közvetlen beváltása érdekében használhatja az Utalvány alkalmazása funkciót, anélkül, hogy bármilyen utalványkódot vagy utalvány-vonalkódot be lenne olvasni vagy be kell olvasnia.

## <a name="price-override"></a>Ár felülbírálása

Az **Ár-felülbírálási** művelet lehetővé teszi a POS-felhasználók számára, hogy felülírják egy tranzakcióban érintett termék eladási árát. Ez a művelet csak olyan termékek esetén működik, amelyeknél az árfelül felülbírálható.

## <a name="line-discount-amount"></a>Sorengedmény összege

A **Sorengedmény összege művelet** lehetővé teszi a POS-felhasználók számára, hogy engedményt adjanak meg egy tranzakció sortételére. Ez a művelet csak olyan leszámolható cikkekre vonatkozik, **amelyeknél** a maximális sorengedményösszeg van megadva a felhasználó POS-engedélycsoportja szerint.

## <a name="line-discount-percent"></a>Sorengedmény százaléka

A sorengedmény **százalékos művelete** lehetővé teszi a POS-felhasználók számára, hogy tranzakció sortételére engedményszázalékot adjanak meg. Ez a művelet csak az olyan cikkekre vonatkozik, amelyeknél kedvezményt lehet alkalmazni, **és** a felhasználó POS-engedélycsoportja által meghatározott maximális sorengedmény százalékos értékét jelenti.

## <a name="total-discount-amount"></a>Teljes engedmény összege

Az **Összengedmény összege művelet** lehetővé teszi a POS-felhasználók számára, hogy engedményösszeget adjanak meg egy tranzakcióhoz. Ez a művelet csak a leszámolható cikkekre vonatkozik, **és** a felhasználó POS-engedélycsoportja által meghatározott maximális teljes engedményösszegre vonatkozik. Ha a megadott engedményösszeg meghaladja a maximális teljes engedményösszeget, a művelet zárolva van, és nem történik engedély-felülbírálási folyamat. Jelenleg nem lehet teljes engedményt alkalmazni olyan kosárra, amelyben vegyes értékesítési cikkek és visszáru cikkek vannak.

## <a name="total-discount-percent"></a>Teljes engedmény (százalék)

Az Összengedményszázalék **művelet** lehetővé teszi a POS-felhasználók számára, hogy engedményszázalékot adjanak meg egy tranzakcióhoz. Ez a művelet csak az olyan cikkekre vonatkozik, amelyeknél kedvezményt lehet alkalmazni, **és** a felhasználó POS-engedélycsoportja által meghatározott maximális teljes százalékos engedményértékre vonatkozik. Ha a megadott engedményszázalék meghaladja a maximális teljes engedményszázalékot, a művelet zárolva van, és nem történik engedély-felülbírálási folyamat. Jelenleg a teljes százalékos engedmény nem alkalmazható olyan kosárra, amelynél vegyes az értékesítési és a visszáru.

## <a name="remove-system-discounts-from-transaction"></a>Rendszerengedmények eltávolítása a tranzakcióból

A Rendszerengedmények **eltávolítása a tranzakciós** műveletből beállítás segítségével a POS-felhasználók törölhetnek minden alkalmazott rendszerengedményt (beleértve az utalvány alapú engedményeket is) a tranzakcióból. A művelet után az árképzési motor megkezdi a rendszerengedmények kizárását az engedményszámítás hatókörébe. A Rendszerengedmények **eltávolítása tranzakciós műveletből** nem távolítja el a manuális engedményeket.

## <a name="reapply-system-discounts"></a>Rendszerengedmények újbóli alkalmazása

A **rendszerengedmények újraalkalmazása** művelet lehetővé teszi a POS-felhasználók számára, hogy rendszer által kiszámított engedményeket vegyenek fel egy tranzakcióra, ha az **engedményeket** a Rendszerengedmények eltávolítása tranzakciós műveletből való eltávolításával eltávolította. A művelet után az árképzési motor megkezdi az összes rendszerengedmény beszámítását az engedményszámítás hatókörébe.

## <a name="add-coupon-code"></a>Utalványkód hozzáadása

Az Utalványkód **hozzáadása** művelet lehetővé teszi a POS-felhasználók számára, hogy utalványt adjanak hozzá egy tranzakcióhoz egy utalványkód megadásával. Másik lehetőségként a **POS-felhasználók beolvashat egy utalvány vonalkódját, vagy beírhatják azt a Tranzakciók képernyőn numerikus billentyűzet** használatával.

## <a name="remove-coupon-code"></a>Utalványkód eltávolítása

Az Utalványkódok **eltávolítása** művelet lehetővé teszi a POS-felhasználók számára, hogy ki válasszanak és távolítsanak el egy vagy több olyan utalványt, amely jelenleg egy tranzakcióra vonatkozik.

## <a name="recalculate"></a>Újraszámítás

Az **Újraszámítás művelet** lehetővé teszi a POS-felhasználók számára az igény szerinti árképzés kiszámítását. Erre a műveletre akkor van szükség, ha engedélyezve van az árzárolás és/vagy a késleltetett árszámítás, és a POS-felhasználó a bevásárlókocsi vagy a rendelés változtatása után újra szeretné számítani az árakat és az engedményeket. Az **Újraszámítási** művelet mindig újraszámul a teljes rendelésre. A kiválasztott értékesítési sorok újraszámításakor nem használható. Ahhoz, hogy manuális engedményeket alkalmazzanak egy zárolt értékesítési sorra a POS-ban, **a** POS-felhasználóknak az összes értékesítési sor zárolásának feloldásához az Újraszámítás műveletet kell használniuk.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
