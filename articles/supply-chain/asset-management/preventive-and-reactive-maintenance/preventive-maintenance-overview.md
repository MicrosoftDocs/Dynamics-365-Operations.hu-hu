---
title: Megelőző karbantartás – áttekintés
description: Ez a cikk a megelőző karbantartás Eszközkezelésben való használatát ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 36a70a3e60566fd8048ad404e0c391d898053a0a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016728"
---
# <a name="preventive-maintenance-overview"></a><span data-ttu-id="3ce1f-103">Megelőző karbantartás – áttekintés</span><span class="sxs-lookup"><span data-stu-id="3ce1f-103">Preventive maintenance overview</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3ce1f-104">Ez a cikk a megelőző karbantartás Eszközkezelésben való használatát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-104">This topic explains preventive maintenance in Asset Management.</span></span> <span data-ttu-id="3ce1f-105">A megelőző karbantartás olyan kategória, amelyben a tervezett karbantartási feladatokat (például a rendszeres szolgáltatást, kalibrálást és vizsgálatokat) tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-105">Preventive maintenance is a discipline involving planned maintenance jobs, for example, regular service, calibration, and inspections.</span></span> <span data-ttu-id="3ce1f-106">Az **Eszközkezelésben** karbantartási terveket hozhat létre, amelyeket beállíthat eszközökhöz és a munkavégzési helyszínekhez.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-106">In **Asset Management**, you can create maintenance plans and set them up on assets and functional locations.</span></span> <span data-ttu-id="3ce1f-107">A munkavégzési helyszínekhez karbantartási körök is beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-107">You can also set up maintenance rounds on functional locations.</span></span> <span data-ttu-id="3ce1f-108">Az eszközök karbantartási tervei az eszköz telepítési helyétől függetlenül aktívak.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-108">Maintenance plans on assets are active regardless of where the asset is installed.</span></span> <span data-ttu-id="3ce1f-109">A munkavégzési helyszínek karbantartási tervei és karbantartási körei a helyen aktuálisan telepített eszközöknél aktívak.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-109">Maintenance plans and maintenance rounds on functional location are active for the assets currently installed at the location.</span></span> <span data-ttu-id="3ce1f-110">Az eszközök karbantartási terveinek beállítása vagy a karbantartási körök munkavégzési helyszíneken való beállítása helyett létrehozhat karbantartási köröket, amelyekben több olyan eszköz is szerepel, amelyhez az adott feladatcsoporthoz tartozó karbantartási feladatok kapcsolódó típusait kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-110">Instead of setting up maintenance plans on assets, or setting up maintenance rounds on functional locations, you can create maintenance rounds that include multiple assets on which you need to perform related types of maintenance jobs in the same work routine.</span></span> <span data-ttu-id="3ce1f-111">Az eszközökből (és nem a munkavégzési helyszíneken) létrehozott karbantartási körök esetén egy karbantartási körhöz több olyan eszköz is kiválasztható, amely nem ugyanazon a munkavégzési helyszínen lett telepítve.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-111">Maintenance rounds created from assets - instead of created on functional locations - means that you can select a number of assets for one maintenance round, which are not installed on the same functional location.</span></span>

<span data-ttu-id="3ce1f-112">A karbantartási tervek az egyéni eszközök preventív és reaktív karbantartására használatosak.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-112">Maintenance plans are used for preventive and reactive maintenance on individual assets.</span></span> <span data-ttu-id="3ce1f-113">A karbantartási körök egy csoport vagy egy eszközkészlet preventív karbantartására használatosak.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-113">Maintenance rounds are used for preventive maintenance on a group or a set of assets.</span></span> <span data-ttu-id="3ce1f-114">A karbantartási tervek és a karbantartási körök munkarendelés-javaslatok létrehozására használhatók.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-114">Maintenance plans and maintenance rounds are used for generating work order proposals.</span></span> <span data-ttu-id="3ce1f-115">A munkarendelés-javaslatokat a rendszer a karbantartási ütemezés olyan soraiként menti, amelyek kötegbe rendezhetők és munkarendelésekké alakíthatók.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-115">The work order proposals are saved as maintenance schedule lines, which can be bundled and converted into work orders.</span></span>

<span data-ttu-id="3ce1f-116">Az alábbi ábra egy olyan, a karbantartási tervek és a karbantartási körök létrehozásától a munkarendelések eszközökhöz való végrehajtásáig terjedő munkafolyamatot mutat, amely ezeken a karbantartási terveken és karbantartási körökön alapul.</span><span class="sxs-lookup"><span data-stu-id="3ce1f-116">The following illustration provides an overview of the work flow from creating maintenance plans and maintenance rounds to creating work orders for assets, based on those maintenance plans and maintenance rounds.</span></span>

![1. ábra](media/01-preventive-maintenance.png)

