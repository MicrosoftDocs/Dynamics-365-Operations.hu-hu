---
title: Személyes kiadások a költségjelentéseken
description: Ez a témakör bemutatja a két módszert, amely a dolgozók személyes kiadásainak kezelésére szolgál a Microsoft Dynamics 365 Finance rendszerben.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 825b6c131c8a65b99d5b7ebdadcd6389886f2d11
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178091"
---
# <a name="personal-expenses-on-an-expense-report"></a><span data-ttu-id="4d9b4-103">Személyes kiadások a költségjelentéseken</span><span class="sxs-lookup"><span data-stu-id="4d9b4-103">Personal expenses on an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d9b4-104">Üzleti utazások során előfordulhat, hogy a dolgozók a vállalati hitelkártyával egyenlíti ki személyes kiadásait.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-104">During business travel, workers might sometimes charge personal expenses to their corporate credit cards.</span></span> <span data-ttu-id="4d9b4-105">Ha a személyes költségek elszámolására nem határozott meg eljárást, akkor a költségelszámolások jóváhagyási folyamata megszakadhat, amikor az alkalmazott elküldi a tételes költségjelentést.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-105">If you don't define a process for handling personal expenses, the approval process for expense reports might be disrupted when workers submit their itemized expense reports.</span></span> 

<span data-ttu-id="4d9b4-106">Két módszert szolgál a dolgozók személyes kiadásainak kezelésére:</span><span class="sxs-lookup"><span data-stu-id="4d9b4-106">There are two methods for handling a worker's personal expenses:</span></span>

- <span data-ttu-id="4d9b4-107">**Alkalmazott által fizetett** – A szervezet nem fizeti ki személyes költségeit, amelyek a vállalati hitelkártya számláján jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-107">**Paid by employee** – Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card.</span></span> <span data-ttu-id="4d9b4-108">Ehelyett olyan jelentést készít, amely feltüntetni a személyes kiadásokat a vállalati hitelkártyára terhelt vállalati kiadásokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-108">Instead, it creates a report that shows personal expenses together with the corporate expenses that were charged to the corporate credit card.</span></span>
- <span data-ttu-id="4d9b4-109">**Vállalat által fizetett** – A vállalat a vállalati hitelkártya-számla teljes összegét kifizeti, és a személyes kiadások összegével megterheli a dolgozó számláját.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-109">**Paid by company** – Your organization pays the whole bill for the corporate credit card and then debits the worker's account for the personal expenses.</span></span>

<span data-ttu-id="4d9b4-110">Kiválaszthatja a szervezetben használt metódust a **Költségjelentés-kezelési paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="4d9b4-110">You can select the method that your organization uses on the **Expense management parameters** page.</span></span>
