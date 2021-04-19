---
title: Szolgáltatási sablonok
description: A szolgáltatási szerződés sablonként adható meg, és később a sablon sorai más szolgáltatási szerződésekbe vagy szervizrendelésekbe másolhatók.
author: ShylaThompson
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 409c15ae9c8f5f3c9c72adf3313f4594ba3c1764
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819016"
---
# <a name="service-templates"></a><span data-ttu-id="966bb-103">Szolgáltatási sablonok</span><span class="sxs-lookup"><span data-stu-id="966bb-103">Service templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="966bb-104">A szolgáltatási szerződés sablonként adható meg, és később a sablon sorai más szolgáltatási szerződésekbe vagy szervizrendelésekbe másolhatók.</span><span class="sxs-lookup"><span data-stu-id="966bb-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="966bb-105">Példa</span><span class="sxs-lookup"><span data-stu-id="966bb-105">Example</span></span>

<span data-ttu-id="966bb-106">Egy ügyfél, akinek a vállalat szolgáltatást nyújt, öt különböző helyen egyforma lifteket szervizeltet.</span><span class="sxs-lookup"><span data-stu-id="966bb-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="966bb-107">Öt szolgáltatási szerződést akar létrehozni az ügyfél számára, mindegyik telephelyhez egyet.</span><span class="sxs-lookup"><span data-stu-id="966bb-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="966bb-108">A létrehozás ismétlődő feladatainak csökkentése, illetve a különböző szerződések egységes kitöltése érdekében létrehoz egy szolgáltatási szerződést, és azt megadja sablonként a lifteken végzett szervizmunkához.</span><span class="sxs-lookup"><span data-stu-id="966bb-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="966bb-109">Így más bemásolhatja a sablon sorait az öt új szolgáltatási szerződésbe, és mindegyik szolgáltatási szerződést a sablonból tölti fel a program adatokkal.</span><span class="sxs-lookup"><span data-stu-id="966bb-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="966bb-110">Sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="966bb-110">Create a template</span></span>

<span data-ttu-id="966bb-111">Szolgáltatássablon létrehozásához létre kell hoznia egy szolgáltatási szerződést, létre kell benne hoznia a szükséges sorokat, majd a szolgáltatási szerződést egy szolgáltatássablon-csoporthoz kell hozzárendelnie.</span><span class="sxs-lookup"><span data-stu-id="966bb-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="966bb-112">Szolgáltatási szerződést csak akkor lehet sablonként megadni, ha nincsen hozzá csatolva szervizrendelés.</span><span class="sxs-lookup"><span data-stu-id="966bb-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="966bb-113">Ezenkívül sablonként meghatározott szolgáltatási szerződésből nem lehet szervizrendeléseket létrehozni.</span><span class="sxs-lookup"><span data-stu-id="966bb-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="966bb-114">Sablonsorok másolása</span><span class="sxs-lookup"><span data-stu-id="966bb-114">Copy template lines</span></span>

<span data-ttu-id="966bb-115">Szolgáltatássablonból másik szolgáltatási szerződésbe vagy szervizrendelésbe lehet sorokat másolni.</span><span class="sxs-lookup"><span data-stu-id="966bb-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="966bb-116">Amikor sablon sorait szervizrendelésekbe vagy szolgáltatási szerződésekbe másolja a sabloncsoportok fastruktúrában jelennek meg, és mindegyik csoportot ki lehet bontani.</span><span class="sxs-lookup"><span data-stu-id="966bb-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="966bb-117">Ez a nézet lehetővé teszi mindegyik sablon és sablonsor megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="966bb-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="966bb-118">Ha a sablonokat a használatuknak megfelelő név szerinti csoportokba rendezte, könnyebb meghatározni, hogy mely szolgáltatásisablon-sorokat kell másolni.</span><span class="sxs-lookup"><span data-stu-id="966bb-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="966bb-119">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="966bb-119">Related topics</span></span>

[<span data-ttu-id="966bb-120">Szolgáltatási sablonok sorainak másolása</span><span class="sxs-lookup"><span data-stu-id="966bb-120">Copy service templates lines</span></span>](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]