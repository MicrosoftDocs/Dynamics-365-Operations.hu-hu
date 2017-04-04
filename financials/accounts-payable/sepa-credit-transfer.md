---
title: "SEPA átutalás áttekintése"
description: "Ez a cikk ISO 20022 átutalások, egyetlen euró SEPA terület kifizetések (típusú) átutalások és egyéb elektronikus fizetések szállítók általános ismertetését tartalmazza. A SEPA típusú átutalások euróban vállalattól vagy egy másik vállalat egyedi vagy egyéni fizetési bizonyos típusú. A témakör azt is bemutatja, hogyan lehet beállítani, és továbbítja az átadás követel fizetési fájl."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>SEPA átutalás áttekintése

Ez a cikk ISO 20022 átutalások, egyetlen euró SEPA terület kifizetések (típusú) átutalások és egyéb elektronikus fizetések szállítók általános ismertetését tartalmazza. A SEPA típusú átutalások euróban vállalattól vagy egy másik vállalat egyedi vagy egyéni fizetési bizonyos típusú. A témakör azt is bemutatja, hogyan lehet beállítani, és továbbítja az átadás követel fizetési fájl.

## <a name="what-is-a-credit-transfer-message"></a>Mi az a hitel átviteli üzenet?
Az követel átviteli üzenet egy kérést, amely saját számlájára alapok áthelyezése a hitelező küld egy kezdeményező fél (cég). Vannak sok ország-/ területspecifikus és a bank-specifikus megvalósítások átutalás üzeneteket. Néhányan közülük egy ország használatosak, és néhány egyre szabványok. Egy jól megalapozott globális szabvány ISO 20022 és a vizsgálat kezdeményezéséről üzeneteket, például átutalás. Az alábbi ábrán látható a kapcsolatok és a kijelölt jóváírások átviteli üzenetek fedezeti. 
![Az átvitel követel](./media/credit-transfer.jpg) hitel átviteli üzenetek\[/felirat\] 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Mik az ISO 20022 és a SEPA típusú támogatások?
Az Egységes Euro Fizetési Övezet (SEPA) az Európai Bizottság által került meghatározásra, és a szabályai előírják, hogy minden elektronikus kifizetés belföldinek számít, függetlenül az egyes személyek, vállalatok, szervezetek vagy bankok elhelyezkedésétől. Nincs nemzeti fizetések és a határokon átnyúló fizetések közötti különbség. A SEPA típusú 28 tagállamai az Európai Unió (EU), és még Izland, Liechtenstein, Norvégia, Svájc, Monaco, és a San Marino tartalmazza. A SEPA egységes piacot teremt az Európai Gazdasági Térségen (EGT) belüli kifizetési tranzakciók számára. A várakozások szerint a SEPA csökkenteni fogja a bankok, vállalatok és személyek által használt és kezelt kifizetési formátumok számát. Az Európai Bizottság a SEPA átutalások jogi alapját a Pénzforgalmi szolgáltatási irányelven (PSD) keresztül alakította ki. Az Európai Fizetési Tanács (EPC) a SEPA-t a következő tevékenységekkel támogatja:

-   A SEPA elektronikus átutalások szabványait az ISO-20022 univerzális pénzügyi iparág XML üzenetformátum segítségével állítja be.
-   Megállapítja az euró kifizetések kezelési szabályait és irányelveit.

Az európai bankokból álló EPC kereskedelmi és műszaki keretrendszereket fejleszt a SEPA-fizetőeszközökhöz. Háromféle SEPA tranzakció van használatban:

-   SEPA átutalás
-   Beszedési megbízás
-   Kártyák

## <a name="what-is-a-sepa-credit-transfer"></a>Mi a SEPA átutalás?
A SEPA átutalás olyan kifizetés, amely egy vállalattól vagy személytől egy másik vállalatnak vagy személynek történik. A kifizetésnek euróban kell történnie, és tartalmaznia kell mindkét fél nemzetközi bankszámlaszámát (IBAN) és bankazonosító kódját (BIC). (A BIC szokás is Society for Worldwide bankközi pénzügyi telekommunikációs társaság \[SWIFT\] kód.) Ezenkívül tranzakciós költségek megosztása a felek. A felek között előforduló átutalások az ISO-20022 kifizetés-feldolgozási szabványt és az EPC által meghatározott XML fájlokat és formátumot kötelesek használni.

## <a name="how-is-a-credit-transfer-implemented"></a>Hogyan történik az átutalást?
Az európai országok követel átviteli fizetési formátumát az elektronikus jelentési (ER) és a fizetési szolgáltatás használata 365 Dynamics műveletek valósul meg. Néhány más régiókban használt hitelkártya letöltési formátumok örökölt fizetési keretében továbbra is használható. Sok más formátumok között nincsenek tizenkét ISO 20022 követel átviteli fájlformátumok elérhető. Ezek az exportálási formátumok a SEPA típusú ISO 20022 XML-szabványoknak. -Euro fizetési átutalások országokkal felhasználási és a SEPA típusú hitel átviteli rendszer szabályzat, az EPC által kiadott euro-fizetési 8.2 verzió a létrehozására használják. Átutalások valósíthat meg, mielőtt kapcsolatba kell lépnie a bank elektronikus banki fájlok feltöltéséhez szükséges szoftver beszerzése. A szoftver a Bank fizetési megbízásokat tartalmazó XML-fájlok átvitelére használhatjuk.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Milyen hitel letöltési formátumok jelenleg támogatott műveletek Dynamics 365?
Mindig a megosztott digitáliseszköz-tár látogassa meg a Microsoft Dynamics életciklus szolgáltatások (LCS) és legfrissebb elérhető fájlok, amelyek az eszköz típusa megtekintéséhez **GER konfigurációs**. A következő szakaszban, a "Mit kell beállítani?", a témakört, amely ismerteti a rendelkezésre álló beállítások áttekintése és a kijelölt konfiguráció importálása egy LCS tárház létrehozása mutató hivatkozást tartalmaz.

