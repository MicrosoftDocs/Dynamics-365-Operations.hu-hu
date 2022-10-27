---
title: SEPA átutalás áttekintése
description: Ez a cikk általános információkat tartalmaz az ISO 20022 átutalásokról, amelyek magukban foglalják a SEPA-átutalásokat és minden más elektronikus kifizetést a szállítók számára.
author: mrolecki
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "11124"
- intro-internal
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 671594b1ac6f10fae7c95ed9210e16f168e8dea1
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716074"
---
# <a name="sepa-credit-transfer-overview"></a>SEPA átutalás áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk általános információkat tartalmaz az ISO 20022 átutalásokról, amelyek magukban foglalják a SEPA-átutalásokat és minden más elektronikus kifizetést a szállítók számára. A SEPA átutalás olyan euroalapú kifizetéstípus, amely egy vállalattól vagy személytől egy másik vállalatnak vagy személynek történik. A cikk azt is leírja, hogyan lehet beállítani és továbbítani egy átutalási fizetési fájlt.

## <a name="what-is-a-credit-transfer-message"></a>Mi a jóváírási üzenet?
A jóváírási üzenet egy olyan kérés, amelyet a kezdeményező fél (az Ön vállalata) elküld annak érdekében, hogy összegeket helyezzen át saját számlájáról egy hitelezőnek. Számos ország-/régióspecifikus és benkspecifikus megvalósítása létezik a jóváírási üzeneteknek. Néhányat csak egy országon/régión belül használnak, míg néhány már szabványossá vált. Az egyik jól megalapozott globális szabvány az ISO 20022 és annak indítási üzenetei, például a Jóváírás átvitele. Az alábbi ábrán a kapcsolatok és a lefedettség látható a kijelölt jóváírási üzenetekre vonatkozóan. 
![Jóváírás átutalása.](./media/credit-transfer.jpg) Jóváírás-átutalási üzenetek 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Mik az ISO 20022 és SEPA átutalások?
Az Egységes Euro Fizetési Övezet (SEPA) az Európai Bizottság által került meghatározásra, és a szabályai előírják, hogy minden elektronikus kifizetés belföldinek számít, függetlenül az egyes személyek, vállalatok, szervezetek vagy bankok elhelyezkedésétől. Az országon belüli és a nemzetközi kifizetések között nincs különbség. A SEPA magában foglalja a 28 Európai Uniós (EU) tagállamot, illetve Izlandot, Liechtensteint, Norvégiát, Svájcot, Monacót és San Marinót. A SEPA egységes piacot teremt az Európai Gazdasági Térségen (EGT) belüli kifizetési tranzakciók számára. A várakozások szerint a SEPA csökkenteni fogja a bankok, vállalatok és személyek által használt és kezelt kifizetési formátumok számát. Az Európai Bizottság a SEPA átutalások jogi alapját a Pénzforgalmi szolgáltatási irányelven (PSD) keresztül alakította ki. Az Európai Fizetési Tanács (EPC) a SEPA-t a következő tevékenységekkel támogatja:

-   A SEPA elektronikus átutalások szabványait az ISO-20022 univerzális pénzügyi iparág XML üzenetformátum segítségével állítja be.
-   Megállapítja az euró kifizetések kezelési szabályait és irányelveit.

Az európai bankokból álló EPC kereskedelmi és műszaki keretrendszereket fejleszt a SEPA-fizetőeszközökhöz. Háromféle SEPA tranzakció van használatban:

-   SEPA átutalás
-   Beszedési megbízás
-   Kártyák

## <a name="what-is-a-sepa-credit-transfer"></a>Mi a SEPA átutalás?
A SEPA átutalás olyan kifizetés, amely egy vállalattól vagy személytől egy másik vállalatnak vagy személynek történik. A kifizetésnek euróban kell történnie, és tartalmaznia kell mindkét fél nemzetközi bankszámlaszámát (IBAN) és bankazonosító kódját (BIC). (A BIC kód a \[SWIFT\] (Society for Worldwide Interbank Financial Telecommunication) kód néven is ismert.) Ezenkívül a tranzakciós költségek a két fél között oszlanak el. A felek között előforduló átutalások az ISO-20022 kifizetés-feldolgozási szabványt és az EPC által meghatározott XML fájlokat és formátumot kötelesek használni.

