---
title: "Szállítói együttműködés a vevőkkel"
description: "Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Operations rendszerben a beszerzési rendelésekkel kezelése és a bizományosi készlet figyelése során."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 11cd2242b5a575ae87b0dbcf6f8ce268fcea5377
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-with-customers"></a>Szállítói együttműködés a vevőkkel

Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Operations rendszerben a beszerzési rendelésekkel kezelése és a bizományosi készlet figyelése során.

Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Operations rendszerben. Figyelni és a beszerzési rendelésekhez, és szállítmány készlet figyelése információt tartalmaz. Egyben szállító együttműködés segítségével a számlák használata. További tudnivalókért lásd: [szállító együttműködési munkaterület számlázás](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Beszerzési rendelések intézése
A **Beszerzési rendelések visszaigazolási** munkaterülete lehetővé teszi, hogy válaszoljon a véleményezésre elküldött beszerzési rendelésekre. Lehetővé teszi a vevői műveletre várakozó beszerzési rendelések adatainak megtekintését, valamint a vevő által visszaigazolt, de még nyitva levő beszerzési rendelésekkel kapcsolatos információk megtekintését is. A **Beszerzési rendelések visszaigazolási** munkaterülete három listát tartalmaz:

-   **Beszerzési rendelések véleményezésre** -Ez a lista tartalmazza, amely akkor küld, és választ váró POs. Ha válaszolt, a beszerzési rendelés eltűnik a listáról. Ha a vevő új beszerzési rendelést küld még mielőtt az előzőre válaszolt volna, a legújabb verzió jelenik meg.
-   **Várakozás vevői műveletre** – Ez a lista a már megválaszolt, de a vevő által még nem jóváhagyott beszerzési rendeléseket jeleníti meg. Ha elfogadja a beszerzési rendelést, akkor nyomon követheti azt a listában addig, amíg az állapota **Visszaigazolva** státuszra nem vált. Ha visszautasítja a beszerzési rendelést vagy módosításokkal fogadta el, itt figyelheti azt addig, amíg a vevő az új verziót el nem küldi.
-   **Visszaigazolt beszerzési rendelések megnyitása** – Ez a lista tartalmazza az összes **Visszaigazolva** státuszú beszerzési megrendelését. Amikor a termékeket vagy szolgáltatásokat teljes mértékben bevételezte, a beszerzési rendelés eltűnik a listáról.

Az alábbi lista jeleníti meg a beszerzési rendelésekkel való munkához használható négy lapot: ebből kettő ugyanazokat az adatokat tartalmazza, mint a munkaterületi listák:

-   **Beszerzési rendelések ellenőrzésre** (lásd fent)
-   **Beszerzési rendelés szállítói visszaigazolásának előzményei** – Ezen a lapon található az összes beszerzési rendelés, valamint a szállítónak elküldött beszerzési rendelések minden verziója és a szállítótól beérkező válaszok.
-   **Visszaigazolt beszerzési rendelések megnyitása** (lásd fent)
-   **Az összes visszaigazolt beszerzési rendelés** – Ez a lap tartalmazza az összes visszaigazolt beszerzési rendelést, beleértve azokat is, amelyek esetében termékek vagy szolgáltatások érkeztek. Ezen lista segítségével követheti nyomon, hogy mely beszerzési rendelésekre küldhet számlákat.

### <a name="responding-to-purchase-orders"></a>Válasz a beszerzési rendelésekre

A vevőnek küldött, hogy tekintse át a beszerzési rendelések jelennek meg a **beszerzési rendelés-visszaigazolások** munkaterület és a **beszerzési rendelések véleményezésre** oldalon. Miután megnyit egy beszerzési rendelés, választhat elfogadni, elutasítás vagy módosításokkal elfogadja azt. A beszerzési rendelés fejlécében vagy az egyes sorokhoz csatolva mellékletek lehetnek. Lehetősége van arra is, hogy adatokat csatoljon a válaszában a beszerzési rendelés fejlécében vagy az egyes sorokban. Például előfordulhat, hogy az egyik sorhoz helyettesítő cikket javasol. A beszerzési rendelést PDF-fájlként megtekintheti nyomtatási előnézetben és ki is nyomtathatja az **Előnézet/nyomtatás** lehetőség használatával. Elrejtheti vagy megjelenítheti a következő dimenzióoszlopokat a **Dimenziók megjelenítése** művelettel: Telephely, Raktár, Szín, Méret, Stílus, Konfiguráció. Ha a **a változások elfogadása** beállítás, elfogadhatja vagy elutasíthatja az egyes sorok. A következő módosításokat is végezhet sorok:

-   Módosíthatja a dátumokat vagy a mennyiségeket. Ha módosítani szeretné a visszaigazolt szállítási dátumot minden sorban, használja a **Szállítási dátum frissítése** lehetőséget a beszerzési rendelés fejlécében.
-   Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján
-   Helyettesíthet egy cikket. Ehhez írja be a cikkleírást és a cikkszámot a **Külső** mezőben a **Soradatok** szakaszban.

Nem módosíthatja az árképzési adatokat vagy a költségeket, de megjegyzések segítségével javasolhat módosításokat. Ha a vevő a beszerzési rendelés új verzióját küldi el, ez rendelkezni fog egy verzió utótaggal, ami azt jelzi, hogy ez a korábban közölt beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével nyomon követheti az egyes rendelések előzményeit.

## <a name="monitoring-consignment-inventory"></a>Bizományosi készlet figyelése
Bizományosi készlet használatakor a szállító együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

-   **Beszerzési rendelések szállítmány készlet fogyasztó** -beszerzési rendelések a szállítmány készlet jön létre, amikor a tulajdonjogot a vevő a készlet. A bizományosi beszerzési rendelések csak a **Bizományosi készletet használó beszerzési rendelések** lapon jelennek meg. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon.
-   **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a készletet fogyasztó vállalatra ruházódott át. Ezt az információt a vevői számlák kibocsátására használhatja.
-   **Aktuális bizományosi készlet** – Ez a lap megjeleníti a vállalata tulajdonában levő aktuális bizományosi készletet, amely aktuálisan a vevők raktárában van.


<a name="see-also"></a>Lásd még
--------

[Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md)


