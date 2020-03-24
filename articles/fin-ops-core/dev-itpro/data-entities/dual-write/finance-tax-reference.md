---
title: A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés
description: Ez a témakör a pénzügyi és adóügyi hivatkozási adatokhoz való hozzáféréssel kapcsolatban nyújt tájékoztatást.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 28f47f8cebca6c7249e0596c53f3589dc6541e26
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112449"
---
# <a name="access-to-finance-and-tax-reference-data"></a><span data-ttu-id="d7012-103">A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés</span><span class="sxs-lookup"><span data-stu-id="d7012-103">Access to finance and tax reference data</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="d7012-104">Minden vállalkozás pénzügyi adatok egy alapvető készletével dolgozik, például üzleti év, a pénznem, amiben az vállalkozás a tranzakcióit folytatja, a számlák, amelyen a pénzforgalom zajlik, adókulcsok és utalás.</span><span class="sxs-lookup"><span data-stu-id="d7012-104">Every business works with a basic set of financial data, such as the fiscal calendar year, the currency that business is transacted in, the accounts that the money to run the business comes in to or goes out of, tax rates, and remittance.</span></span> <span data-ttu-id="d7012-105">Ezek az adatok a Finance and Operations alkalmazásokban találhatók.</span><span class="sxs-lookup"><span data-stu-id="d7012-105">This data resides in Finance and Operations apps.</span></span> <span data-ttu-id="d7012-106">Azonban ez elérhető a Common Data Service számára, hogy a modellvezérelt alkalmazások a Microsoft Dynamics 365-ben egyetlen forrásból jussanak pénzügyi és adózási adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="d7012-106">However, it's exposed to Common Data Service so that model-driven apps in Microsoft Dynamics 365 can have a single source for finance and tax data.</span></span> <span data-ttu-id="d7012-107">Ily módon az adatok az üzleti ökoszisztémán belül egységesek.</span><span class="sxs-lookup"><span data-stu-id="d7012-107">In this way, data is uniform across the business ecosystem.</span></span> 

<span data-ttu-id="d7012-108">A pénzügyi és adózási adatok a következő hozzárendelések segítségével integrálhatók:</span><span class="sxs-lookup"><span data-stu-id="d7012-108">Finance and tax data is integrated by using the following mappings:</span></span>

+ [<span data-ttu-id="d7012-109">Integrált főkönyv</span><span class="sxs-lookup"><span data-stu-id="d7012-109">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="d7012-110">Integrált adózási alapadat</span><span class="sxs-lookup"><span data-stu-id="d7012-110">Integrated tax master</span></span>](tax-mapping.md)
