---
title: Munkakör adatai API
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Munkakör adatai entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4f15282bf72340cb1a832ff3264361472d0a6c70
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881997"
---
# <a name="job-detail-api"></a><span data-ttu-id="b8244-103">Munkakör adatai API</span><span class="sxs-lookup"><span data-stu-id="b8244-103">Job detail API</span></span>

<span data-ttu-id="b8244-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Munkakör adatai entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b8244-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="b8244-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="b8244-105">Properties</span></span>

| <span data-ttu-id="b8244-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="b8244-106">Property</span></span><br><span data-ttu-id="b8244-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="b8244-107">**Physical name**</span></span><br><span data-ttu-id="b8244-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="b8244-108">**_Type_**</span></span> | <span data-ttu-id="b8244-109">Használat</span><span class="sxs-lookup"><span data-stu-id="b8244-109">Use</span></span> | <span data-ttu-id="b8244-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="b8244-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b8244-111">**Beosztásazonosító**</span><span class="sxs-lookup"><span data-stu-id="b8244-111">**Job ID**</span></span><br><span data-ttu-id="b8244-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="b8244-112">mshr_jobid</span></span><br><span data-ttu-id="b8244-113">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="b8244-113">*String*</span></span> | <span data-ttu-id="b8244-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="b8244-114">Read-only</span></span><br><span data-ttu-id="b8244-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="b8244-115">Required</span></span> | <span data-ttu-id="b8244-116">Egy feladat egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="b8244-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="b8244-117">**A piaci ár alsó küszöbértéke**</span><span class="sxs-lookup"><span data-stu-id="b8244-117">**Market price low threshold**</span></span><br><span data-ttu-id="b8244-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="b8244-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="b8244-119">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="b8244-119">*Decimal*</span></span> | | <span data-ttu-id="b8244-120">A pozíció egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="b8244-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
