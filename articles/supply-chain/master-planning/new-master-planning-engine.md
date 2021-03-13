---
title: Áttelepítés az alaptervezéshez használatos Tervezési optimalizálásra
description: Ez a témakör az új beépített tervezési motorral, a tervezési optimalizálással és a meglévő motorból történő átállítással kapcsolatban tartalmaz tájékoztatást.
author: ChristianRytt
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8a55958a4b9573a7c3527d3d97cbcb818457b995
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007979"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Áttelepítés az alaptervezéshez használatos Tervezési optimalizálásra

[!include [banner](../includes/banner.md)]

A beépített alaptervezési motor elavultnak van ütemezve (elavult). A Microsoft Dynamics 365 Supply Chain Management Tervezés optimalizálása bővítménye váltja fel. Ez a témakör az új és a meglévő telepítésekre gyakorolt hatásával kapcsolatban tartalmaz tájékoztatást. A szükséges műveletekre vonatkozó információkat tartalmaz.

A Tervezési optimalizálás lehetővé teszi, hogy az alaptervezési számítások a Supply Chain Management szolgáltatáson és a kapcsolódó Azure SQL-adatbázison kívül történjenek. A Tervezési optimalizáláshoz tartozó előnyök között szerepel a továbbfejlesztett teljesítmény és az SQL-adatbázisra tett minimális hatás az alaptervezés futtatásakor. Mivel a gyors tervezési futtatások a nyitvatartási idő alatt is megtehetők, így a tervezők azonnal reagálni tudnak a igényre vagy a paraméterek változásaira.

