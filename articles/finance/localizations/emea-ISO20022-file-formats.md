---
title: ISO20022 fájlok importálása
description: Ez a témakör ismerteti az ISO-20022 camt.054 és pain.002 formátumú fizetési fájlok importálását a Microsoft Dynamics 365 Finance szolgáltatásba.
author: neserovleo
manager: AnnBe
ms.date: 07/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, CustBankAccounts, VendPaymMode, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 48738f6af67bf40cac084d65aa4ff01935259c85
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209926"
---
# <a name="import-iso20022-files"></a>ISO20022 fájlok importálása

[!include [banner](../includes/banner.md)]

A következő formátumú fizetési fájlokat importálhatja:

 - **ISO20022 camt.054 jóváírási bizonylat** – Ilyen formátumú fájlból bejövő befizetéseket importálhat az Ügyfél fizetési naplójába.
 - **ISO20022 pain.002 visszáru** és **ISO20022 camt.054 jóváírási bizonylat** – Az ilyen formátumú visszárufájlokat a kötelezettségek kifizetési naplójába importálhatja.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>A camt.054 jóváírásibizonylat-fájl importálásának előfeltételei
Teljesítenie kell az alábbi előfeltételeket a banki értesítések camt.054.001.002 formátumban történő importálásához az ügyfél fizetési naplójába.

1. Importálja az **ISO20022 camt.054** elektromos jelentési (ER) konfigurációt a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból. Ezután, a **Vevői fizetési mód** oldalon, az **Importformátum konfigurációja** mezőben válassza ki a konfigurációt. További információ: [Fizetési módok fájlformátumai](emea-select-file-formats-for-the-method-of-payments.md).
2. A **Minden vevő** oldalon adjon meg egy nevet és egy szervezetszámot minden vevőnél.
3. A **vevői bankszámla** oldalon, a vevő bankszámlájának rekordja beállítása az alábbi információk megadásával: IBAN-száma és a bank számla számát, és a SWIFT-kód vagy útvonalszám.
4. A **Bankszámlák** oldalon, a vevő bankszámlájának rekordja beállítása az alábbi információk megadásával: IBAN-száma és a bank számla számát, és a SWIFT-kód vagy útvonalszám.

   > [!NOTE]
   > Továbbfejlesztett banki egyeztetés használni tervezi a **egyeztetés** gyorslapon állítsa a **a banki egyeztetés speciális** lehetőséggel **Igen**. Fel nem adott importált fizetések egyeztetni szeretné, ha a **bankszámlakivonatok használja az elektronikus fizetések visszaigazolására** lehetőséggel **Igen**.

5. Választható: A a **Tranzakciókód-hozzárendelés** lapon állítsa be a bank Kifizetésitranzakció-kódok a fájlt, és a banki tranzakciótípusok közötti megfeleltetés.
6. Ha a fájl tartalmazza a tranzakció fel szeretné adni a beérkező fizetés és költségek, létrehozni a kifizetési díjat a **vevői kifizetés díja** oldalon. Ezt a **fizetési módok** oldalon, a kifizetési díj hozzárendelése a bankszámlával kifizetési díjak beállításában.
7. Ha fogja tartalmazni az ISR-hivatkozások (érvényes jogi személyek Svájcban) ESR kifizetések importálására fog sor kerülni, hajtsa végre a következő beállításokat:

    - A **vevői kifizetések, számla hosszúság** mezőbe írja be a vevőkód használt hosszát, ISR-hivatkozás vagy a vevő azonosítása automatikus.
    - Győződjön meg arról, hogy a vevő számát és a számla száma (Számsorozatok) csak számjegyeket tartalmazhat. Más karaktereket nem tartalmazhatnak. A számla száma nem lehet a vezető nullákat.
    - Az ESR, BESR gyorslapon adja meg a jogi személyhez tartozó bankszámlaszámokat és regisztrációs azonosítókat. További tudnivalók: [ESR vevői importkifizetések](emea-che-esr-customer-payments-import.md), mert hasonló beállításokat kell megadni.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>A követel bizonylat camt.054 fájl importálása a vevői kifizetési naplóhoz
