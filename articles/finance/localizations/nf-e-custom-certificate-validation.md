---
title: NF-e egyéni tanúsítvány érvényesítése
description: Ez a témakör az NF-e egyéni tanúsítvány érvényesítéséről és használatáról ad tájékoztatást.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443912"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e egyéni tanúsítvány érvényesítése

[!include [banner](../includes/banner.md)]

Az NF-e egyéni tanúsítvány érvényesítési funkciójának bekapcsolásakor az egyéni érvényesítés lehetővé teszi a webszolgáltatásokkal való kapcsolatot. Erre a kapcsolatra azért van szükség, hogy továbbítsa az NF-e-t, és fogadni tudja a SEFAZ-tól kapott engedélyt.

A V5-tanúsítványból származó **Kiszolgálóihitelesítési cél** tulajdonságot a brazil legfelsőbb szintű hitelesítésszolgáltató adja ki. Ez a tulajdonság alapértelmezés szerint ki van kapcsolva, és manuálisan kell engedélyezni. Bizonyos körülmények között az automatikus tanúsítványfrissítés ezt a tulajdonságot letilthatja. Ha ez történik, akkor az hatással lehet a TLS-kapcsolatra, amely így a továbbiakban már nem megbízható. Ezen felül a Minas Gerais (MG) és Paraná (PR) államok számára gyártási környezetre vonatkozó NF-e kiadása is nehézségekbe ütközhet.

Ez a frissítés alternatív megoldást kínál a tanúsítványok hitelesítésére, ami azt jelenti, hogy biztonságos kommunikációt létesíthető.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]