---
title: NF-e egyéni tanúsítvány érvényesítése
description: Ez a témakör az NF-e egyéni tanúsítvány érvényesítéséről és használatáról ad tájékoztatást.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755591"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e egyéni tanúsítvány érvényesítése

[!include [banner](../includes/banner.md)]

A brazil legfelsőbb szintű hitelesítésszolgáltató által kiállított tanúsítványok **Kiszolgálóhitelesítési cél** tulajdonsága alapértelmezés szerint ki van kapcsolva, és manuálisan kell engedélyezni. Bizonyos körülmények között az automatikus tanúsítványfrissítés ezt a tulajdonságot letilthatja. Ha ez megtörténik, az a TLS-kapcsolatot is befolyásolja, és többé nem lesz megbízható. Ez érinti Minas Gerais (MG) és Paraná (PR) államban a brazil elektronikus pénzügyi dokumentum 55-ös modelljének (NF-e) kibocsátását a termelési környezetekben.

Az **NF-e egyéni tanúsítványérvényesítés** javításának engedélyezéséhez lépjen a **Funkciókezelés** lehetőségre. Ez a funkció alternatív megoldást kínál a V5 és V10 tanúsítványok érvényesítésére, és lehetővé teszi a megbízható kapcsolatot a webszolgáltatásokkal, ami az NF-e biztonságos továbbításához és a SEFAZ engedélyezésének fogadásához szükséges.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
