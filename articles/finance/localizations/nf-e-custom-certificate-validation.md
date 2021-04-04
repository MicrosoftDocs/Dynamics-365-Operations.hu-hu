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
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3efa05f49748f6bbff680f322a77cec24da46c0c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240579"
---
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="62469-103">NF-e egyéni tanúsítvány érvényesítése</span><span class="sxs-lookup"><span data-stu-id="62469-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62469-104">Az NF-e egyéni tanúsítvány érvényesítési funkciójának bekapcsolásakor az egyéni érvényesítés lehetővé teszi a webszolgáltatásokkal való kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="62469-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="62469-105">Erre a kapcsolatra azért van szükség, hogy továbbítsa az NF-e-t, és fogadni tudja a SEFAZ-tól kapott engedélyt.</span><span class="sxs-lookup"><span data-stu-id="62469-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="62469-106">A V5-tanúsítványból származó **Kiszolgálóihitelesítési cél** tulajdonságot a brazil legfelsőbb szintű hitelesítésszolgáltató adja ki.</span><span class="sxs-lookup"><span data-stu-id="62469-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="62469-107">Ez a tulajdonság alapértelmezés szerint ki van kapcsolva, és manuálisan kell engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="62469-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="62469-108">Bizonyos körülmények között az automatikus tanúsítványfrissítés ezt a tulajdonságot letilthatja.</span><span class="sxs-lookup"><span data-stu-id="62469-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="62469-109">Ha ez történik, akkor az hatással lehet a TLS-kapcsolatra, amely így a továbbiakban már nem megbízható.</span><span class="sxs-lookup"><span data-stu-id="62469-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="62469-110">Ezen felül a Minas Gerais (MG) és Paraná (PR) államok számára gyártási környezetre vonatkozó NF-e kiadása is nehézségekbe ütközhet.</span><span class="sxs-lookup"><span data-stu-id="62469-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="62469-111">Ez a frissítés alternatív megoldást kínál a tanúsítványok hitelesítésére, ami azt jelenti, hogy biztonságos kommunikációt létesíthető.</span><span class="sxs-lookup"><span data-stu-id="62469-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]