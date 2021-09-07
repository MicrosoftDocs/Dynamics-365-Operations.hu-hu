---
title: Újdonságok és változások a Warehouse Management mobilalkalmazásban
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új és módosult funkcióit ismerteti.
author: ivanv-microsoft
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6d98cea29f4c25319caed6680966f61c660778f0
ms.sourcegitcommit: 3d05bb2a423fe130700686ff73daa355d15b0e09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386099"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Újdonságok és változások a Warehouse Management mobilalkalmazásban

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management rendszerhez használatos Warehouse Management mobilalkalmazás egyes kiadásainak új funkcióit, hibajavításait, fejlesztéseit és ismert hibáit ismerteti.

## <a name="version-2090"></a>2.0.9.0-s verzió

Ez a verzió javítja azt a problémát, hogy az alkalmazás nem reagál, ha a felhasználók a lista tetejéről lapoznak felfelé.

## <a name="version-2080"></a>2.0.8.0-s verzió

Ez a kiadás az alábbi új funkciókat, hibajavításokat és fejlesztéseket tartalmazza:

- A 10.0.21-es Supply Chain Management verzióban bevezetett [lépésutasítás funkció](mobile-app-titles-instructions.md) támogatása.
- Hozzáadva a célzási animáció, amely megmutatja a felhasználóknak, hogy lefelé húzással bezárhatják az átfedéseket.
- Hozzáadva a funkcióbillentyűk támogatása a műveleti listákon és menükben. A felhasználók bármelyik funkcióbillentyűt három másodpercig lenyomva tartva megjeleníthetik az elérhető parancsok listáját.
- Javítottunk egy olyan problémát, amely miatt egyes eszközökön a következő hibaüzenet jelent meg: „Nem talál megfelelő nézetet a megadott mérethez”
- Javítottunk egy olyan problémát, amikor a teljes képernyős mód nem mindig működött, amikor a képernyőn megjelenő billentyűzetet használtuk.
- Javítottunk egy olyan problémát, amikor az oldalhúzás nem működött a Windows-eszközökön.
- Számos olyan problémát javított, amely a rendszer leállását okozta.

## <a name="version-2070"></a>2.0.7.0-s verzió

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>Új funkciók, hibajavítások és fejlesztések a 2.0.7.0 verzióban

- Szakasz hozzáadása a **Névjegy** laphoz, amely ellenőrzi az alkalmazás legújabb kiadott verzióját.
- Megkönnyíti a lapok pöccintését és húzását.
- A munkalista növekvő/csökkenő gombjának ikonja módosult.
- Csökkentette a **Részletek** kártya margóját, hogy még több adat férjen el rajta.
- Különböző teljesítményjavításokkal csökkenti azt a problémát, hogy az alkalmazás idővel egyre lassabbá vált.
- Ha a képernyő kapacitásánál több vezérlőelem van, ami lapozást eredményezve, a betöltésjelző vezérlő már nem görgethető ugyanúgy, mint a lap.
- Az utolsó beolvasott érték megjelenítésének előnyben részesítése a feladat címének megjelenítése előtt, így ha átfedésben van a feladat címével, akkor az csonkolva lesz.
- Számos olyan problémát javított, amely a rendszer leállását okozta.
- A különböző helyeken már nincs levágva a szöveg egyes nyelveken.
- Az alkalmazás immár alapértelmezés szerint teljes képernyős módban fut.
- Kijavított egy problémát, amely esetenként a beolvasások figyelmen kívül hagyását okozhatja a főoldalon bizonyos készülékekkel.

### <a name="known-issues-in-version-2070"></a>Ismert problémák a 2.0.7.0 verzióban

- Egyes eszközöknél a következő hibaüzenet jelenik meg, amikor elindítja az alkalmazást, vagy elindít egy feladatot: "Nem található megfelelő nézet a megadott mérethez." Ha bármelyik eszközön látja ezt a hibaüzenetet, akkor álljon vissza az eszközön a Warehouse Management mobilalkalmazás 2.0.6.0 verziójára azon az eszközön, és várja meg a frissítést, amíg az alkalmazás következő verziója meg nem jelenik.

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
