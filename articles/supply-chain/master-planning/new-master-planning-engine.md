---
title: Áttelepítés a tervezési optimalizálásra az alaptervezéshez
description: Ez a cikk az új alaptervezési motorról, a tervezési optimalizálásról és a meglévő motorból való áttelepítésről nyújt tájékoztatást.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: dbbc58f0dcd833f63e84a73ac68ada60bd0c291d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739951"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Áttelepítés az alaptervezéshez használatos Tervezési optimalizálásra

[!include [banner](../includes/banner.md)]

A beépített alaptervezési motor elavultnak van ütemezve (elavult). A Microsoft Dynamics 365 Supply Chain Management Tervezés optimalizálása bővítménye váltja fel. Ez a cikk az új és a meglévő telepítésekre gyakorolt hatásokkal kapcsolatban tartalmaz tájékoztatást. A szükséges műveletekre vonatkozó információkat tartalmaz.

A Tervezési optimalizálás lehetővé teszi, hogy az alaptervezési számítások a Supply Chain Management szolgáltatáson és a kapcsolódó Azure SQL-adatbázison kívül történjenek. A Tervezési optimalizáláshoz tartozó előnyök között szerepel a továbbfejlesztett teljesítmény és az SQL-adatbázisra tett minimális hatás az alaptervezés futtatásakor. Mivel a gyors tervezési futtatások a nyitvatartási idő alatt is megtehetők, így a tervezők azonnal reagálni tudnak a igényre vagy a paraméterek változásaira.

