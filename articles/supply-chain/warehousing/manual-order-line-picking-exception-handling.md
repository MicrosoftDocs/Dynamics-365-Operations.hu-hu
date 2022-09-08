---
title: Értékesítési és átátviteli sorok kitárolási kivételének manuális kezelés
description: Ez a témakör azt írja le, hogyan válogathatják ki (vagy visszatárhatják) a készlettranzakciókat a hibás értékesítési és átátviteli rendelési adatok által okozott problémák kijavítása érdekében.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9404420"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Értékesítési és átátviteli sorok kitárolási kivételének manuális kezelés

[!include [banner](../includes/banner.md)]

Az értékesítési sorok kitárolási kivételeinek manuális kezelése lehetővé teszi a rendszergazdák számára, hogy kijavítsák az értékesítési és átmozgatási rendelések sérült adatai által okozott problémákat. Lehetővé teszi, hogy a megbízható felhasználók manuálisan kitárolják (vagy visszatárolják) azokat a készlettranzakciókat, amelyek értékesítési és átátviteli rendelési sorokkal kapcsolatosak, miközben a raktári folyamatok már folyamatban vannak.

Az itt leírt funkciókat csak olyan esetekben szabad használni, amikor a rendszer nem tudja a szokásos módon befejezni a raktári folyamatok feldolgozását. Alapértelmezés szerint csak a rendszer rendszergazdai szerepkörrel berekedő felhasználók használhatja azt. Ehhez azonban úgy adhat *hozzáférést*, hogy a kiválasztó értékesítési sorokat kézzel rendeli más szerepkörökhöz.

## <a name="turn-on-this-feature-for-your-system"></a>A funkció bekapcsolása a rendszerhez

A jelen cikk által leírt funkciók csak akkor használhatók, ha bekapcsolták őket a rendszerben. A rendszergazdák a funkciókezelési [beállítások segítségével](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) ellenőrizhetik és bekapcsolhatja a funkciók állapotát. A Funkciók **kezelése munkaterületen** a szolgáltatások a következő nevek használatával megjelenik a listában:

- *Manuális értékesítési sor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező, és nem lehet kikapcsolni.)
- *Manuális transzfersor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Értékesítési vagy átátviteli rendelési sorokhoz kapcsolódó tranzakciók korrigálása

A következő eljárás szerint javíthatja ki az értékesítési vagy átrendelési sorokhoz kapcsolódó tranzakciókat.

1. Hajtsa végre a következő lépések valamelyikét attól függően, hogy milyen típusú rendelést kell kijavítani:

    - Az értékesítési rendelésekhez kapcsolódó tranzakciók kijavítása érdekében menjen a **Raktárkezelés \>\> – Időszakos feladatok – Az \> értékesítési sor manuális kitisztítható kivezetése művelethez**.
    - Ha ki kell javítani egy átvezetési rendeléshez kapcsolódó tranzakciót, **válassza a Raktárkezelés \>\> – Időszakos feladatok – Az \> átvezetési sorok manuális tisztítása parancsot**.

1. Az értékesítési **sorok** **manuális** kirendelése vagy Az áthozott sorok manuális kiválasztása lapon a rács tetején található szűrők használatával keresse meg a keresett sort, majd válassza ki a célrendeléssort a felső rácsban.
1. Az alsó **szakaszban található Készlettranzakciók**, **Rakománysorok**, **·** **Munkasorok** és Tárolósorok lapon a kijelölt sor további adatait lehet megtekinteni. Az ezeken a lapokon található információk alapvető áttekintést nyújtanak a kapcsolódó raktári folyamatokról és állapotukról.
1. A műveletpanel Kitár **gombra** kattintva megnyithatja a kijelölt rendeléssort a készlettranzakciók **Kitározás** lapján. Ezt a lépést akkor is el lehet végrehajtani, ha olyan rendeléssorok vannak kiadva a raktárba, amelyek már ki vannak adva a raktárba. (A raktárba már kiadott rendeléssorok általában nem nyitható meg a következőn: **Oldal** kiválasztószáma.)

    > [!NOTE]
    > A Kiválasztó lap megnyitásakor különféle figyelmeztetések **lehetnek**. Az alábbi figyelmeztetések által ajánlott bármely művelet meghozva. Figyelmeztetést kaphat például a raktári munkához kapcsolódó rendeléssorokkal kapcsolatban. Ebben az esetben a manuális [javítás](cancel-warehouse-work.md) előtt próbálja meg visszavonni a munkát a szokásos érvénytelenítési funkcióval.

1. Válassza ki a sort a **Tranzakciók rácsban**, majd válassza **a Kitárolási sor hozzáadása lehetőséget a** Tranzakciók **eszköztáron**.
1. A kijelölt sor átkerül a Kitárolási **sorok rácsba**. Állítsa be a megfelelő értékeket az olyan oszlopokhoz, amelyekből hiányoznak a szükséges adatok. (Megadhatja például azt a helyet és táblatáblát, amelyből a cikket ki kell kihozni/ki kell nem kihozni.)
1. Válassza az **összes kitárolás megerősítése lehetőséget** a Kitárolási **sorok eszköztáron**.

## <a name="correct-load-line-quantities"></a>Rakománysor mennyiségének megfelelő mennyiség

A következő eljárás szerint javíthatja ki a rakománysor mennyiségét.

1. Hajtsa végre a következő lépések valamelyikét attól függően, hogy milyen típusú rendelést kell kijavítani:

    - Az értékesítési rendelésekhez kapcsolódó tranzakciók kijavítása érdekében menjen a **Raktárkezelés \>\> – Időszakos feladatok – Az \> értékesítési sor manuális kitisztítható kivezetése művelethez**.
    - Ha ki kell javítani egy átvezetési rendeléshez kapcsolódó tranzakciót, **válassza a Raktárkezelés \>\> – Időszakos feladatok – Az \> átvezetési sorok manuális tisztítása parancsot**.

1. Az értékesítési **sorok** **manuális** kirendelése vagy Az áthozott sorok manuális kiválasztása lapon a rács tetején található szűrők használatával keresse meg a keresett sort, majd válassza ki a célrendeléssort a felső rácsban.
1. Az alsó rész **Rakománysorok** lapján válassza **a** Rakománysorok manuális beállítása lehetőséget az eszköztáron.
1. A Rakománysorok **manuális** korrigálása **lapon**, a Készlettranzakciók rácsban ellenőrizze a kiválasztott rakománysorhoz kapcsolódó készlettranzakciókat.
1. Szükség esetén javítsa ki a felső rácsban a rakománysorok mennyiségét az alábbi oszlopokban:

    - **Munka létrehozott mennyisége**
    - **Kitárolt mennyiség**
    - **Tervezett áttárolási mennyiség**

    A rendszer ellenőrzi az ezen oszlopokon végrehajtott módosításokat.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