## <a name="how-is-a-credit-transfer-implemented"></a>Hogyan történik az átutalás?
Az európai országok számára elérhető átutalási fizetési formátum a Microsoft Dynamics 365 Finance elektronikus jelentés és fizetési módok funkció segítségével valósítható meg. Néhány átutalási formátum, amelyet más régiókban használnak, még mindig a régi fizetési keretrendszert használja. Számos más formátum közül 12 elérhető ISO 20022 átutalási fájlformátum létezik. Ezek az exportformátumok megfelelnek a SEPA ISO 20022 XML szabványnak. Használatukkal nem euró-átutalások juttathatók el azoknak az országoknak/régióknak, ahol használják őket az EPC által kiadott SEPA Credit Transfer Scheme szabálykönyv 8.2-es verziójában meghatározott szabályok szerint. Mielőtt megvalósítana egy átutalást, kapcsolatba kell lépnie a bankjával az elektronikus bankhasználati fájlok feltöltéséhez használt szoftver érvényesítéséhez. Ezt a szoftvert fogja használni az utalványokat tartalmazó XML fájlok banki átviteléhez.

## <a name="what-credit-transfer-formats-are-currently-supported"></a>Melyik jóváírási átmozgatási formátumok támogatottak jelenleg?
Mindig meg kell keresnie a Microsoft Dynamics Lifecycle services (LCS) megosztott eszközkönyvtárát, és meg kell tekintenie a legfrissebb listát a rendelkezésre álló fájlokról, amelyek **GER-konfiguráció** eszköztípusúak. A következő, "Mit kell beállítani?", egy hivatkozást tartalmaz arra a cikkre, amely bemutatja, hogyan lehet LCS-tárházat létrehozni a rendelkezésre álló konfigurációk áttekintése és a kiválasztott konfigurációk importálása során.

