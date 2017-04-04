---
title: "SEPA beszedési megbízás – áttekintés"
description: "Az egységes euro-pénzforgalmi övezet (SEPA) az Európai Bizottság által került meghatározásra, és szabályai előírják, hogy minden elektronikusan küldött kifizetés belföldinek számít, függetlenül az egyes személyek, vállalatok, szervezetek vagy bankok elhelyezkedésétől. Az országon belüli és a nemzetközi kifizetések között nincs különbség. A SEPA magában foglalja a 28 Európai Uniós (EU) tagállamot, csak úgy mint Izlandot, Liechtensteint, Norvégiát, Svájcot, Monacót és San Marinót. A SEPA egységes piacot teremt az Európai Gazdasági Térségen (EGT) belüli kifizetési tranzakciók számára. A várakozások szerint a SEPA csökkenteni fogja a bankok, vállalatok és személyek által használt és kezelt kifizetési formátumok számát."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 849fea6030c665e1724c3fc8f31353dd4bafed27
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-direct-debit-overview"></a>SEPA beszedési megbízás – áttekintés

Az egységes euro-pénzforgalmi övezet (SEPA) az Európai Bizottság által került meghatározásra, és szabályai előírják, hogy minden elektronikusan küldött kifizetés belföldinek számít, függetlenül az egyes személyek, vállalatok, szervezetek vagy bankok elhelyezkedésétől. Az országon belüli és a nemzetközi kifizetések között nincs különbség. A SEPA magában foglalja a 28 Európai Uniós (EU) tagállamot, csak úgy mint Izlandot, Liechtensteint, Norvégiát, Svájcot, Monacót és San Marinót. A SEPA egységes piacot teremt az Európai Gazdasági Térségen (EGT) belüli kifizetési tranzakciók számára. A várakozások szerint a SEPA csökkenteni fogja a bankok, vállalatok és személyek által használt és kezelt kifizetési formátumok számát.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Mi az a cél a SEPA típusú közvetlen számlaterhelések?
---------------------------------------

SEPA típusú közvetlen tartozik lehetővé teszi, hogy a hitelező alapok összegyűjtésére a vevő bankszámla, feltéve, hogy a hitelező aláírt megbízást adtak a vevő által. A vevő aláír egy felhatalmazást, amellyel engedélyezi a hitelezőnek a fizetés beszedését, és saját bankjának utasítást ad a pénz kifzetésére. 

A SEPA beszedési megbízások a történelembenelőször olyan eszközt hoztak létre, amely a 32 SEPA országban/ régióban országon belüli és határon átnyúló eurobeszedési megbízásokhoz is használható. 

Ehhez két rendszer érhető el: a SEPA Core beszedési megbízások valamint a SEPA vállalatközi (B2B) beszedési megbízások sémája. Mindkét séma ugyanazt a fájlformátumot használja.