A tervezésoptimalizálással kapcsolatos további tudnivalókat lásd [az Alaptervezés rendszer architektúráját](master-planning-architecture.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>A meglévő alaptervezési motor elavulása

A Microsoft az elavult alaptervezési motort elavulttá teszi a tervezési optimalizálás során. Ez a módosítás hatással van az összes felhőalapú környezetre. Az intézményi telepítések nem érintettek. A 10.0.16-os és későbbi verzióban egy hibaüzenet jelenik meg, ha a tervezett termelési rendelések létrehozása nélkül futtatja az elavult alaptervezési motort. A hibaüzenet ellenére azonban a program sikeresen végrehajtja az alaptervezést.

Az elavult alaptervezési [motorról az Eltávolítva vagy elavult funkciók bejelentései tartalmaznak további tudnivalókat a következőben:Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md)

## <a name="migration-messages-and-exceptions"></a>Áttelepítés, üzenetek és kivételek

A meglévő környezetek tulajdonosai, akik tervezett termelési rendelések létrehozása nélkül futtatják az elavult alaptervezési motort, e-mailt kapnak, amely a kivétel folyamatának részleteit tartalmazza. Javasoljuk, hogy egy partnerrel folytasson együttműködést a tervezési optimalizáláshoz szükséges áttelepítés értékeléséhez és megtervezéséhez.

Amint már említettük, hibaüzenetet kap a 10.0.16-os és később verzióban, ha a tervezett termelési rendelések létrehozása nélkül futtatja az elavult alaptervezési motort. Ez a hibaüzenet az áttelepítéssel és a kivételek kérelmezésével kapcsolatos útmutatást tartalmaz.

### <a name="new-deployments"></a>Új telepítések

A tervezési optimalizálást a felhő minden új telepítésének alapértelmezett alaptervezési motorjaként kell figyelembe venni. Általánosan a tervezési optimalizálás minden olyan új telepítésnél használható, amely nem hoz létre tervezett termelési rendeléseket az alaptervezés során. Ha az új telepítés olyan funkcióktól függ, amelyek használatát a tervezési optimalizálás jelenleg nem támogatja, kivételt kérhet, így továbbra is használhatja az elavult alaptervezési motort.

### <a name="existing-deployments"></a>Meglévő telepítések

Az alaptervezéstől függő meglévő felhőalapú telepítések tulajdonosainak tervbe kell tenniük a Tervezési optimalizálásra való áttelepítést. Ha a megvalósítás olyan funkcióktól függ, amelyek használatát a tervezési optimalizálás jelenleg nem támogatja, kivételt kérhet, így továbbra is használhatja az elavult alaptervezési motort.

A jelenleg elavult alaptervezési folyamatokat használó környezetek esetében a Microsoft e-mailt küld a környezet adminisztrátorának. Ez az e-mail információt nyújt az áttelepítéshez vagy a kivételek kéréséhez szükséges műveletekről.

## <a name="the-exception-process"></a>A kivétel folyamata

Kivételt akkor lehet kérni, ha továbbra is használnia kell az elavult alaptervezési motort, mivel az üzleti folyamatok legalább egy olyan funkciótól függnek, amely jelenleg nincs megvalósítva a tervezési optimalizálásban. Az elérhető szolgáltatások listáját lásd: [Tervezési optimalizálása illeszkedési elemzése](planning-optimization/planning-optimization-fit-analysis.md).

Jelenleg csak akkor van jelentősége a tervezési optimalizálás áttelepítésére vonatkozó kivételeknek, ha az alaptervezés folyamata nem tartalmazza a termelést (azaz az alaptervezés által létrehozott tervezett termelési rendeléseket), és az elavult alaptervezési motorra a 10.0.15-ös verzión túl van szükség.

A szükséges szolgáltatások elérhetővé válása után a Microsoft türelmi időszakot ad meg, amíg a kivétel lejár. A környezet adminisztrátorát tájékoztatni kell a szükséges szolgáltatások elérhetővé válásakor és a türelmi időszak indulásakor.

Az alábbi folyamatábra összefoglalja a jelen cikk adatait, így gyorsan ki tudja találni, hogy kivételt kell-e kérnie. Ha kivételt kell kérnie, töltse ki és küldje el a [Tervezési optimalizálás áttelepítése és kivétel kérdőívet](https://go.microsoft.com/fwlink/?linkid=2144962). A termékcsoport felelős az egyes kivételi kérelmek kiértékeléséért és jóváhagyásáért, ezért kérjük, a megadott hivatkozás használatával közvetlenül a termékcsoportnak küldje el a kérést, és ne hozzon létre támogató jegyet. Ha a kérést elutasítják, ne hozzon létre támogatási jegyet, mert a Microsoft-támogatás nem tudja újra kiértékelni vagy támogatni a kivételeket.

![Kivétel folyamatábra.](media/exception-diagram.png "Kivétel folyamatábra")

> [!NOTE]
> Kivételt csak olyan bérlők esetében lehet kérelmezni, akik jelenleg tartalmaznak vagy tartalmazni fognak éles környezetet, olyan bérlők esetén nem, akik csak tesztkörnyezetben vannak. Ha egy szolgáltatott infrastruktúra (IaaS) elvű tesztkörnyezetében le kell tiltania a Tervezési optimalizálás kivételi hibáját, futtassa a [tesztkörnyezetekben](#faq-sandbox) nyújtott SQL-lekérdezést.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Tesztkörnyezetek

Használhatom az elavult alaptervezési motort a saját beérkezett üzenetek környezetében? Kivétel szükséges?

**Válasz:** A kivételek általában nem fontosak a dobozos környezetekben, mert a tervezési optimalizálási kivétel hibája nem akadályozza meg az elavult alaptervezési motor sikeres futtatását. Ha azonban a hibaüzenet zavarja, akkor letilthatja egy IaaS (nem Service Fabric) tesztkörnyezetében, ha a következő lekérdezést futtatja az adatbázison:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Helyszíni környezetek

A környezetem helyszíni. Kivétel szükséges?

**Válasz:** Nem. Nem szükség kivételre a helyszíni környezetekhez. Folytathatja az elavult alaptervezési motor használatát. A környezet adminisztrátora tájékoztatni fogja, ha szükséges valamilyen művelet.

### <a name="production-scenarios"></a>Termelési esetek

A tervezett termelési rendeléseket használjuk, de aggódom amiatt, hogy mi fog történni, amikor frissítünk a 10.0.16-os verzióra. Van valamilyen teendőm?

**Válasz:** Nem kell aggódnia. A 10.0.16 verzióban továbbra is használhatja az elavult alaptervezési motort. Azonban azt ajánljuk, hogy kezdje el mérlegelni, hogy az aktuális funkciókkal megkezdődhet-e a Tervezési optimalizálásra való áttelepítés. Azt ajánljuk továbbá, hogy az új funkciókról továbbra is tájékozódjon.

### <a name="email-from-microsoft"></a>E-mail a Microsofttól

Környezeti adminisztrátorunk egy e-mailt kapott a Microsofttól. Az e-mail szerint át kell állítanunk a rendszerünket a Tervezési optimalizálásra, vagy kivételt kell kérnünk. Szükség van valamilyen műveletre?

**Válasz:** Igen. Ez érinteni fogja a környezetét, hacsak nem követi az e-mail utasításait. Átállíthatja rendszerét a Tervezési optimalizálásra a megadott dátummal, vagy az e-mailben található hivatkozással kivételt kérhet. Ez a hivatkozás egy kérdőívet nyit meg. Miután kitöltötte, és elküldte a kérdőívet, e-mailben kap választ. Bár ez a folyamat manuális, a Microsoft a kérdőív elküldése után egy héten belül próbálkozik a válaszadással.

### <a name="error-messages"></a>Hibaüzenetek

Az alaptervezés futtatásakor a következő hibaüzenet jelenik meg a 10.0.16-os vagy későbbi verzión. Az alaptervezés zárolva van?

> Ez a hibaüzenet azért jelenik meg, mert az elavult alaptervezési motort a tervezési optimalizálás által támogatott helyzetekhez használta a rendszer. Most kell áttérni a Tervezési optimalizálásra, mert a beépített alaptervezési motor már elavult. Ne feledje, hogy ennek az alaptervezésnek a futtatása sikeresen befejeződött.
>
> Ha az áttelepítésben erős függőségek vannak a függő funkcióktól, kivételt lehet kérni az elavult alaptervezési motor folyamatos használatára.
>
> Töltse ki a következő kérdőívet a kezdéshez, illetve a szükséges, kérelmezzen kivételt a Tervezési optimalizálásra való átállítás alól.

**Válasz:** Nem, az alaptervezés nem zárolt. Az alaptervezés futtatása sikeresen befejeződött, és az eredményt a megszokott módon lehet használni. Ha azonban a jövőbeli alaptervezés során nem szeretné látni ezt a hibaüzenetet, akkor vagy azonnal át kell telepítenie a rendszerét a Tervezési optimalizálásra, vagy kivételt kell kérnie a hibaüzenetben szereplő hivatkozás használatával.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
