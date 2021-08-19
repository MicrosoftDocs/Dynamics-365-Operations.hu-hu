---
title: Beszedési megbízási felhatalmazás létrehozása vevő részére
description: Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51fea2b9a0f25b078abc3ca83ee02c585eaf465128bebba0234ffadb030ef42a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740050"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Beszedési megbízási felhatalmazás létrehozása vevő részére

[!include [banner](../../includes/banner.md)]

Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.


## <a name="create-a-bank-account"></a>Bankszámla létrehozása
1. A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.
2. A listában válasszon ki egy rekordot. Válassza ki például az US-001-et.
3. A Művelet panelen kattintson a **Vevő** elemre.
4. Kattintson a **Bankszámlák** lehetőségre.
5. Kattintson az **Új** elemre.
6. A **Bankszámla** mezőben adjon meg egy értéket.
7. Írjon be egy értéket a **Név** mezőbe.
8. Az **IBAN** mezőben adjon meg egy értéket.
9. Érték beírása a **Pénznem** mezőbe.
10. Kattintson a **Mentés** gombra.
11. Zárja be a lapot.
12. A **navigációs ablakban** nyissa meg ezt: **Modulok > Készpénz- és banki menedzsment > Bankszámlák > Bankszámlák**.
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. Kattintson a **Szerkesztés** lehetőségre.
16. Bontsa ki a **További azonosítás** gyorslapot.
17. Írjon egy értéket a **Beszedési megbízási azonosító** mezőbe.
18. Az **IBAN** mezőben adjon meg egy értéket.
19. Zárja be a lapot.
20. Zárja be a lapot.

## <a name="define-the-electronic-payment-method"></a>Elektronikus fizetési mód meghatározása
1. A **navigációs ablaktáblán** ugorjon a **Modulok > Követelések és beszedések > Fizetés beállítása > Fizetési módok** elemre.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Fizetési mód** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Fizetés típusa** mezőben adja meg az „Elektronikus fizetés” lehetőséget. A beszedési megbízási felhatalmazás fizetési módjában elektronikus fizetést kell beállítani.
6. Válassza az Igen lehetőséget a **Felhatalmazás szükséges** mezőben.
7. Zárja be a lapot.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Beszedési megbízási rendelet hozzáadása a vevőhöz.
1. A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.
2. A listában válasszon ki egy rekordot. Válassza ki például az US-001-et.
3. Kattintson a **Szerkesztés** lehetőségre.
4. Bontsa ki a **Fizetés alapértelmezései** gyorslapot.
5. A **Fizetési mód** mezőben adjon meg vagy válasszon ki egy értéket.
6. Bontsa ki a **Fizetés alapértelmezései** gyorslapot.
7. Bontsa ki a **Beszedési megbízási felhatalmazások** gyorslapot.
8. Kattintson a **Hozzáadás** parancsra.
9. A **Bankszámlák** mezőben adjon meg vagy válasszon ki egy értéket.
10. A **Hitelező bank mezőben** adjon meg vagy válasszon ki egy értéket.
11. A **Fizetés gyakorisága** mezőben adja meg, hogy várhatóan hány fizetést tervez feldolgozni ehhez a felhatalmazáshoz.
12. Kattintson az **OK** gombra.
13. Kattintson a **Nyomtatás** parancsra.
14. Kattintson a **Felhatalmazás jelentése** pontra.
15. Zárja be a lapot.
16. Kattintson a **Szerkesztés** lehetőségre.
17. Adja meg a dátumot az **Aláírás dátuma** mezőben.
18. Kattintson az **Igen** gombra.
19. Adja meg a felhatalmazás aláírásának helyét.
20. Kattintson az **OK** gombra.
21. Zárja be a lapot.

## <a name="create-a-free-text-invoice-with-mandate"></a>Szabadszöveges számla létrehozása felhatalmazással
1. A **Navigációs panelen** ugorjon ide: **Modulok > Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák**.
2. Kattintson az **Új** elemre.
3. Válassza ki a vevőt, akihez hozzáadta a felhatalmazást.
4. A **Beszedési megbízási felhatalmazás azonosítója** mezőben adjon meg, vagy válasszon ki egy értéket.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]