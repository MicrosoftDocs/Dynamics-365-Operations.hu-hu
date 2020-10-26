---
title: Szolgáltatási tárgyak áttekintése
description: A szolgáltatási tárgyak a vevő azon eszközei és termékei, amelyhez szolgáltatást lehet elvégezni.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29d2cf6a496fed8d9932d5c6d49f4560d7eabbbb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979112"
---
# <a name="service-objects-overview"></a><span data-ttu-id="34653-103">Szolgáltatási tárgyak áttekintése</span><span class="sxs-lookup"><span data-stu-id="34653-103">Service objects overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34653-104">A szolgáltatási tárgyak a vevő azon eszközei és termékei, amelyhez szolgáltatást lehet elvégezni.</span><span class="sxs-lookup"><span data-stu-id="34653-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="34653-105">A nyújtott szolgáltatás típusától függően az objektumok lehetnek tárgyi vagy nem tárgyi jellegűek:</span><span class="sxs-lookup"><span data-stu-id="34653-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="34653-106">A tárgyi jellegű objektumokon – például gépeken vagy épületen – fizikai jellegű szolgáltatási feladatot lehet végezni.</span><span class="sxs-lookup"><span data-stu-id="34653-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="34653-107">A materiális szolgáltatási objektum készletcikk is lehet, amelyet a Megjelent termék részletei képernyőn hoz létre.</span><span class="sxs-lookup"><span data-stu-id="34653-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="34653-108">A a cikkhez csatolt készletdimenzió-csoporttól függően létrehozhat egy olyan részletes szolgáltatási objektumot, amely tartalmazza a cikk sorozatszámát.</span><span class="sxs-lookup"><span data-stu-id="34653-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="34653-109">Ez akkor hasznos, ha nyomon kell követnie azt az adott cikket, amelyet a szolgáltatási tárgy jelöl meg.</span><span class="sxs-lookup"><span data-stu-id="34653-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="34653-110">Materiális szolgáltatási objektum lehet olyan cikk is, ami nem kapcsolódik közvetlenül a vállalat közvetlen termelési vagy ellátási láncához.</span><span class="sxs-lookup"><span data-stu-id="34653-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="34653-111">Lehet például a szervizrendelésen szereplő javításokhoz használt eszközcsomag lehet egy szolgáltatási tárgy, amely nem szerepel a készletben.</span><span class="sxs-lookup"><span data-stu-id="34653-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="34653-112">Ebben az esetben nem készletcikként regisztrálja azt.</span><span class="sxs-lookup"><span data-stu-id="34653-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="34653-113">A nem tárgyi jellegű objektumok nem fizikai jellegű elemek, például számlák vagy jogi dokumentumok, amelyeken szervizfeladatokat lehet végezni.</span><span class="sxs-lookup"><span data-stu-id="34653-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="34653-114">Immateriális szolgáltatási objektumok például</span><span class="sxs-lookup"><span data-stu-id="34653-114">Example of an intangible service object</span></span>

<span data-ttu-id="34653-115">Az A vállalat pénzügyi nyilvántartást kezel több kisebb vállalat számára.</span><span class="sxs-lookup"><span data-stu-id="34653-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="34653-116">Az A vállalat egyik ügyfele a helyi futballcsapat, amely számára A vállalat heti könyvelést végez, valamint évente auditálja a klub könyvelését.</span><span class="sxs-lookup"><span data-stu-id="34653-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="34653-117">A klub könyvelése A szolgáltatás tárgyai képernyőn van beállítva, és a szolgáltatási szerződésben ez van megadva objektumként.</span><span class="sxs-lookup"><span data-stu-id="34653-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="34653-118">Az objektumhoz két szolgáltatásiszerződés-sor tartozik.</span><span class="sxs-lookup"><span data-stu-id="34653-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="34653-119">Az 1. sor a heti könyvelés a sorokhoz rendelt heti időközökkel, a 2. sor pedig az éves audit, amihez egy éves időtartam van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="34653-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34653-120">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="34653-120">Related topics</span></span>

[<span data-ttu-id="34653-121">Szolgáltatási objektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="34653-121">Create service objects</span></span>](create-service-objects.md)

