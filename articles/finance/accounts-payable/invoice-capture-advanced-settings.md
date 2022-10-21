---
title: Számlarögzítési megoldás speciális beállításai
description: Ez a cikk a Számlarögzítés megoldás speciális beállításaival kapcsolatban tartalmaz tájékoztatást.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690989"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Számlarögzítési megoldás speciális beállításai

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk a Számlarögzítés megoldás speciális beállításaival kapcsolatban tartalmaz tájékoztatást.

## <a name="create-additional-connections-for-channels"></a>További kapcsolatok létrehozása csatornákhoz

Ahhoz, hogy a különböző csatornák bejövő számláit figyelni tudja, kapcsolatot kell létesítenie az e-mail vagy fájltárolóval. A kapcsolatot kezdetben regisztrálnia kell, hogy hozzáférést adjon a megoldásban használt automatizált folyamatokhoz.

A számlák importálása a következő kapcsolattípusokkal használatos:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

A számlaimportozás csatornája a kapcsolatokat fogja használni a további konfigurációs lépésekben. Ahhoz, hogy a felhasználók csatornát hoznak létre egy adott kapcsolathoz, **biztosítani** kell számukra a Rendszergazda biztonsági szerepkört, és létre kell hozniuk a kapcsolatokat.

A következő lépések szerint hozzon létre Microsoft Dataverse kapcsolatot.

1. Ugrás az **Admin system \> Default megoldásra**.
2. Válassza az **Új**, majd a Kapcsolathivatkozás **lehetőséget**.
3. A Megjelenítendő **név** mezőbe írjon be egy nevet.
4. Válassza ki **Microsoft Dataverse** a csatlakoztatóként.
5. Ha első alkalommal adja meg a kapcsolatot, válassza az Új kapcsolat **lehetőséget**.
6. A megjelenő párbeszédpanelen hozzon létre egy kapcsolatot, majd válassza a Dataverse Létrehozás **lehetőséget**.
7. Adja meg Dataverse a fiókot és a jelszót.
8. Az ellenőrzés érvényesítése után menjen a kapcsolati lapra, válassza a Frissítés **lehetőséget**, jelölje ki a fiókot, majd válassza **a Létrehozás lehetőséget**.

E-mail vagy fájl tárolási kapcsolatának létrehozásához kövesse az alábbi lépéseket.

1. Válassza az **Outlook** lehetőséget **a Kapcsolat létrehozása lapon a Kapcsolat típusa** mezőben **Office 365**.
2. E-mail kapcsolat esetén csatlakoztatóként **a** Outlook.com outlook **Office 365 lehetőséget** választhatja. Fájltárolási kapcsolat esetén az egyiket vagy a lehetőséget választhatja **OneDrive** **SharePoint**.

A meglévő kapcsolatok áttekintéséhez használja az **Alapértelmezett megoldás \> – Objektumok \> kapcsolathivatkozásai hivatkozást**. A csatornákat létrehozása felhasználónak Dataverse az e-mailben vagy fájltárolási kapcsolaton kívül legalább egy kapcsolatnak kell létesítenie. Az új csatorna létrehozójának kell lennie a kapcsolat tulajdonosának.
