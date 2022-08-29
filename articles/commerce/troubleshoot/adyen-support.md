---
title: Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz
description: Ez a témakör olyan hibaelhárítási Microsoft Dynamics útmutatást tartalmaz, amelyek segítséget nyújtanak az Adyen 365 Payment Connector alkalmazással kapcsolatos problémák esetén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 687f2fdff5e29cc25fae911b015164f0d90aee88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268865"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási Microsoft Dynamics útmutatást tartalmaz, amelyek segítséget nyújtanak az Adyen 365 Payment Connector alkalmazással kapcsolatos problémák esetén.

## <a name="description"></a>Leírás

A következő területeken problémák vannak a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz termékkel, és az Adyen csapat segítségére van szüksége:

- A pénztár (POS), a modern pénztár (MPOS), a hívásközpont vagy a Dynamics 365 Commerce konfigurálása
- Az Adyen fizetési szolgáltató (PSP) hivatkozási száma (például ha kérdései vannak az elutasításokkal kapcsolatban, ideértve a manuális kulcsbevitel \[MKE\]-elutasításokat)
- Bármi, ami nem működik teszt- vagy élő kereskedői környezetben

## <a name="resolution"></a>Felbontás

A következő e-mail-sablon használatával elindíthatja a támogatási folyamatot az Adyen csapatával. A hibaelhárítás felgyorsítása érdekében győződjön meg arról, hogy az e-mail-cím tartalmazza az összes szükséges adatot.

| Mező        | Érték |
|--------------|-------|
| Záró időpont           | `support@adyen.com` |
| Másolatot kap           | |
| Tárgysor | Microsoft Dynamics támogatási kérés |
| Törzs         | <p>Tisztelt ügyféltámogatási szolgálat!</p><p>Támogatásra van szükségem a következő probléma megoldásában:</p><ul><li>Kereskedői számla</li><li>Környezet (teszt/éles)</li><li>Csatorna (POS/hívásközpont/Commerce e-kereskedelem)</li><li>Fizetési szolgáltató hivatkozási száma, ha a probléma egy konkrét tranzakciót érint (a fizetési szolgáltató hivatkozási számát a nyugtán, az Adyen vevőterületen vagy a pénztárterminál tranzakciókat tartalmazó menüjében találja.)</li><li>Képernyőkép vagy fénykép a hibaüzenetről, ha van ilyen</li><li>Eseménynaplók (.txt formátumban)</li><li>A hibe leírása és az Ön által megpróbált és hibaelhárítási lépések bemutatása</li></ul> |

## <a name="additional-resources"></a>További erőforrások

[Kifizetések elfogadása a Dynamics 365 Commerce Adyen összekötőjével](https://www.adyen.com/partners/dynamics-365-commerce)

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../dev-itpro/adyen-connector.md)

[Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz](https://docs.adyen.com/plugins/microsoft-dynamics)
