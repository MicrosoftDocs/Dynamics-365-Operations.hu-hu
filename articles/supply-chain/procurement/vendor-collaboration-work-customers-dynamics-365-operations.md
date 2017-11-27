---
title: "Szállítói együttműködés a vevőkkel"
description: "Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Finance and Operations rendszerben a beszerzési rendelésekkel kezelése és a bizományosi készlet figyelése során."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4ad7c4f14cf60b2f59124ac98d55c4b92edabb47
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-collaboration-with-customers"></a>Szállítói együttműködés a vevőkkel

[!include[banner](../includes/banner.md)]


Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Finance and Operations rendszerben a beszerzési rendelésekkel kezelése és a bizományosi készlet figyelése során.

Ez a témakör leírja, hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Finance and Operations rendszerben. Információkat tartalmaz a beszerzési rendelések figyelésével és nyomon követhetésével, valamint a bizományosi készlet figyelésével kapcsolatban. A szállítói együttműködést a számlázás során is használhatja. További tudnivalókért lásd: [Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

## <a name="working-with-purchase-orders"></a>Beszerzési rendelések intézése
A **Beszerzési rendelések visszaigazolási** munkaterülete lehetővé teszi, hogy válaszoljon a véleményezésre elküldött beszerzési rendelésekre. Lehetővé teszi a vevői műveletre várakozó beszerzési rendelések adatainak megtekintését, valamint a vevő által visszaigazolt, de még nyitva levő beszerzési rendelésekkel kapcsolatos információk megtekintését is. A **Beszerzési rendelések visszaigazolási** munkaterülete három listát tartalmaz:

-   **Beszerzési rendelések ellenőrzésre** – Ez a lista azokat a beszerzési rendeléseket jeleníti meg, amelyek a válaszára várnak. Miután válaszol, a beszerzési rendelés eltűnik a listáról. Ha a vevő új beszerzési rendelést küld még mielőtt az előzőre válaszolt volna, a legújabb verzió jelenik meg.
-   **Várakozás vevői műveletre** – Ez a lista a már megválaszolt, de a vevő által még nem jóváhagyott beszerzési rendeléseket jeleníti meg. Ha elfogadja a beszerzési rendelést, akkor nyomon követheti azt a listában addig, amíg az állapota **Visszaigazolva** státuszra nem vált. Ha visszautasítja a beszerzési rendelést vagy módosításokkal fogadta el, itt figyelheti azt addig, amíg a vevő az új verziót el nem küldi.
-   **Visszaigazolt beszerzési rendelések megnyitása** – Ez a lista tartalmazza az összes **Visszaigazolva** státuszú beszerzési megrendelését. Amikor a termékeket vagy szolgáltatásokat teljes mértékben bevételezte, a beszerzési rendelés eltűnik a listáról.

Az alábbi lista jeleníti meg a beszerzési rendelésekkel való munkához használható négy lapot: ebből kettő ugyanazokat az adatokat tartalmazza, mint a munkaterületi listák:

-   **Beszerzési rendelések ellenőrzésre** (lásd fent)
-   **Beszerzési rendelés szállítói visszaigazolásának előzményei** – Ezen a lapon található az összes beszerzési rendelés, valamint a szállítónak elküldött beszerzési rendelések minden verziója és a szállítótól beérkező válaszok.
-   **Visszaigazolt beszerzési rendelések megnyitása** (lásd fent)
-   **Az összes visszaigazolt beszerzési rendelés** – Ez a lap tartalmazza az összes visszaigazolt beszerzési rendelést, beleértve azokat is, amelyek esetében termékek vagy szolgáltatások érkeztek. Ezen lista segítségével követheti nyomon, hogy mely beszerzési rendelésekre küldhet számlákat.

### <a name="responding-to-purchase-orders"></a>Válasz a beszerzési rendelésekre

A vevő által küldött beszerzési rendelések megtekinthetők a **Beszerzési rendelések visszaigazolási** munkaterületén és a **Beszerzési rendelések véleményezésre** lapon. A beszerzési rendelés megnyitása után elfogadhatja, elutasíthatja vagy módosításokkal elfogadhatja azt. A beszerzési rendelés fejlécében vagy az egyes sorokhoz csatolva mellékletek lehetnek. Lehetősége van arra is, hogy adatokat csatoljon a válaszában a beszerzési rendelés fejlécében vagy az egyes sorokban. Például előfordulhat, hogy az egyik sorhoz helyettesítő cikket javasol. A beszerzési rendelést PDF-fájlként megtekintheti nyomtatási előnézetben és ki is nyomtathatja az **Előnézet/nyomtatás** lehetőség használatával. Elrejtheti vagy megjelenítheti a következő dimenzióoszlopokat a **Dimenziók megjelenítése** művelettel: Telephely, Raktár, Szín, Méret, Stílus, Konfiguráció. Ha az **Elfogadás módosításokkal** lehetőséget használja, akkor elfogadhatja vagy elutasíthatja az egyes sorokat. A sorokban az alábbi módosításokat lehet még végrehajtani:

-   Módosíthatja a dátumokat vagy a mennyiségeket. Ha módosítani szeretné a visszaigazolt szállítási dátumot minden sorban, használja a **Szállítási dátum frissítése** lehetőséget a beszerzési rendelés fejlécében.
-   Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján
-   Helyettesíthet egy cikket. Ehhez írja be a cikkleírást és a cikkszámot a **Külső** mezőben a **Soradatok** szakaszban.

Nem módosíthatja az árképzési adatokat vagy a költségeket, de megjegyzések segítségével javasolhat módosításokat. Ha a vevő a beszerzési rendelés új verzióját küldi el, ez rendelkezni fog egy verzió utótaggal, ami azt jelzi, hogy ez a korábban közölt beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével nyomon követheti az egyes rendelések előzményeit.

## <a name="monitoring-consignment-inventory"></a>Bizományosi készlet figyelése
Bizományosi készlet használatakor a szállító együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

-   **Bizományosi készletet használó beszerzési rendelések** – A bizományosi készletet használó beszerzési rendelések akkor jönnek létre, amikor az ügyfél lesz a készlet tulajdonosa. A bizományosi beszerzési rendelések csak a **Bizományosi készletet használó beszerzési rendelések** lapon jelennek meg. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon.
-   **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a készletet fogyasztó vállalatra ruházódott át. Ezt az információt a vevői számlák kibocsátására használhatja.
-   **Aktuális bizományosi készlet** – Ez a lap megjeleníti a vállalata tulajdonában levő aktuális bizományosi készletet, amely aktuálisan a vevők raktárában van.


<a name="see-also"></a>Lásd még
--------

[Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md)