## <a name="what-do-i-have-to-set-up"></a>Mit kell beállítanom?
-   Átutalási fájlok létrehozása, előtt legalább egy aktív hitelkártya-átviteli konfigurációs kell a ER konfigurációk importálja. További tudnivalókért lásd: [letöltés elektronikus jelentési szolgáltatások életciklus konfigurációk](https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Számlák fizetési kötelezettségek módok konfigurálásakor jelölje ki a **általános elektronikus jelentés** jelölőnégyzetet, és válassza ki a megfelelő jóváírás átviteli formátumot (például **ISO 20022 átutalás (AT)**) az exportálási formátum beállításokkal.
-   Akkor is be kell állítania Dynamics 365 műveletek jogi személy és a bankszámla adatait.
-   Bankszámlaszámok, IBANs, és néha a SWIFT-kód (BICs), vagy más azonosítók érvényes átutalás kifizetések létrehozása érdekében szükségesek. Ezért be kell állítania azokat a szállító bankszámla és a bankszámla átvitelét igénylő szervezet.
-   További információ szükség lehet, például a felek, hogy a hitel átviteli üzenetben említett hozzáadottérték-adó (HÉA) számokat. Ezt az információt be kell állítani a szállítók és a jogi személy azt kérik.
-   Előfordulhat, hogy egyes fiókok fizetendő többnyire ISO 20022-alapú fizetési módok, fizetési módszerek esetében további beállítási **fizetési formátum kódkészletek**, mint **típusú szolgáltatás** = **SLEV**. Ezeket a kódokat használják kiegészítő címkézés a fizetési tranzakciók kifizetés feldolgozása során. Hasonló alapértelmezett értéket a fizetési kódok, **kategória célja**, **kamat termő**, **helyi eszköz** és **szolgáltatási szint** két helyen állítható. Az első helyen **számlák kötelezettségek kifizetési napló fejléce**, a második pedig **számlák fizetési kötelezettségek módszerek**. Kifizetési napló sorok létrehozását követően fizetési napló fej fizetési kód értékek vannak naplósorból át, ha nincs beállítva, a fizetési módok értékeit használják.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Milyen paramétereket elérhetők az átadás fizetések jóváírás létrehozása?
Meghatározott paraméterek listája attól függ, hogy a hitel átviteli formátum. A következő táblázat a paraméterek érhetők el ISO 20022 követel átviteli kifizetési fájl Németország a szállítói kifizetési napló létrehozásakor. A rendelkezésre álló lehetőségek segítségével a **fut a háttérben** lap futtatása Fizetésgenerálás kötegelt módban.

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
<li><strong>Strd</strong> – ezzel a beállítással a strukturált formátum használata, ha egy fizetési sort ellen egy számla kiegyenlítése. Ez a beállítás nem érhető el az ország-/ területspecifikus exportálási formátumok, Franciaország, Németország és Hollandia.</li>
<li><strong>Strukturálatlan</strong> – Válassza ezt az opciót a strukturálatlan formátum használatához, amikor a kifizetést több számlával szemben számolnak el. A kiegyenlített számlák számlaszámait a rendszer összefűzi, és átutalási információként használja. ISO 20022 megfelelően iránymutatásokat, átutalási strukturálatlan adatok korlátozódik 140 karakter.</li>
</ul></td>
</tr>
<tr class="even">
<td>Számlák száma</td>
<td>A számlák számát adja meg, hogy a <strong>kifizetési bizonylat</strong> jelentést nyomtat ki.</td>
</tr>
<tr class="odd">
<td>Sorszám</td>
<td>Adjon meg egy sorszámot a fájl azonosításához. A sorszám jelenik meg a <strong>részvételi bizonylat</strong> jelentés.</td>
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
A nemzetközi bankszámlaszám (IBAN) és a banki azonosító számát (BIC) sok országban/régióban világszerte minden fiók azonosítására szolgálnak. Ezek közé tartoznak a 34 SEPA típusú országokban/régiókban. Adja meg a BIC kódja az **SWIFT kód** mező és az IBAN a a **IBAN** mező. Hitelező bankszámla és a vevő bankszámla ezekben a mezőkben található a **további azonosítási** gyorslapján a **bankszámla** lapján a **bankszámlák** oldalon. SEPA típusú kifizetések BIC használata már nem érvényesül.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Hogyan küldjem el a fizetési fájlt a banknak?
Kifizetések létrehozása, amikor a fizetési fájl jön létre, és megkérdezi, hogy menteni a böngészőből elérhető helyre. A következő lépés, hogy az XML-fájlt küld a bank. Ez a folyamat bankról bankra változik. Kövesse a banktól kapott utasításokat fájlok banki feldolgozásra való feladásához.


