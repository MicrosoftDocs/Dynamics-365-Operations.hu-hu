---
title: Újdonságok és változások a Warehouse Management mobilalkalmazásban
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új és módosult funkcióit ismerteti.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261780"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Újdonságok és változások a Warehouse Management mobilalkalmazásban

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új funkcióit, hibajavításait, fejlesztéseit és ismert hibáit ismerteti.

## <a name="version-2060"></a>2.0.6.0-s verzió

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Új funkciók, hibajavítások és fejlesztések a 2.0.6.0 verzióban

Ez a kiadás az alábbi új funkciókat, hibajavításokat és fejlesztéseket tartalmazza:

- A Bemutató módban mostantól az összes címke az eszköz nyelvén jelenik meg.
- Kevésbé valószínű, hogy megjelenik a következő hibaüzenet: „A megadott mérethez nem található megfelelő nézet”.
- A munkakártyák minimális magassága megnőtt (azokban az esetekben, amikor legfeljebb három mező van beállítva a munkalistában való megjelenésre).
- A részletkártyák alján található margókat (elhalványulva) tökéletesítettük.
- A kiszolgálóval cserélt XML-fájlok érvénytelen szimbólumainak kezelése megfelelően történik. (A nem nyomtatható karakterek kezelése például megfelelő, és az ilyen karakterek már nem okozzák az alkalmazás leállását.)
- A kiszolgálói kérések elküldésekor jelentkező HTTP-hibák (például „503-as hiba”) kezelése megfelelően történik.
- Amikor egy hiba megjelenik, a beállítások listája már nem jelenik meg automatikusan a kombinált lista vezérlőkhöz.
- Az alkalmazás már nem áll le a felhasználói beállítások között kiválasztott megjelenítési tájolás miatt.
- A termékek képe mostantól önkiszolgáló környezetben jelenik meg. (Ez a módosítás csak a kis felbontású verziókra vonatkozik. A fájlkezelő szolgáltatás nem támogatja a teljes méretű képek önkiszolgáló környezetben való használatát.)
- Kijavítottuk a nulla mennyiségű rövid kiválasztásokkal kapcsolatos problémát.
- Az alkalmazás már nem áll le, ha egy részletkártya több azonos mezőt tartalmaz.

### <a name="known-issues-in-version-2060"></a>Ismert problémák a 2.0.6.0 verzióban

Ebben a verzióban a következő problémák ismertek:

- Az alkalmazás (különösen a munkalista) az idő múlásával lelassul.
- **Windows-verzió:** Ha USB-fegyvert használnak a Windowson történő szkenneléshez, az inkonzisztens eredmények miatt a beolvasott szimbólumok összekeveredésnek.

## <a name="version-2050"></a>2.0.5.0-s verzió

Ez a kiadás az alábbi új funkciókat, hibajavításokat és fejlesztéseket tartalmazza:

- Az ügyfél titkos kódja már nem rejtett a kapcsolat beállításaira szolgáló részen.
- Mostantól a bármelyik szöveg hosszú lenyomásával teljesen megjeleníthető.
- Tökéletesítettük a tárolási engedélyek hiányzása esetén megjelenő hibaüzenetet.
- Egyes folyamatokhoz új vezérlősorozatokat adtunk hozzá.
- A Küldés gomb már nem jelenik meg helytelenül az ablakméret miatt.
- A csúszkák nagyobb gombméret használata esetén kisebb képernyőkön is használhatók.
- A négygombos átfedés már nincs levágva.
- A billentyűzet már támogatja a törlési gombot.
- Kijavítottuk a billentyűzet használatakor előforduló fényerősség-problémát.
- A bemutató adatokkal kapcsolatos különböző problémákat kijavítottuk.
- Kijavítottunk egy, a részletek lapon lévő numerikus mezőket érintő problémát.
- A képernyőbillentyűzet már nem tűnik el időnként egyes eszközökön.
- Kijavítottunk különböző felhasználói felületi hibákat, például azokat, amelyek a háttérszínre és a pozicionálásra voltak hatással.
- Az orosz nyelvű felhasználói felületet tökéletesítettük.
- Számos olyan problémát javítottunk, amely a rendszer leállását okozta.
- A számológép újbóli megnyitásával kapcsolatos problémát kijavítottuk.
- **Android-verzió:** Kijavítottunk egy olyan problémát, amely miatt az Android 4.4 leállt az indításkor.
- **Android-verzió:** A minimális méretezés 50 százalékra csökkent.

## <a name="version-2040"></a>2.0.4.0-s verzió

A 2.0.4.0 verzió volt a Warehouse Management mobilalkalmazás első általánosan elérhető kiadása.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Új funkciók, hibajavítások és fejlesztések a 2.0.4.0 verzióban

Ez a verzió az előzetes verzió el nem érhető következő új funkciókat, hibajavításokat és fejlesztéseket kínálja:

- Ha egy részleteket tartalmazó kártya két azonos adatokat mutató címkét tartalmaz, az egyik címke rejtve marad.
- A speciális karakterek alapértelmezés szerint már megjelennek, és az elrejtésükre szolgáló beállítás kikerült a felhasználói beállítások közül.
- A letiltott küldési gombok mostantól nem érhetők el a kompakt, karon használt nézetben.
- A vezérlők sorrendbe állítási logikájának módosítása gördülékenyebb méretezést biztosít az eszközök között. Ennek megfelelően a betűtípusok és a gombok méretezését ritkábban kell korrigálni.
- Az alapértelmezett színtéma a *Sötét* lett.
- A letiltott küldési gomb hiányzó ikonját hozzáadtuk a szalagnézetből.
- Az időkorlát túllépése miatti kivételek esetén a felhasználó mostantól a kapcsolat oldalára kerül, és nem hibaüzenet jelenik meg.
- Ha nincs használható küldési művelet (pl. **OK**, **Igen**, **Elfogadás**, **Kész** vagy **Befejezve**), akkor a küldésre szolgáló gomb le van tiltva.
- Az alkalmazás stabilabb lett.
- A [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) biztonsági rést javítottuk.
- **Windows-verzió:** Kijavították azt a windowsos problémát, amely miatt a menük az ablak átméretezése után nem reagáltak.

### <a name="known-issue-in-version-2040"></a>Ismert probléma a 2.0.4.0 verzióban

Ebben a verzióban a következő probléma ismert:

- A verzió Android 4.4-en való használata problémát okozott. Problémák merülhettek fel, ha az alkalmazást ezzel az Android-verzióval használja.