Tervezési optimalizálással kapcsolatos további tudnivalókért lásd: [Tervezési optimalizálás áttekintése](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>A meglévő alaptervezési motor elavulása

A Microsoft a beépített tervezési motort elavulttá teszi a Tervezési optimalizálás javára. Ez a módosítás hatással van az összes felhőalapú környezetre. Az intézményi telepítések nem érintettek. A 10.0.16 és újabb verziókban egy hibaüzenet jelenik meg, ha a beépített alaptervezést tervezett termelési rendelések létrehozása nélkül futtatja. A hibaüzenet ellenére azonban a program sikeresen végrehajtja az alaptervezést.

Ha további tájékoztatást szeretne kapni a beépített tervezési rendszer elavulásáról, olvassa el a következő témakör bejelentéseit: [Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Áttelepítés, üzenetek és kivételek

Azok, akik beépített alaptervezési motort a tervezett termelési rendelések létrehozása nélkül, a meglévő környezetekben futtatnak, egy e-mail fognak kapni, amely a kivételezési folyamat részleteit ismerteti. Javasoljuk, hogy egy partnerrel folytasson együttműködést a tervezési optimalizáláshoz szükséges áttelepítés értékeléséhez és megtervezéséhez.

Mint már említettük, a 10.0.16 és újabb verziókban egy hibaüzenet jelenik meg, ha a beépített alaptervezést tervezett termelési rendelések létrehozása nélkül futtatja. Ez a hibaüzenet az áttelepítéssel és a kivételek kérelmezésével kapcsolatos útmutatást tartalmaz.

### <a name="new-deployments"></a>Új telepítések

A Tervezési optimalizálást kell az alapértelmezett alaptervezési motornak tekinteni az összes új felhőalapú telepítés esetében. Általánosan a tervezési optimalizálás minden olyan új telepítésnél használható, amely nem hoz létre tervezett termelési rendeléseket az alaptervezés során. Ha egy új telepítés olyan funkciótól függ, amelyet a Tervezési optimalizálás jelenleg nem támogat, akkor kivételt kérhet, így továbbra is használhatja a beépített alaptervezési motort.

### <a name="existing-deployments"></a>Meglévő telepítések

Az alaptervezéstől függő meglévő felhőalapú telepítések tulajdonosainak tervbe kell tenniük a Tervezési optimalizálásra való áttelepítést. Ha a megvalósítása olyan funkciótól függ, amelyet a Tervezési optimalizálás jelenleg nem támogat, akkor kivételt kérhet, így továbbra is használhatja a beépített alaptervezési motort.

A jelenleg elavult alaptervezési folyamatokat használó környezetek esetében a Microsoft e-mailt küld a környezet adminisztrátorának. Ez az e-mail információt nyújt az áttelepítéshez vagy a kivételek kéréséhez szükséges műveletekről.

## <a name="the-exception-process"></a>A kivétel folyamata

Akkor kérhet kivételt, ha továbbra is használni szeretné a beépített alaptervezési motort, mivel az üzleti folyamatok legalább egy olyan funkciótól erősen függenek, amely jelenleg nincs megvalósítva a Tervezési optimalizálásban. Az elérhető szolgáltatások listáját lásd: [Tervezési optimalizálása illeszkedési elemzése](planning-optimization/planning-optimization-fit-analysis.md).

Jelenleg a Tervezési optimalizálás áttelepítési kivételei csak akkor relevánsak, ha az alaptervezési folyamata nem tartalmaz termelést (azaz az alaptervezés által létrehozott tervezett termelési rendeléseket), és egy 10.0.15-ös verzión túli beépített alaptervezési motort kell igényelnie.

A szükséges szolgáltatások elérhetővé válása után a Microsoft türelmi időszakot ad meg, amíg a kivétel lejár. A környezet adminisztrátorát tájékoztatni kell a szükséges szolgáltatások elérhetővé válásakor és a türelmi időszak indulásakor.

> [!NOTE]
> Csak termelési környezetek esetében kérhet kivételt, tesztkörnyezetek esetében nem. Ha egy szolgáltatott infrastruktúra (IaaS) elvű tesztkörnyezetében le kell tiltania a Tervezési optimalizálás kivételi hibáját, futtassa a [tesztkörnyezetekben](#faq-sandbox) nyújtott SQL-lekérdezést.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Tesztkörnyezetek

Használható a beépített alaptervezés a tesztkörnyezethez? Kivétel szükséges?

**Válasz:** Kivételek általában nem vonatkoznak a tesztkörnyezetekre, mert a Tervezési optimalizálási kivételi hibája nem akadályozza meg, hogy a beépített alaptervezési motor sikeresen fusson. Ha azonban a hibaüzenet zavarja, akkor letilthatja egy IaaS (nem Service Fabric) tesztkörnyezetében, ha a következő lekérdezést futtatja az adatbázison:

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

**Válasz:** Nem. Nem szükség kivételre a helyszíni környezetekhez. A beépített alaptervezést továbbra is használhatja. A környezet adminisztrátora tájékoztatni fogja, ha szükséges valamilyen művelet.

### <a name="production-scenarios"></a>Termelési esetek

A tervezett termelési rendeléseket használjuk, de aggódom amiatt, hogy mi fog történni, amikor frissítünk a 10.0.16-os verzióra. Van valamilyen teendőm?

**Válasz:** Nem kell aggódnia. A beépített alaptervezést továbbra is használhatja a 10.0.16-os verzióban. Azonban azt ajánljuk, hogy kezdje el mérlegelni, hogy az aktuális funkciókkal megkezdődhet-e a Tervezési optimalizálásra való áttelepítés. Azt ajánljuk továbbá, hogy az új funkciókról továbbra is tájékozódjon.

### <a name="email-from-microsoft"></a>E-mail a Microsofttól

Környezeti adminisztrátorunk egy e-mailt kapott a Microsofttól. Az e-mail szerint át kell állítanunk a rendszerünket a Tervezési optimalizálásra, vagy kivételt kell kérnünk. Szükség van valamilyen műveletre?

**Válasz:** Igen. Ez érinteni fogja a környezetét, hacsak nem követi az e-mail utasításait. Átállíthatja rendszerét a Tervezési optimalizálásra a megadott dátummal, vagy az e-mailben található hivatkozással kivételt kérhet. Ez a hivatkozás egy kérdőívet nyit meg. Miután kitöltötte, és elküldte a kérdőívet, e-mailben kap választ. Bár ez a folyamat manuális, a Microsoft a kérdőív elküldése után egy héten belül próbálkozik a válaszadással.

### <a name="error-messages"></a>Hibaüzenetek

Az alaptervezés futtatásakor a következő hibaüzenet jelenik meg a 10.0.16-os vagy későbbi verzión. Az alaptervezés zárolva van?

> Ez a hibaüzenet akkor jelenik meg, ha a beépített alaptervezési motort a Tervezési optimalizálás által támogatott esetekhez használta. Most át kell telepítenie rendszerét a Tervezés optimalizálásra, mivel az aktuális beépített alaptervezés elavult. Ne feledje, hogy ennek az alaptervezésnek a futtatása sikeresen befejeződött.
>
> Abban az esetben, ha az áttelepítés erősen függ a függőben lévő szolgáltatásoktól, kérhető a beépített alaptervezési motor további használatának kivétele.
>
> Töltse ki a következő kérdőívet a kezdéshez, illetve a szükséges, kérelmezzen kivételt a Tervezési optimalizálásra való átállítás alól.

**Válasz:** Nem, az alaptervezés nem zárolt. Az alaptervezés futtatása sikeresen befejeződött, és az eredményt a megszokott módon lehet használni. Ha azonban a jövőbeli alaptervezés során nem szeretné látni ezt a hibaüzenetet, akkor vagy azonnal át kell telepítenie a rendszerét a Tervezési optimalizálásra, vagy kivételt kell kérnie a hibaüzenetben szereplő hivatkozás használatával.
