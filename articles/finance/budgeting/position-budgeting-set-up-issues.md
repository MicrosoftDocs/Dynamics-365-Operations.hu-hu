---
title: Beosztás-költségvetéskészítés hibaelhárítása
description: Ez a cikk olyan kérdésekre ad választ, amelyek a beosztás-költségvetés elkészítésekor merülhetnek fel. A költségvetési költségösszetevők, kompenzációs csoportok és a kompenzációs rácsok létrehozásával kapcsolatban leggyakrabban feltett kérdéseket tárgyalja.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3e3c2f8a69d620bd2babe0d8d55858d01b25436
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833113"
---
# <a name="position-budgeting-troubleshooting"></a>Beosztás-költségvetéskészítés hibaelhárítása

[!include [banner](../includes/banner.md)]

Ez a cikk olyan kérdésekre ad választ, amelyek a beosztás-költségvetés elkészítésekor merülhetnek fel. A költségvetési költségösszetevők, kompenzációs csoportok és a kompenzációs rácsok létrehozásával kapcsolatban leggyakrabban feltett kérdéseket tárgyalja. 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Miért nem található az Emberi erőforrásokban az előre jelzett beosztás oldal?
---------------------------------------------------------------

Az előre jelzett beosztások átkerültek a Költségvetés készítésébe.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Miért nem lehet törölni a költségvetési költségösszetevőt?
Az olyan költségvetési költségösszetevő nem törölhető, amely egy előre jelzett beosztáshoz van hozzárendelve. Mielőtt törölne egy költségvetési költségösszetevőt, el kell távolítania az összes előre jelzett beosztásból. **Tipp:** Az összes olyan beosztás eléréshez, amelyhez tartozik költségvetési költségösszetevő válassza ki a költségösszetevőt a **Költségvetési költségösszetevők** oldalon, majd kattintson a **Beosztások frissítése** lehetőségre. Az adott költségösszetevőt használó beosztások a felső rácson szerepelnek.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Hogyan távolíthatom el a költségösszetevőt több előre jelzett beosztásból, anélkül, hogy mindegyiket megnyitnám?
A költségösszetevő nem távolítható el. Azonban ha úgy módosítja a kezdő és záró dátumokat, hogy kívül essenek a költségvetés-tervezési cikluson, akkor a költségösszetevő nem lesz többé hozzárendelve az ezen költségtervezési ciklusban található előre jelzett beosztásokhoz. Ezen módosítás végrehajtásához nyissa meg a költségvetési költségösszetevőt, majd a **Költségszámítás** gyorslapon kattintson a **Dátum módosítása** lehetőségre, és változtassa meg az érvénybe lépési dátumot vagy a lejárati dátumot. Ezután kattintson az **OK** gombra, hogy automatikusan frissítse az összes előre jelzett beosztást, amelyekhez a költségösszetevő hozzá van rendelve. **Tipp:** Ha ezt a módszert alkalmazza, ügyeljen arra, hogy ezzel eltávolítja a költségvetési költségösszetevőt **minden** olyan előre jelzett beosztásból, amelyben a kezdő és záró dátumok már nem a megfelelő tartományba esnek. Ha nem ezt a hatás akarja elérni, akkor meg kell nyitnia minden egyes előre jelzett beosztást, amelyből el kívánja távolítani a költségvetési költségösszetevőt és a módosítást manuálisan kell elvégeznie.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Miért nem adható meg a költségvetési költségösszetevő gyorslapján éves összeg?
Éves összeg nem adható meg, ha költségvetési költségösszetevők vannak a **Számítás alapja** gyorslapon, mert a rendszer százalékos értéket igényel a számításhoz. Az érték módosításához távolítson el minden költségvetési költségösszetevőt a **Számítás alapja** gyorslapról.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Miért nem lehet módosítani a kereseti költségvetési költségtípust más költségtípusra?
Néhány költségvetési költségösszetevő a kereseti költségösszetevőt használja a számítás alapjául. Ha módosítani szeretné az **Előirányzott költség típusa** mezőt, akkor távolítsa el a kereseti költségösszetevőt az összes költségvetési költségösszetevő **Számítás alapja** gyorslapjáról.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Miért nem módosítható egy költségvetési költségösszetevő költségösszetevő-sorainak dátuma?
Nem módosíthatja a költségvetési összetevő sorának dátumát, ha a költségvetési költségösszetevőt egy előre jelzett beosztás használja. Ez a korlátozás segít garantálni, hogy az előre jelzett beosztások mindig megfelelnek a költségvetési költségösszetevő irányelveinek. A dátum módosításához a **Költségszámítás** gyorslapon kattintson a **Dátum módosítása** lehetőségre, és írja be az új dátumokat. Ezután kattintson az **OK** gombra, hogy frissítse az összes előre jelzett beosztást, amelyekhez a költségösszetevő hozzá van rendelve.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Miért nem lehet módosítani a költségvetési költségösszetevő költségeit a Kompenzációs csoport lapon?
Csak a **Költségvetési költségösszetevők** oldalon hozhat létre és módosíthat költségvetési költségösszetevőket.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Miért jelenik meg egy hibaüzenetet egy előre jelzett beosztás esetén a költségösszetevő dátumának módosításakor?
Az előre jelzett beosztás költségösszetevő sorának dátuma a következő tartományokba kell hogy essen:

-   A beosztás aktiválási és kivezetési dátuma.
-   A költségvetési költségösszetevő aktiválási és lejárati dátuma.
-   Azon költségvetési ciklus kezdő és záró dátumai, amely az előre jelzett beosztás költségvetés-tervezési folyamatával van társítva.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]