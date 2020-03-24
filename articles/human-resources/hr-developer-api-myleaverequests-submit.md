---
title: Szabadságkérelem elküldése munkafolyamathoz
description: A Microsoft Dynamics 365 Human Resources alkalmazásban a MyLeaveRequests submit () alkalmazásprogramozási felületet (API) használhatja a szabadságkérelmek elküldésére a munkafolyamatba.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7552a4c921dc4a88034b5d2c87d5a9b47d699ae3
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092014"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="34244-103">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="34244-103">Submit a leave request to workflow</span></span>

<span data-ttu-id="34244-104">A Microsoft Dynamics 365 Human Resources alkalmazásban a MyLeaveRequests submit () alkalmazásprogramozási felületet (API) használhatja a szabadságkérelmek elküldésére a munkafolyamatba.</span><span class="sxs-lookup"><span data-stu-id="34244-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="34244-105">Ez az API műveletként használható a MyLeaveRequests OData entitáson.</span><span class="sxs-lookup"><span data-stu-id="34244-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34244-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="34244-106">Prerequisites</span></span>

<span data-ttu-id="34244-107">A szabadságkérelmet menteni kell az adatbázisba, és a beolvashatónak kell lennie a MyLeaveRequests entitáson keresztül.</span><span class="sxs-lookup"><span data-stu-id="34244-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="34244-108">Engedélyek</span><span class="sxs-lookup"><span data-stu-id="34244-108">Permissions</span></span>