1. A **vevő kifizetési naplósoraiban** lap **funkciók** > **Importkifizetések**.
2. Válassza ki, amely rendelkezik a szükséges beállításokat az ISO20022 camt.054 formátumhoz fizetési mód.
3. Adja meg a szükséges paramétereket és a fájl elérési útját, és kattintson a **OK**. Megtörténik a fájl importálása.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Az pain.002 visszáru és camt.054 jóváírási bizonylat előfeltételei – Az ilyen formátumú visszárufájlokat a kötelezettségek kifizetési naplójába importálhatja.
Hajtsa végre a következő formátumban ISO20022 banki üzenetek importálása a következő előfeltételek az **szállítói kifizetések átviteli** oldal: pain.002.001.003 állapotát vissza üzeneteit és camt.054.001.002 jóváírási bizonylat.

1. Importálás a **ISO20022 camt.054** és **ISO20022 pain.002** ER konfigurációk LCS közül.
2. A **szállítói fizetési mód** oldalon, a a **visszatérési formátumát konfigurációs** és **visszatérési formátumát másodlagos konfiguráció** mezőben válassza ki az importált ER konfigurációt. Az általános elektronikus a kiválasztott fizetési mód visszatérési formátumát aktiválni kell.
3. A **visszáru-formátum állapot leképezés** a megfeleltetés pain.002 állapotok és a szállítói kifizetési napló állapotok között állapotkódok beállítása lapon.

    Íme, egy példa az állapotbeállításra.

    Visszatérési állapot | Fizetés állapota
    --------------|---------------
    RJCT          | Elutasítva
    ACCP          | Elfogadva
    ACSP          | Fogadott

4. A **visszatérési formátumát hibakódok** pain.002 hibák kódjait és leírásait, összhangban a külső ISO20022 állapot okkódok beállítása lapon.

    Íme egy példa egy hibakódbeállításra.

    Kód | Név
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Ha a fájl tartalmazza a tranzakció fel szeretné adni a beérkező fizetés és költségek, létrehozni a kifizetési díjat a **vevői kifizetés díja** oldalon. Ezt a **fizetési módok** oldalon, a kifizetési díj hozzárendelése a bankszámlával kifizetési díjak beállításában.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>A pain.002 állapota visszaadási vagy camt.054 tartozik bizonylat-fájlok importálása a szállítói kifizetési naplóhoz
1. Nyissa meg a **átutalása** a Kötelezettségek menü oldalra.
2. A **átutalása** lap **Visszárufájl - Szállító**.
3. Válassza ki, amely rendelkezik a szükséges beállításokat az ISO20022 camt.054 formátumhoz, majd kattintson az **OK** gombra.
4. Válassza ki azt a fájlformátumot, amelyet importálni kíván, majd kattintson az **OK** gombra.
5. Adja meg a szükséges paramétereket és a fájl elérési útját, és kattintson a **OK**.

A pain.002 fájlt importál, ha a szállítói kifizetési sorok állapota frissül, az importált fájlban szereplő információk alapján.

Ha a camt.054 fájlt importál, meg kell adnia a következő kiegészítő paraméterek:

- **Díj azonosítója** – adja meg a díj azonosítója, amellyel így meghatározhatja az új fizetési Díjsorok, ha a költség összegét a camt.054 fájlban található meg a szállítói fizetési napló sorából létrehozandó.
- **Új naplónév** és **új napló leírása** – adja meg a nevét, és át szeretné vinni a feldolgozott tranzakciók napló leírása. Az átvitel után az új bizonylatszámmal az új napló kell hozzárendelni.
- **Beszedési tranzakciók importálása** – állítja ezt a beállítást **Igen**, ha a kimenő közvetlen tételek kell importálhatók a szállítói kifizetési naplóhoz.
- **Naplónév** – adja meg egy új naplónevet a beszedési megbízás importált tranzakciókhoz.
- **Tranzakciók kiegyenlítése** – állítja ezt a beállítást **Igen** Ha importált szállítói kifizetések számlákkal, amelyek megtalálhatók a rendszerben ki kell egyenlíteni.