## <a name="what-do-i-have-to-set-up"></a>Mit kell beállítanom?
-   Mielőtt átutalási fájlokat hoz létre, legalább egy aktív SEPA átutalási konfigurációt importálni kell az ER-konfigurációkba. További utasításokért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
-   Válassza ki az **Általános elektronikus jelentéskészítés** jelölőnégyzetet, majd válassza ki a megfelelő átutalási formátumot (pl. **ISO 20022 átutalás (AT)**) exportformátum-konfigurációként, amikor konfigurálja a Kötelezettségek fizetési módjait.
-   Be kell állítani a jogi személyt és a bankszámla adatait.
-   Bankszámlaszámok, IBAN-ok és néha SWIFT-kódok (BIC-k) vagy más azonosító adatok szükségesek az érvényes átutalások létrehozásához. Ezért be kell állítania őket az eladói bankszámlához és az átutalást kérelmező szervezet bankszámlájához.
-   További információra is szükség lehet, például az áfaszámokra azoknál a feleknél, akik szerepelnek az átutalási üzenetben. Ezt az információt a kereskedők és a jogi személy számára kérésre kell beállítani.
-   Egyes kötelezettségek fizetési módjai, főként az ISO 20022-alapú fizetési módok, további beállításra szorulhatnak a **Fizetési formátum kódkészletei** tekintetében, például **Szolgáltatás típusa** = **SLEV**. Ezeket a kódokat a fizetés feldolgozása során a fizetési tranzakciók további címkézésére használják. A fizetési kódok alapértelmezett értékeit (pl. **Kategória célja**, **Költségviselő**, **Helyi eszköz** és **Szolgáltatásszint**) két helyen lehet beállítani. Az első hely a **Kötelezettségek fizetési naplójának fejléce**, a második pedig a **Kötelezettségek fizetési módszerei**. A fizetési napló sorainak létrehozásakor a fizetési napló fejlécében beállított fizetési kódértékek átkerülnek a naplósorba, ha nincs megadva, akkor a Fizetési mód értékeit használja a rendszer.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Milyen paraméterek érhetők el a jóváírási kifizetések létrehozásakor?
Az egyes paraméterek listája az átutalási formátumtól függ. Az alábbi táblázat azokat a paramétereket tartalmazza, amelyeket a ISO 20022 Németországra érvényes jóváírási kifizetés fájl létrehozásakor használhat a szállítói kifizetési naplóban. A rendelkezésre álló beállítások használatával a **Futtatás háttérben** lapon futtathatja a kifizetés létrehozását kötegelt módban.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Köteg foglalása</td>
<td>Jelölje be ezt a jelölőnégyzetet a köteg foglalási címke szerepeltetéséhez az XML fájlban.</td>
</tr>
<tr class="even">
<td>Feldolgozás dátuma</td>
<td>Adja meg a dátumot, mikor dolgozza fel a bank a kifizetéseket.</td>
</tr>
<tr class="odd">
<td>Formátum</td>
<td>Válassza ki az utalási adatok formátumát az ország/régió vagy a bank elvárásainak megfelelően:
<ul>
<li><strong>Strukturált</strong> – Válassza ezt az opciót a strukturált formátum használatához, amikor egy fizetési sort egy számlával szemben számolnak el. Ez a beállítás nem érthető el ország-/területspecifikus exportálási formátumként Franciaországban, Németországban és Hollandiában.</li>
<li><strong>Strukturálatlan</strong> – Válassza ezt az opciót a strukturálatlan formátum használatához, amikor a kifizetést több számlával szemben számolnak el. A kiegyenlített számlák számlaszámait a rendszer összefűzi, és átutalási információként használja. A ISO 20022 irányelvek szerint a strukturálatlan utalási adatok 140 karakterre korlátozódnak.</li>
</ul></td>
</tr>
<tr class="even">
<td>Számlák száma</td>
<td>Adja meg a számlák darabszámát, amelyből a <strong>Fizetési bizonylat</strong> jelentést nyomtatta.</td>
</tr>
<tr class="odd">
<td>Sorszám</td>
<td>Adjon meg egy sorszámot a fájl azonosításához. A sorozatszám megjelenik a <strong>Részvételi bizonylat</strong> jelentésen.</td>
</tr>
<tr class="even">
<td>Részvételi bizonylat nyomtatása</td>
<td>Jelölje be ezt a jelölőnégyzetet a <strong>Részvételi bizonylat</strong> kinyomtatásához.</td>
</tr>
<tr class="odd">
<td>Ellenőrzési jelentés nyomtatása</td>
<td>Jelölje be ezt a jelölőnégyzetet a kifizetési információkat tartalmazó jelentés kinyomtatásához.</td>
</tr>
<tr class="even">
<td>Kísérőlevél nyomtatása</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha szeretné kinyomtatni a <strong>Kifizetési bizonylat</strong> jelentést.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Mi az IBAN és a BIC?
A nemzetközi bankszámlaszám (IBAN) és a bankazonosító kód (BIC) minden számla azonosítható sok országban/régióban világszerte. Ezek közé tartozik a 34 SEPA ország is. Adja meg a BIC-kódot a **SWIFT kód** mezőben és az IBAN-kódot az **IBAN** mezőben. A hitelező bankszámlájának és a vevő bankszámlájának esetében ezek a mezők a **További azonosítás** gyorslapon a **Bankszámla** fülön a **Bankszámlák** oldalon találhatók. A BIC használatát a SEPA-fizetésekre már nem érvényesítik.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Hogyan küldjem el a fizetési fájlt a banknak?
Amikor kifizetéseket hoz létre, létrejön egy kifizetési fájl, és a rendszer arra kéri, hogy mentse le a böngészőből bármilyen rendelkezésre álló helyre. A következő lépés az, hogy az XML fájlt elküldje a bankjának. Ez a folyamat bankról bankra változik. Kövesse a banktól kapott utasításokat fájlok banki feldolgozásra való feladásához.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