<span data-ttu-id="34244-109">Az API hívásához a következő engedélyek egyike szükséges.</span><span class="sxs-lookup"><span data-stu-id="34244-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34244-110">Az engedélyekkel és a kiválasztásukkal kapcsolatos további tudnivalókat lásd: [Hitelesítés](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="34244-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="34244-111">Engedély típusa</span><span class="sxs-lookup"><span data-stu-id="34244-111">Permission type</span></span>                    | <span data-ttu-id="34244-112">Engedélyek (a legalacsonyabb szintűtől a legmagasabb szintűig)</span><span class="sxs-lookup"><span data-stu-id="34244-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="34244-113">Delegált (munkahelyi vagy iskolai fiók)</span><span class="sxs-lookup"><span data-stu-id="34244-113">Delegated (work or school account)</span></span> | <span data-ttu-id="34244-114">user\_impersonation</span><span class="sxs-lookup"><span data-stu-id="34244-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="34244-115">HTTPS-kérelem</span><span class="sxs-lookup"><span data-stu-id="34244-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="34244-116">A kérelem megfelel az OData szabványoknak.</span><span class="sxs-lookup"><span data-stu-id="34244-116">The request conforms to OData standards.</span></span> <span data-ttu-id="34244-117">A {requestId}, a {leaveType}, a {leaveDate}, a {dataArea} és a paraméterek a MyLeaveRequests entitás összetett természetes kulcsát alkotó mezőket jelentik.</span><span class="sxs-lookup"><span data-stu-id="34244-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="34244-118">Noha a MyLeaveRequests entitás mezői a szabadságkérelem egy adott sorára hivatkoznak, a küldési API hívása a teljes szabadságkérelmet (az összes sort) elküldi a munkafolyamatba.</span><span class="sxs-lookup"><span data-stu-id="34244-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="34244-119">Kérelem fejléce</span><span class="sxs-lookup"><span data-stu-id="34244-119">Request headers</span></span>

| <span data-ttu-id="34244-120">Fejléc</span><span class="sxs-lookup"><span data-stu-id="34244-120">Header</span></span>         | <span data-ttu-id="34244-121">Value</span><span class="sxs-lookup"><span data-stu-id="34244-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="34244-122">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="34244-122">Authorization</span></span>  | <span data-ttu-id="34244-123">Tulajdonosi {token} (kötelező)</span><span class="sxs-lookup"><span data-stu-id="34244-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="34244-124">Tartalomtípus</span><span class="sxs-lookup"><span data-stu-id="34244-124">Content-Type</span></span>   | <span data-ttu-id="34244-125">alkalmazás/json</span><span class="sxs-lookup"><span data-stu-id="34244-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="34244-126">Kérelem törzse</span><span class="sxs-lookup"><span data-stu-id="34244-126">Request body</span></span>

<span data-ttu-id="34244-127">Ehhez a metódushoz ne adjon meg kérelemtörzset.</span><span class="sxs-lookup"><span data-stu-id="34244-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="34244-128">Válasz</span><span class="sxs-lookup"><span data-stu-id="34244-128">Response</span></span>

<span data-ttu-id="34244-129">A sikeres válasz mindig **204 Nincs tartalom** válasz.</span><span class="sxs-lookup"><span data-stu-id="34244-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="34244-130">A jogosulatlan hívások **401 Nem engedélyezett** vagy **403 Tiltott** választ kapnak.</span><span class="sxs-lookup"><span data-stu-id="34244-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="34244-131">Ha a küldés sikertelen (például az érvényesítés miatt), akkor a válasz **500 Kiszolgálóhiba**, és a válasz törzse tartalmaz egy JSON-objektumot a további részletekkel.</span><span class="sxs-lookup"><span data-stu-id="34244-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="34244-132">Példa</span><span class="sxs-lookup"><span data-stu-id="34244-132">Example</span></span>

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a><span data-ttu-id="34244-133">Ellenőrzési és hibaüzenetek</span><span class="sxs-lookup"><span data-stu-id="34244-133">Validation and error messages</span></span>

<span data-ttu-id="34244-134">A küldési API hívásának részeként a Human Resources elvégzi az üzleti logika érvényesítését az elküldés előtt, ami biztosítja, hogy a szabadságkérelem érvényes állapotban van az elküldéshez.</span><span class="sxs-lookup"><span data-stu-id="34244-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="34244-135">A válaszban előforduló esetleges hibaüzenetek azt jelzik, hogy az ellenőrzés sikertelen:</span><span class="sxs-lookup"><span data-stu-id="34244-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="34244-136">A kérelem a(z) „{LeaveTypeId}” egyenleget a(z) {date} esetén engedélyezett minimális egyenleg alá mozdítaná.</span><span class="sxs-lookup"><span data-stu-id="34244-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="34244-137">Befejezett állapotú szabadságkérelem nem küldhető el.</span><span class="sxs-lookup"><span data-stu-id="34244-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="34244-138">A kérelem nem küldhető el vagy nem menthető, mivel nem történt módosítás.</span><span class="sxs-lookup"><span data-stu-id="34244-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="34244-139">Adja meg vagy frissítse az összeget vagy a szabadság típusát, majd próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="34244-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="34244-140">A megadott szabadságkérelemben egy vagy több nap szerepel ugyanazzal a dátummal és szabadságtípussal meglévő függő kérelemként.</span><span class="sxs-lookup"><span data-stu-id="34244-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="34244-141">A módosítások elvégzéséhez hívja újra a meglévő kérelmet.</span><span class="sxs-lookup"><span data-stu-id="34244-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="34244-142">A(z) „{ReasonCodeId}” okkód nem vonatkozik a kérésben szereplő egyik szabadságtípusra sem.</span><span class="sxs-lookup"><span data-stu-id="34244-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="34244-143">A „{LeaveTypeId}” típusú szabadsághoz okkód szükséges.</span><span class="sxs-lookup"><span data-stu-id="34244-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="34244-144">Válassza ki a megfelelő típust és okkódot.</span><span class="sxs-lookup"><span data-stu-id="34244-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="34244-145">A szabadság elküldése nem volt sikeres.</span><span class="sxs-lookup"><span data-stu-id="34244-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="34244-146">A szabadság vázlat állapotúként lett mentve.</span><span class="sxs-lookup"><span data-stu-id="34244-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="34244-147">Lásd még</span><span class="sxs-lookup"><span data-stu-id="34244-147">See also</span></span>

- [<span data-ttu-id="34244-148">MyLeaveRequests áttekintése</span><span class="sxs-lookup"><span data-stu-id="34244-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="34244-149">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="34244-149">Authentication</span></span>](hr-developer-api-authentication.md)