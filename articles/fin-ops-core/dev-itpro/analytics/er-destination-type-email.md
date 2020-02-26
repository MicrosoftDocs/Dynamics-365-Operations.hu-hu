---
title: E-mail ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy e-mail célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019806"
---
# <a name="EmailDestinationType">E-mail célja</a>

[!include [banner](../includes/banner.md)]

Beállíthat egy e-mail célhelyet a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez. A célhely beállításai alapján a létrejövő dokumentumot a rendszer egy e-mail csatolmányaként küldi el.

Állítsa a **Bekapcsolva** opciót **Igen** állapotra egy eredményfájl email-ben történő küldéséhez. Ezen beállítás engedélyezése után szerkesztheti az e-mail címzettjeit, tárgyát és szövegét. Beállíthat állandó szöveget az e-mail tárgyaként és szövegeként, illetve használhat ER-[képleteket](er-formula-language.md) az e-mail szövegének dinamikus létrehozására. 

Elektronikus jelentéstételhez e-mail-címeket két módon konfigurálhat. A konfiguráció ugyanúgy fejezhető be, mint a Nyomtatás kezelése funkció. Ezenfelül e-mail-címet megoldhat úgy is, hogy képlettel közvetlenül hivatkozik az ER-konfigurációra.

[![E-mail céljának engedélyezése](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>E-mail-címek típusai

Amikor kiválasztja a **Szerkesztés** elemet a **Címzett** vagy **Másolatot kap** mezőkben, megjelenik az **E-mail címzettje** párbeszédpanel. Ezután kiválaszthatja a használandó e-mail-cím típusát. A jelenleg támogatott e-mail-típusok: **Konfigurációs e-mail** és **Nyomtatás kezelése**.

[![E-mail típusának kiválasztása](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Nyomtatás kezelése

Ha bejelöli a **Nyomtatás kezelése** e-mail-típust, fix e-mail-címeket adhat meg a **Címzett** mezőben. 

[![Fix e-mail-címek konfigurálása](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Nem rögzített email-cím használatához válassza ki az e-mail forrástípusát a fájlcélponthoz. A következő értékek használhatók: **Vevő**, **Szállító**, **Potenciális vevő**, **Kapcsolat**, **Versenytárs**, **Dolgozó**, **Kérelmező**, **Potenciális szállító** és **Nem engedélyezett szállító**. Miután kiválasztott egy e-mail-forrástípust, használja az **E-mail származási fiókja** mező melletti gombot a **Képletszerkesztő** képernyő megnyitásához. Ez az űrlap olyan képlet csatolására használható, amely futásidőben visszatéríti a kiválasztott forrástípus **partnerfiókját** a feldolgozott dokumentumból az e-mail célhelyre.

[![E-mail-forrásfiók konfigurálása](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

A receptúrák ER-konfigurációspecifikusak. A **Receptúra** mezőben adja meg a vevői vagy szállítói féltípusra történő dokumentumspecifikus hivatkozást. Gépelés helyett megkeresheti a vevőt vagy szállítót reprezentáló adatforrás-csomópontokat, és az **Adatforrás hozzáadása** lehetőséget kiválasztva frissítheti a receptúrát. Például ha az **ISO 20022 Jóváírás átutalása** konfigurációt használja, a szállító számláját reprezentáló csomópont a következő: `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Ha karakterláncot ad meg, például `"DE-001"`, és ment egy receptúrát, akkor a program elküld egy e-mailt a szállító kapcsolattartójának: **DE-001**.


[![ER-receptúra szerkesztő oldala](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![E-mail-forrásfiók konfigurálása](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Konfigurációs e-mail

Használja ezt az e-mail-típust, ha a használt konfiguráció tartalmaz egy **e-mail-címet** visszatérítő csomópontot az adatforrásokban. A Képletszerkesztő adatforrásainak és függvényeinek használatával helyesen formázott e-mail-címet állíthat elő. Például ha az **ISO 20022 Jóváírás átutalása** konfigurációt használja, a szállító kapcsolattartójának e-mail-címét reprezentáló csomópont a következő: `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![E-mail-cím forrásának konfigurálása](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [Képletszerkesztő elektronikus jelentésekhez (ER)](general-electronic-reporting-formula-designer.md)