Megtekintheti az importált adatokat a **átutalása** oldalon. 

## <a name="additional-details"></a>További részletek

Ha formátumkonfigurációt importál az LCS-rendszerből, a teljes konfigurációs fát importálja, ami azt jelenti, hogy a Modell és a Modell hozzárendelése konfigurációk is szerepelnek benne. A Fizetési modellben a 8-as verziótól kezdve a hozzárendelések külön ER-konfigurációkban találhatók a megoldásfán (Fizetési modell hozzárendelése 1611, Fizetési modell hozzárendelése az ISO20022 célhoz stb.). Egyetlen modell (Fizetési modell) keretén belül több különböző fizetési formátum létezik, így a hozzárendelések különálló kezelése a könnyű karbantartás kulcsa. Tegyük fel a következő esetet: az ISO20022 kifizetések segítségével általános átutalási fájlokat hoz létre, majd importálja a bank visszaküldött üzeneteit. Ebben az esetben a következő konfigurációkat kell használnia:

 - **Fizetési modell**
 - **Fizetési modell hozzárendelése 1611** – a rendszer ezt a hozzárendelést használja az exportfájl létrehozásakor
 - **Fizetési modell hozzárendelése az ISO20022 célhoz** – ez a konfiguráció tartalmazza az adatimportáláshoz („a célhoz” hozzárendelési irány) használt összes hozzárendelést
 - **ISO20022 átutalás** – ez a konfiguráció tartalmazza felelős az exportálási fájl létrehozásáért (pain.001) felelős formátum-összetevőt a Fizetési modell hozzárendelése 1611 alapján, valamint egy modell-hozzárendelési összetevő-formátumot, amelyet Fizetési modell hozzárendelése az ISO20022 célhoz fizetési modellel együtt használ a rendszer az exportált fizetések regisztrálására a további importálási célok érdekében (importálás a CustVendProcessedPayments műszaki táblában).
 - **ISO20022 átutalás (CE)**, ahol a CE az országjelzésnek felel meg – az ISO20022 átutalás származtatott formátuma azonos struktúrával és az egyes országspecifikus eltérésekkel
 - **Pain.002** – ezt a formátumot kell a Fizetési modell hozzárendelése az ISO20022 célhoz fizetési modellel együtt használni a pain.002 fájlnak a szállítói kifizetések átvitele naplóba történő importálása érdekében
 - **Camt.054** – ezt a formátumot kell a Fizetési modell hozzárendelése az ISO20022 célhoz fizetési modellel együtt használni a camt.054 fájlnak a szállítói kifizetések átvitele naplóba történő importálása érdekében. Ugyanaz a formátumkonfiguráció fog szerepelni a vevői kifizetések importálása funkcióban, de a rendszer különböző hozzárendelést fog használni a Fizetési modell hozzárendelése az ISO20022 célhoz konfigurációban.

Az elektronikus jelentéssel kapcsolatos további tudnivalókat lásd: [Elektronikus jelentések áttekintése](../../dev-itpro/analytics/general-electronic-reporting.md).

## <a name="additional-resources"></a>További erőforrások
- [Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban](./tasks/create-export-vendor-payments-iso20022-payment-format.md)
- [ISO20022 jóváírási konfiguráció importálása](./tasks/import-iso20022-credit-transfer-configuration.md)
- [ISO20022 beszedési megbízási konfiguráció importálása](./tasks/import-iso20022-direct-debit-configuration.md)
- [Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)
- [Vállalati bankszámlák beállítása ISO20022 beszedési megbízásokhoz](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)
- [Vevők és vevői bankszámlák beállítása ISO20022 beszedési megbízásokhoz](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)
- [Fizetési mód beállítása ISO20022-jóváírás átutalásához](./tasks/set-up-method-payment-iso20022-credit-transfer.md)
- [Fizetési mód beállítása ISO20022 beszedési megbízáshoz](./tasks/setup-method-payment-iso20022-direct-debit.md)
- [Szállítók és szállítói bankszámlák beállítása ISO20022 típusú átutalásokhoz](./tasks/set-up-vendor-iso20022-credit-transfers.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]