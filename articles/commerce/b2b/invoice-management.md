---
title: Számlakezelés B2B e-commerce webhelyekhez
description: Ez a témakör ismerteti Microsoft Dynamics 365 Commerce a vállalat és vállalat között létre tartozó e-commerce webhelyek számlakezelési lehetőségeit.
author: ShalabhjainMSFT
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: c1f3533eb711bf87fe226f5c61678b6939f35e13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274428"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Számlakezelés B2B e-commerce webhelyekhez

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti Microsoft Dynamics 365 Commerce a vállalat és vállalat között létre tartozó e-commerce webhelyek számlakezelési lehetőségeit.

A B2B tranzakciókat kezelő vállalatoknál be kell fogadniuk a vevői jóváírásra vonatkozó rendeléseket, majd a rendelés teljesítése után számlát kell küldeniük a vevőknek. A fizetési feltételek meg vannak határozva a vevőkhöz, és előfordulhatnak bizonyos engedmények, amelyek a vevők motiváltak arra, hogy időben vagy idő előtt fizethetnek. A B2B e-commerce webhelyek segítségével a vevők megtekinthetik az összes számlájukat, így növelheti annak a valószínűségét, hogy a kifizetések időben érkeziknek. A vevő egyszerűen szűrheti a számlákat, hogy a fizetett, a kifizetetlen és a részben kifizetett számlákat a határidővel együtt tekintse meg.

![Számlák lapja a B2B webhelyen.](../media/ViewInvoices.png)

> [!NOTE]
> A bejelentkezett felhasználó csak saját számláit tudja megtekinteni és kifizetni. Ha **be** **van** állítva szervezeti számla a Commerce Headquarters vevőrekordját a Számla és szállítás gyorsmenü Számla– legördülő menüjében, a felhasználó megtekintheti és kifizeti a szervezet számláját.

A B2B **webhely** Számlák lapján a felhasználó kiválaszthat egy kifizetetlen vagy **részben kifizetett számlát, majd kiválaszthatja a Számla kifizetése lehetőséget**. A kiválasztott számlát hozzáadja a rendszer a kosárhoz, és a felhasználó folytathatja a kifizetést. A felhasználó eldöntheti, hogy a számla teljes összegét, vagy csak egy részleges összeget fizeti ki. A felhasználó nem használhatja a számlán történő kifizetésre használt fizetési módot a számlák kifizetésére.

> [!NOTE]
> A számlákat csak akkor lehet a kosárhoz adni, ha jelenleg nincsenek benne cikkek. Fordítva, csak akkor lehet cikkeket hozzáadni a kosárhoz, ha jelenleg nincsenek benne számlák. A Microsoft a későbbi Commerce-verziókban el szeretné távolítani ezt a korlátozást.

![Bevásárlókocsi lapja egy B2B webhelyen](../media/PayInvoice.png)

A Számlák **lapon** a felhasználók a **számla** melletti Számla kérése lehetőséget is kiválaszthatják. Ily módon a felhasználó kérheti a számla részleteinek elküldését a regisztrált e-mail címére.

![Számla kérése párbeszédpanel.](../media/RequestInvoice2.png)

Miután egy felhasználó számlát kért, **a kérés átkerül a Saját számla lap B2B Kérések** **szakaszára**. **Ezt követően a P-0001** **és** a Rendelések és csatornakérések szinkronizálása feladat futtatása után a Commerce Headquarters elindítja a számlázási e-mailt, és a B2B kérés állapota készként lesz megjelölve.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
