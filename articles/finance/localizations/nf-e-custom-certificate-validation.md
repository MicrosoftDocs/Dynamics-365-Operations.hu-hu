---
title: NF-e egyéni tanúsítvány érvényesítése
description: Ez a cikk a EGYEN és az e-mail alapú egyéni tanúsítvány engedélyezésével és használatával kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 3d69aa9d6d0ce33fbed9ba1c7a7af441e14d0d07
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875904"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e egyéni tanúsítvány érvényesítése

[!include [banner](../includes/banner.md)]

A brazil legfelsőbb szintű hitelesítésszolgáltató által kiállított tanúsítványok **Kiszolgálóhitelesítési cél** tulajdonsága alapértelmezés szerint ki van kapcsolva, és manuálisan kell engedélyezni. Bizonyos körülmények között az automatikus tanúsítványfrissítés ezt a tulajdonságot letilthatja. Ha ez megtörténik, az a TLS-kapcsolatot is befolyásolja, és többé nem lesz megbízható. Ez érinti Minas Gerais (MG) és Paraná (PR) államban a brazil elektronikus pénzügyi dokumentum 55-ös modelljének (NF-e) kibocsátását a termelési környezetekben.

Az **NF-e egyéni tanúsítványérvényesítés** javításának engedélyezéséhez lépjen a **Funkciókezelés** lehetőségre. Ez a funkció alternatív megoldást kínál a V5 és V10 tanúsítványok érvényesítésére, és lehetővé teszi a megbízható kapcsolatot a webszolgáltatásokkal, ami az NF-e biztonságos továbbításához és a SEFAZ engedélyezésének fogadásához szükséges.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
