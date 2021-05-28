---
title: Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak a Microsoft Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazással kapcsolatos problémák esetén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 707efeba9553b996e4e33a4754e42a9d22643e33
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019589"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Hibaelhárítás – Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak a Microsoft Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazással kapcsolatos problémák esetén.

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
