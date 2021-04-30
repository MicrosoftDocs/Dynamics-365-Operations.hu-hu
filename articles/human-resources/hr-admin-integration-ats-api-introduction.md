---
title: Pályázó követésrendszer integrációs API bevezetése
description: Ez a témakör a Dynamics 365 Human Resources Pályázó követésrendszer (ATS) integrációs API-t írja le.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f70e377d6844b5c4f9201f0a561ad9cfcab2eda1
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890125"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="f9894-103">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="f9894-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f9894-104">Ez a témakör a Dynamics 365 Human Resources Pályázó követésrendszer (ATS) integrációs API-t írja le.</span><span class="sxs-lookup"><span data-stu-id="f9894-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="f9894-105">Az API célja a Dynamics 365 Human Resources és az ATS-ek közötti leegyszerűsített integráció engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="f9894-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![ATS integrációs folyamat](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="f9894-107">Az integrált tapasztalat akkor kezdődik a Human Resources rendszerben, amikor egy felvételi vezető toborzási kérelmet hoz létre.</span><span class="sxs-lookup"><span data-stu-id="f9894-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="f9894-108">A kérelem aktiválásakor az ATS lekéri a toborzási projekt létrehozására vonatkozó kérelem részleteit.</span><span class="sxs-lookup"><span data-stu-id="f9894-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="f9894-109">Ezután követi a toborzási folyamatot a jelölt pozíció(k)ra történő kiválasztásához és felvételéhez.</span><span class="sxs-lookup"><span data-stu-id="f9894-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="f9894-110">Végül az ATS úgy fejezi be az oda-vissza integrációt, hogy elküldi a kiválasztott jelölt rekordját a Human Resources rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="f9894-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="f9894-111">A jelölt rekordja ezután több, felvételre vonatkozó ellenőrzésen és munkafolyamaton mehet át az alkalmazotti rekord létrehozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="f9894-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="f9894-112">Az integráció engedélyezéséhez a Human Resources alkalmazás a következő összetevőket adta hozzá:</span><span class="sxs-lookup"><span data-stu-id="f9894-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="f9894-113">A toborzási kérelem létrehozására használható funkciók.</span><span class="sxs-lookup"><span data-stu-id="f9894-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="f9894-114">Kibővített jelölti profil és a kapcsolódó munkafolyamatok.</span><span class="sxs-lookup"><span data-stu-id="f9894-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="f9894-115">Integrációs API, amely az új funkciókat megnyitja az alkalmazások integrálása előtt.</span><span class="sxs-lookup"><span data-stu-id="f9894-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="f9894-116">A toborzási kérelem és a jelölti funkció beállításával és használatával kapcsolatos további tudnivalókat lásd: [Jelöltek toborzása](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="f9894-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="f9894-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="f9894-117">Microsoft Dataverse</span></span>

<span data-ttu-id="f9894-118">Ez az API Microsoft Dataverse rendszerben (korábbi nevén Common Data Service) működik.</span><span class="sxs-lookup"><span data-stu-id="f9894-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="f9894-119">Az API-val való minden RESTful interakció az OData rendszert használó Microsoft Dataverse webes API-n keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="f9894-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="f9894-120">Ez az API a Dataverse webes API alkészlete.</span><span class="sxs-lookup"><span data-stu-id="f9894-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="f9894-121">A Dataverse webes API definiálja a hitelesítés, a szolgáltatásiszint-szerződések, a köteg, a párhuzamossági vezérlés és a hibakezelés jellemzőit.</span><span class="sxs-lookup"><span data-stu-id="f9894-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="f9894-122">További általános információ a Microsoft Dataverse webes API-ról, lásd:</span><span class="sxs-lookup"><span data-stu-id="f9894-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="f9894-123">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="f9894-123">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="f9894-124">A Microsoft Dataverse webes API használata</span><span class="sxs-lookup"><span data-stu-id="f9894-124">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="f9894-125">Microsoft Dataverse fejlesztői iránymutatás</span><span class="sxs-lookup"><span data-stu-id="f9894-125">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="f9894-126">A fenti dokumentáció részletes és fejlesztői útmutatásokat tartalmaz a Dataverse webes API használatával kapcsolatban, ilyen például a [hitelesítés kezelése](/powerapps/developer/data-platform/webapi/authenticate-web-api), a [műveletek végrehajtása](/powerapps/developer/data-platform/webapi/perform-operations-web-api), a [Postman és az API használata](/powerapps/developer/data-platform/webapi/use-postman-web-api), valamint [változáskövetési vagy eltérési tokenek használata](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) az API-val.</span><span class="sxs-lookup"><span data-stu-id="f9894-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="f9894-127">Beállításkészletek</span><span class="sxs-lookup"><span data-stu-id="f9894-127">Option sets</span></span>

<span data-ttu-id="f9894-128">Az ATS integrációs API-jának ebben a dokumentumban ismertetett adatmodellje olyan beállításkészleteket tartalmaz, amelyek entitástulajdonságokhoz rendelt, felsorolt értékeket tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="f9894-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="f9894-129">A Dataverse webes API-t használó beállításkészletekkel való munka részletes részleteit lásd: [Beállításkészletek létrehozása és frissítése a webes API segítségével](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="f9894-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="f9894-130">A beállításkészleteket az egyes Dataverse-környezetekhez határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="f9894-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="f9894-131">A Dataverse for Human Resources számára elérhető virtuális táblák</span><span class="sxs-lookup"><span data-stu-id="f9894-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="f9894-132">Az ATS integrációs API végpontjai a Microsoft Dataverse virtuális tábla platformképességeit használják.</span><span class="sxs-lookup"><span data-stu-id="f9894-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="f9894-133">Alapértelmezés szerint a virtuális táblák és a hozzájuk kapcsolódó API-végpontok nincsenek telepítve a Human Resources-környezetekben, lehetővé téve a szervezetek számára, hogy ők határozzák meg, hogy mely OData-végpontok lesznek kitéve a környezetnek.</span><span class="sxs-lookup"><span data-stu-id="f9894-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="f9894-134">Az API használatához létre kell hozni a Human Resources-entitások virtuális tábláit a környezet számára.</span><span class="sxs-lookup"><span data-stu-id="f9894-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="f9894-135">Az API virtuális tábláinak létrehozásáról lásd: [Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="f9894-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="f9894-136">Adatmodell</span><span class="sxs-lookup"><span data-stu-id="f9894-136">Data model</span></span>

<span data-ttu-id="f9894-137">Az adatmodell két fő entitás köré csoportosul:</span><span class="sxs-lookup"><span data-stu-id="f9894-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="f9894-138">A **RecruitingRequest** egy vagy több nyitott beosztásra vonatkozó toborzási kérés egy ATS-nek. Példalekérdezéshez lásd: [Példa lekérdezésre toborzási kérelemhez](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="f9894-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="f9894-139">**A CandidateToHire** a pozícióra vonatkozó ajánlatot elfogadó jelölt részletes adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f9894-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="f9894-140">A **Személy** a jelöltre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f9894-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="f9894-141">Egy személynek a vállalatnál több szerepköre is lehet, például jelölt, dolgozó, alkalmazott vagy alvállalkozó.</span><span class="sxs-lookup"><span data-stu-id="f9894-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="f9894-142">Példalekérdezés: [Példa lekérdezésre Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="f9894-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="f9894-143">A következő ábra az API-n belüli kapcsolatokat illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="f9894-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="f9894-144">Különböző típusok idegen kulcsokkal rendelkeznek egyéb, itt nem ábrázolt, a Human Resources rendszerben már létező entitásokhoz kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="f9894-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="f9894-145">Ez a dokumentum a toborzási integrációs helyzetekre jellemző entitásokkal kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="f9894-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="f9894-146">A Dynamics 365 Human Resources rendszer Dataverse webes API-jában azonban számos más entitás is releváns lehet az integráció szempontjából.</span><span class="sxs-lookup"><span data-stu-id="f9894-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="f9894-147">Például az itt nem meghatározott dolgozókra, munkakörökre, pozíciókra vagy más entitásokra vonatkozóan is szüksége lehet részletes adatokra.</span><span class="sxs-lookup"><span data-stu-id="f9894-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="f9894-148">Ezen entitások közül többre az idegenkulcs-kapcsolatok vagy navigációs tulajdonságok hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="f9894-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![ATS-integráció az API adatmodell használatával](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="f9894-150">Toborzási kérelem és a kapcsolódó entitások és beállításkészletek</span><span class="sxs-lookup"><span data-stu-id="f9894-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="f9894-151">Példa lekérdezésre:</span><span class="sxs-lookup"><span data-stu-id="f9894-151">Example query:</span></span> 

- [<span data-ttu-id="f9894-152">Példa lekérdezésre Toborzási kérelemmel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="f9894-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="f9894-153">Entitások:</span><span class="sxs-lookup"><span data-stu-id="f9894-153">Entities:</span></span>

- [<span data-ttu-id="f9894-154">Toborzási kérelem</span><span class="sxs-lookup"><span data-stu-id="f9894-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="f9894-155">Toborzási kérelem beosztása</span><span class="sxs-lookup"><span data-stu-id="f9894-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="f9894-156">Toborzási kérelem – szakértelem</span><span class="sxs-lookup"><span data-stu-id="f9894-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="f9894-157">Toborzási kérelem – végzettség</span><span class="sxs-lookup"><span data-stu-id="f9894-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="f9894-158">Toborzási kérelem helye</span><span class="sxs-lookup"><span data-stu-id="f9894-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="f9894-159">Beállításkészletek:</span><span class="sxs-lookup"><span data-stu-id="f9894-159">Option sets:</span></span>

- [<span data-ttu-id="f9894-160">Munka mentességi állapota</span><span class="sxs-lookup"><span data-stu-id="f9894-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="f9894-161">Toborzási kérelem – pozíció állapota</span><span class="sxs-lookup"><span data-stu-id="f9894-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="f9894-162">Toborzási kérelem állapota</span><span class="sxs-lookup"><span data-stu-id="f9894-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="f9894-163">Jogszabállyal kapcsolatos álláskategória</span><span class="sxs-lookup"><span data-stu-id="f9894-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="f9894-164">Felvenni kívánt jelölt és a kapcsolódó entitások és beállításkészletek</span><span class="sxs-lookup"><span data-stu-id="f9894-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="f9894-165">Példa lekérdezésre:</span><span class="sxs-lookup"><span data-stu-id="f9894-165">Example query:</span></span>

- [<span data-ttu-id="f9894-166">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="f9894-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="f9894-167">Entitások:</span><span class="sxs-lookup"><span data-stu-id="f9894-167">Entities:</span></span>

- [<span data-ttu-id="f9894-168">Felveendő jelentkező</span><span class="sxs-lookup"><span data-stu-id="f9894-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="f9894-169">Személy</span><span class="sxs-lookup"><span data-stu-id="f9894-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="f9894-170">Személy végzettsége</span><span class="sxs-lookup"><span data-stu-id="f9894-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="f9894-171">Személy szakmai tapasztalata</span><span class="sxs-lookup"><span data-stu-id="f9894-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="f9894-172">Személy címe</span><span class="sxs-lookup"><span data-stu-id="f9894-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="f9894-173">Fél kapcsolattartója</span><span class="sxs-lookup"><span data-stu-id="f9894-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="f9894-174">Személy szakértelme</span><span class="sxs-lookup"><span data-stu-id="f9894-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="f9894-175">Minősítési szint</span><span class="sxs-lookup"><span data-stu-id="f9894-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="f9894-176">Személy tanúsítványa</span><span class="sxs-lookup"><span data-stu-id="f9894-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="f9894-177">Tanúsítvány típusa</span><span class="sxs-lookup"><span data-stu-id="f9894-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="f9894-178">Személy szűrési adatai</span><span class="sxs-lookup"><span data-stu-id="f9894-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="f9894-179">Szűréstípusok</span><span class="sxs-lookup"><span data-stu-id="f9894-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="f9894-180">Személy személyazonosító száma</span><span class="sxs-lookup"><span data-stu-id="f9894-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="f9894-181">Beállításkészletek:</span><span class="sxs-lookup"><span data-stu-id="f9894-181">Option sets:</span></span>

- [<span data-ttu-id="f9894-182">Pályázó integrációs eredménye</span><span class="sxs-lookup"><span data-stu-id="f9894-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="f9894-183">Üres Igen Nem</span><span class="sxs-lookup"><span data-stu-id="f9894-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="f9894-184">Végrehajtás állapota</span><span class="sxs-lookup"><span data-stu-id="f9894-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="f9894-185">Kapcsolattartó típusa</span><span class="sxs-lookup"><span data-stu-id="f9894-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="f9894-186">Végzettség – tanulmányi pontszám alapja</span><span class="sxs-lookup"><span data-stu-id="f9894-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="f9894-187">Nem</span><span class="sxs-lookup"><span data-stu-id="f9894-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="f9894-188">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="f9894-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="f9894-189">Év hónapjai</span><span class="sxs-lookup"><span data-stu-id="f9894-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="f9894-190">Nem Igen</span><span class="sxs-lookup"><span data-stu-id="f9894-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="f9894-191">Időszakegység</span><span class="sxs-lookup"><span data-stu-id="f9894-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="f9894-192">Szűrési gyakoriság</span><span class="sxs-lookup"><span data-stu-id="f9894-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="f9894-193">Szűrési gyakoriság generálása innen:</span><span class="sxs-lookup"><span data-stu-id="f9894-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="f9894-194">Szakértelmi szint típusa</span><span class="sxs-lookup"><span data-stu-id="f9894-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="f9894-195">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f9894-195">See also</span></span>

[<span data-ttu-id="f9894-196">Jelöltek toborzása</span><span class="sxs-lookup"><span data-stu-id="f9894-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="f9894-197">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="f9894-197">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="f9894-198">A Microsoft Dataverse webes API használata</span><span class="sxs-lookup"><span data-stu-id="f9894-198">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="f9894-199">Beállításkészletek létrehozása és frissítése a webes API segítségével</span><span class="sxs-lookup"><span data-stu-id="f9894-199">Create and update option sets using the Web API</span></span>](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]