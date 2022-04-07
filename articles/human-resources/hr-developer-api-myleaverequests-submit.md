---
title: Szabadságkérelem elküldése munkafolyamathoz
description: A Microsoft Dynamics 365 Human Resources alkalmazásban a MyLeaveRequests submit () alkalmazásprogramozási felületet (API) használhatja a szabadságkérelmek elküldésére a munkafolyamatba.
author: twheeloc
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: caea924a2bab9439374ea933d4a0886059e5fe53
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2022
ms.locfileid: "8534136"
---
# <a name="submit-a-leave-request-to-workflow"></a>Szabadságkérelem elküldése munkafolyamathoz


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources alkalmazásban a MyLeaveRequests submit () alkalmazásprogramozási felületet (API) használhatja a szabadságkérelmek elküldésére a munkafolyamatba. Ez az API műveletként használható a MyLeaveRequests OData entitáson.

## <a name="prerequisites"></a>Előfeltételek

A szabadságkérelmet menteni kell az adatbázisba, és a beolvashatónak kell lennie a MyLeaveRequests entitáson keresztül.

## <a name="permissions"></a>Engedélyek

Az API hívásához a következő engedélyek egyike szükséges. Az engedélyekkel és a kiválasztásukkal kapcsolatos további tudnivalókat lásd: [Hitelesítés](hr-developer-api-authentication.md).

| Engedély típusa                    | Engedélyek (a legalacsonyabb szintűtől a legmagasabb szintűig) |
|------------------------------------|--------------------------------------------------------|
| Delegált (munkahelyi vagy iskolai fiók) | user\_impersonation                                    |

## <a name="https-request"></a>HTTPS-kérelem

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

A kérelem megfelel az OData szabványoknak. A {requestId}, a {leaveType}, a {leaveDate}, a {dataArea} és a paraméterek a MyLeaveRequests entitás összetett természetes kulcsát alkotó mezőket jelentik.

> [!NOTE]
> Noha a MyLeaveRequests entitás mezői a szabadságkérelem egy adott sorára hivatkoznak, a küldési API hívása a teljes szabadságkérelmet (az összes sort) elküldi a munkafolyamatba.

### <a name="request-headers"></a>Kérelem fejléce

| Fejléc         | Value                     |
|----------------|---------------------------|
| Hitelesítés  | Tulajdonosi {token} (kötelező) |
| Tartalomtípus   | alkalmazás/json          |

### <a name="request-body"></a>Kérelem törzse

Ehhez a metódushoz ne adjon meg kérelemtörzset.

### <a name="response"></a>Válasz

A sikeres válasz mindig **204 Nincs tartalom** válasz.

A jogosulatlan hívások **401 Nem engedélyezett** vagy **403 Tiltott** választ kapnak.

Ha a küldés sikertelen (például az érvényesítés miatt), akkor a válasz **500 Kiszolgálóhiba**, és a válasz törzse tartalmaz egy JSON-objektumot a további részletekkel.

## <a name="example"></a>Példa

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

## <a name="validation-and-error-messages"></a>Ellenőrzési és hibaüzenetek

A küldési API hívásának részeként a Human Resources elvégzi az üzleti logika érvényesítését az elküldés előtt, ami biztosítja, hogy a szabadságkérelem érvényes állapotban van az elküldéshez. A válaszban előforduló esetleges hibaüzenetek azt jelzik, hogy az ellenőrzés sikertelen:

 - A kérelem a(z) „{LeaveTypeId}” egyenleget a(z) {date} esetén engedélyezett minimális egyenleg alá mozdítaná.
 - Befejezett állapotú szabadságkérelem nem küldhető el.
 - A kérelem nem küldhető el vagy nem menthető, mivel nem történt módosítás. Adja meg vagy frissítse az összeget vagy a szabadság típusát, majd próbálkozzon újra.
 - A megadott szabadságkérelemben egy vagy több nap szerepel ugyanazzal a dátummal és szabadságtípussal meglévő függő kérelemként. A módosítások elvégzéséhez hívja újra a meglévő kérelmet.
 - A(z) „{ReasonCodeId}” okkód nem vonatkozik a kérésben szereplő egyik szabadságtípusra sem.
 - A „{LeaveTypeId}” típusú szabadsághoz okkód szükséges. Válassza ki a megfelelő típust és okkódot.
 - A szabadság elküldése nem volt sikeres. A szabadság vázlat állapotúként lett mentve.

## <a name="see-also"></a>Lásd még

- [MyLeaveRequests áttekintése](hr-developer-api-myleaverequests-overview.md)
- [Hitelesítés](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
