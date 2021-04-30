---
title: Bérlista-integrációs API bemutatása
description: Ez a témakör a Dynamics 365 Human Resources bérszámfejtés integrációs API-ját írja le.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61b90c566325bb8d83b09fceebc721cfb14d3fc8
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891126"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="5fa8d-103">Bérlista-integrációs API bemutatása</span><span class="sxs-lookup"><span data-stu-id="5fa8d-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5fa8d-104">Ez a dokumentum a Dynamics 365 Human Resources bérszámfejtés integrációs API-ját írja le.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="5fa8d-105">Az API leegyszerűsített integrációt tesz lehetővé a Human Resources és a partneri bérlistarendszerek között.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="5fa8d-106">Az integrált tapasztalat a Human Resourcesban az alkalmazotti profillal, a fizetéssel és a levonással, valamint a hozzájárulási adatokkal kezdődik.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="5fa8d-107">Amikor alkalmazottat szerződtet, és beviszi a szükséges profilt és fizetési adatokat a Human Resourcesba, a bérszámfejtő rendszer ezeket az adatokat a bérlista feldolgozásához használja.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="5fa8d-108">A program az alkalmazottra vonatkozó frissítéseket vagy fizetési adatokat későbbi fizetési futtatás során is lekéri használatra.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Bérlista-integrációs folyamat](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="5fa8d-110">Az integráció engedélyezéséhez a Human Resources alkalmazás a következő összetevőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="5fa8d-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="5fa8d-111">Az alkalmazott fizetésre készként való megjelöléséhez használható funkció</span><span class="sxs-lookup"><span data-stu-id="5fa8d-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="5fa8d-112">Integrációs API, amely megnyitja az alkalmazások integrálásának új funkcióját</span><span class="sxs-lookup"><span data-stu-id="5fa8d-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="5fa8d-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="5fa8d-113">Microsoft Dataverse</span></span>

<span data-ttu-id="5fa8d-114">Ez az API Microsoft Dataverse rendszerben (korábbi nevén Common Data Service) működik.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="5fa8d-115">Az API-val való minden RESTful interakció az OData rendszert használó Microsoft Dataverse webes API-n keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="5fa8d-116">Ez az API a Dataverse webes API alkészlete.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="5fa8d-117">A Dataverse webes API definiálja a hitelesítés, a szolgáltatásiszint-szerződések, a köteg, a párhuzamossági vezérlés és a hibakezelés jellemzőit.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="5fa8d-118">További általános információ a Microsoft Dataverse webes API-ról, lásd:</span><span class="sxs-lookup"><span data-stu-id="5fa8d-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="5fa8d-119">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="5fa8d-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="5fa8d-120">A Microsoft Dataverse webes API használata</span><span class="sxs-lookup"><span data-stu-id="5fa8d-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="5fa8d-121">Microsoft Dataverse fejlesztői iránymutatás</span><span class="sxs-lookup"><span data-stu-id="5fa8d-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="5fa8d-122">Ez a dokumentáció részletes adatokat és fejlesztői útmutatást tartalmaz a Dataverse webes API használatával kapcsolatban, beleértve a következő témaköröket:</span><span class="sxs-lookup"><span data-stu-id="5fa8d-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="5fa8d-123">Microsoft Dataverse hitelesítés a webes API-val</span><span class="sxs-lookup"><span data-stu-id="5fa8d-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="5fa8d-124">Műveletek végrehajtása a webes API segítségével</span><span class="sxs-lookup"><span data-stu-id="5fa8d-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="5fa8d-125">Postman használata a webes API-val</span><span class="sxs-lookup"><span data-stu-id="5fa8d-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="5fa8d-126">A változáskövetés használata az adatok külső rendszerekkel történő szinkronizálására</span><span class="sxs-lookup"><span data-stu-id="5fa8d-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="5fa8d-127">A Dataverse for Human Resources számára elérhető virtuális táblák</span><span class="sxs-lookup"><span data-stu-id="5fa8d-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="5fa8d-128">A bérszámfejtés integrációs API végpontjai a Microsoft Dataverse virtuális tábla platformképességeit használják.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="5fa8d-129">Alapértelmezés szerint a virtuális táblák és a hozzájuk kapcsolódó API-végpontok nincsenek telepítve a Human Resources-környezetekben, lehetővé téve a szervezetek számára, hogy ők határozzák meg, hogy mely OData-végpontok lesznek kitéve a környezetnek.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="5fa8d-130">Az API használatához létre kell hozni a Human Resources-entitások virtuális tábláit a környezet számára.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="5fa8d-131">Az API virtuális tábláinak létrehozásáról lásd: [Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="5fa8d-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="5fa8d-132">Adatmodell</span><span class="sxs-lookup"><span data-stu-id="5fa8d-132">Data model</span></span>

<span data-ttu-id="5fa8d-133">A következő ábra az API-n belüli kapcsolatokat illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="5fa8d-134">Különböző típusok idegen kulcsokkal rendelkeznek egyéb, itt nem ábrázolt, a Human Resources rendszerben már létező entitásokhoz kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="5fa8d-135">Ez a dokumentum a bérszámfejtési integrációs helyzetekre jellemző entitásokkal kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="5fa8d-136">A Human Resources rendszer Dataverse webes API-jában azonban számos más entitás is releváns lehet az integráció szempontjából.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="5fa8d-137">Ezen entitások közül néhányra az idegenkulcs-kapcsolatok vagy navigációs tulajdonságok hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5fa8d-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Bérszámfejtés-integráció az API adatmodell használatával](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="5fa8d-139">Bérszámfejtési alkalmazott és kapcsolódó entitások</span><span class="sxs-lookup"><span data-stu-id="5fa8d-139">Payroll employee and related entities</span></span>

<span data-ttu-id="5fa8d-140">Entitások:</span><span class="sxs-lookup"><span data-stu-id="5fa8d-140">Entities:</span></span>

- [<span data-ttu-id="5fa8d-141">Bárlista alkalmazottja</span><span class="sxs-lookup"><span data-stu-id="5fa8d-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="5fa8d-142">Bérlista dolgozói címe</span><span class="sxs-lookup"><span data-stu-id="5fa8d-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="5fa8d-143">Fix kompenzációs konstrukció bérlistája</span><span class="sxs-lookup"><span data-stu-id="5fa8d-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="5fa8d-144">Bérlista szerinti beosztás feladata</span><span class="sxs-lookup"><span data-stu-id="5fa8d-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="5fa8d-145">Bérlista szerinti beosztás</span><span class="sxs-lookup"><span data-stu-id="5fa8d-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="5fa8d-146">Lásd még</span><span class="sxs-lookup"><span data-stu-id="5fa8d-146">See also</span></span>

[<span data-ttu-id="5fa8d-147">Bérlistaentitások létrehozása és áttekintése</span><span class="sxs-lookup"><span data-stu-id="5fa8d-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="5fa8d-148">A Human Resources paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5fa8d-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="5fa8d-149">Megosztott Human Resources paraméterek karbantartása</span><span class="sxs-lookup"><span data-stu-id="5fa8d-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="5fa8d-150">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="5fa8d-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="5fa8d-151">A Microsoft Dataverse webes API használata</span><span class="sxs-lookup"><span data-stu-id="5fa8d-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]