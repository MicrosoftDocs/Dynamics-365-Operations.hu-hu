---
title: A visszavont termékbevételezések nem frissítik a tranzakció állapotát Regisztrálva állapotra
description: Miután visszavonta a bejövő rakomány termékbevételezéseit, a rendszer automatikusan Beérkezett állapotról Megrendelve állapotra frissíti a készlettranzakció állapotát.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eae703ce0b2c981518b18c4badd4f90031b902ece62f3ca0837427b306d618b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731103"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>A visszavont termékbevételezések nem frissítik a tranzakció állapotát Regisztrálva állapotra

## <a name="symptoms"></a>Tünetek

Miután a beérkező terhelésen futtatta a **Termékbevételek törlése** műveletet, a rendszer automatikusan frissíti a készlettranzakciók állapotát a *Fogadottról* a *Rendeltre*.

## <a name="resolution"></a>Megoldás

Amikor a kimenő rakományok csomagjegyzékét törlik, a készlettranzakciók állapota *Kitárolt* marad. Amikor azonban a bejövő rakományból származó termékbevételezéseket visszavonják, a készlettranzakciók állapota nem áll vissza a *Regisztrálva* állapotra. Ennek megfelelően a bejövő rakományból származó termékbevételezés visszavonása után a raktári dolgozónak újra regisztrálnia kell a cikkmennyiségeket a rakományok számára.

További információ a bejövő rakományba [Bejövő rakománnyal érkező cikkmennyiség regisztrálása](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