## <a name="what-is-the-core-direct-debit-scheme"></a>Mi az a Core beszedési megbízási séma?
A SEPA Core beszedési megbízási sémája az alapséma. Az alábbi tulajdonságok jellemzik:
-   Az átutalás euróban történik (még akkor is, ha a bankszámlák más pénznemben vannak nyilvántartva).
-   A vevő és a hitelező is a SEPA-térségen belüli banknál kell számlát vezessen.
-   A vevőnek aláírt felhatalmazást kell adnia a hitelezőnek.
-   A felhatalmazás az utolsó beszedés után 36 hónappal lejár.
-   A hitelezőnek meg kell őriznie a felhatalmazásokat azok érvényességi idején keresztül, és az utolsó beszedés után legalább 14 további hónapig.
-   A séma egyetlen (egyszeri) vagy ismétlődő beszedésekhez is használható.
-   A vevőnek indoklás nélküli joga van az összeg visszatérítését kérni a számla megterhelése után következő nyolc héten keresztül.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Mit az a vállalatközi (B2B) SEPA beszedési megbízási séma?
A SEPA B2B beszedési megbízási sémája a vállalatok közötti tranzakciókra vonatkozik, és a SEPA Core beszedési megbízási sémára épül. A fő különbségek a következők:
-   A SEPA B2B beszedési megbízási sémája magánszemély (fogyasztó) típusú vevő esetén nem engedélyezett.
-   A vevő nem jogosult a visszatérítésre a tranzakció engedélyése után.
-   A vevő bankjának kell meggyőződnie róla, hogy a beszedés felhatalmazáson alapul, a beszedésnek a felhatalmazás alapján való ellenőrzésével. A vevők és a vevői bankok meg kell egyezzenek az egyes beszedési megbízásokon elvégzett ellenőrzésben.
-   Ez a séma gyorsabb beszedési megbízásokat tesz lehetővé, és lecsökkenti a visszatérítési időszakot.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Használhatom a COR1 sémát beszedési megbízások felhatalmazásainál?
Igen. Használhatja a COR1 sémát a SEPA beszedési megbízások alkalmazásánál Ausztriában, Belgiumban, Németországban, Franciaországban, Olaszországban, Spanyolországban és Hollandiában. Ez a séma rövidebb előzetes értesítési periódust tartalmaz a hitelező számára a beszedéshez.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Mi az a nemzetközi bankszámlaszám (IBAN) és a bankazonosító kód (BIC)?
A nemzetközi bankszámlaszám (IBAN) és a bankazonosító kód (BIC) minden számla azonosítható a 32 SEPA országban/régióban. A SWIFT-kód és az IBAN az IBAN mezőben adja meg a BIC. Mindkét mező a további azonosítás gyorslapon található a bankszámla lapon a bankszámlák oldalon. Ez mind a hitelező, mind a vevő bankszámlájára érvényes.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Hol rögzíthetem a hitelező azonosítóit (beszedési megbízási azonosítóit)?
A SEPA rendszerben az egyes hitelezőket egyedi azonosítókód azonosítja. Ez az azonosító lehetővé teszi a vevő és a vevői bank számára a beszedési megbízások szűrését, hogy azután a vevői utasítások alapján lehessen feldolgozni vagy elutasítani az egyes beszedési megbízásokat. A hitelezőnek saját bankjától kell azonosítót kérnie. Adja meg az azonosítót a Beszedési megbízás azonosító mezőben a bankszámla jogi személyének.

## <a name="what-are-mandates"></a>Mi az a felhatalmazás?
A vevő aláír egy felhatalmazást, amellyel engedélyezi a hitelezőnek a fizetés beszedését, és saját bankjának utasítást ad a pénz kifzetésére. A vevő papíron vagy elektronikus formában is kiadhatja meghatalmazását. Alapértelmezés szerint a meghatalmazás 36 hónappal az utolsó beszedési megbízás után jár le.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Hol határozható meg a SEPA beszedési megbízás fájlformátuma (ISO-20022)?
A SEPA adatformátumok az ISO-20022 üzenetszabványkészleten alapulnak. Ön jelölőnégyzetet az általános elektronikus jelentési, és válasszuk ki a SEPA típusú közvetlen tartozik egy exportálási formátum beállításokkal fiókok Kinnlevőségek kifizetési módok konfigurálásakor. Használhatja azt a fizetési módot, amikor létrehoz egy kifizetési fájlt egy vevő fizetési naplójában.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>Milyen fájlformátumokban tudok SEPA beszedési megbízási fizetésfájlokat generálni?
Létrehozhat elektronikus fizetési fájlokat a SEPA beszedési megbízásokhoz a következő formátumokban:
-   SEPA beszedési megbízás kifizetési fájlok a PAIN.008.001.02 XML fájlformátumban Belgiumban, Németországban, Spanyolországban, Franciaországban, Olaszországban és Hollandiában.
-   SEPA beszedési megbízási kifizetési fájlok a PAIN.008.001.02 XML fájlformátumban Ausztria és a PAIN.008.003.02 XML fájlformátumban Németországban.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Hogyan kezelhetők a visszatérítések és visszaküldések a SEPA beszedési megbízások vonatkozásában?
A vevőnek mindkét SEPA beszedési megbízási rendszerben rendelkezik bizonyos visszatérítési jogokkal. A vevő az esedékességi dátum után nyolc héten belül jogosult bármely engedélyezett tranzakciót visszahívni, indoklás megadása nélkül. Abban az esetben, ha a tranzakció még nem került engedélyésre, ez az időszak az esedékességi dátum utáni 13 hónap. Bármely kifizetés sztornírozása, amely manuálisan lett végrehajtva a Kifizetés érvénytelenítése gombbal a Vevői tranzakciók oldalon.




