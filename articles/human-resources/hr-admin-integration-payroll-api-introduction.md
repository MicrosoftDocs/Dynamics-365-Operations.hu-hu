---
title: Bérlista-integrációs API bemutatása
description: Ez a témakör a Dynamics 365 Human Resources bérszámfejtés integrációs API-ját írja le.
author: twheeloc
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3743561e3ea3c798c37d71d851eb6b197c8d1c41
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533826"
---
# <a name="payroll-integration-api-introduction"></a>Bérlista-integrációs API bemutatása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a dokumentum a Dynamics 365 Human Resources bérszámfejtés integrációs API-ját írja le. Az API leegyszerűsített integrációt tesz lehetővé a Human Resources és a partneri bérlistarendszerek között. Az integrált tapasztalat a Human Resourcesban az alkalmazotti profillal, a fizetéssel és a levonással, valamint a hozzájárulási adatokkal kezdődik. Amikor alkalmazottat szerződtet, és beviszi a szükséges profilt és fizetési adatokat a Human Resourcesba, a bérszámfejtő rendszer ezeket az adatokat a bérlista feldolgozásához használja. A program az alkalmazottra vonatkozó frissítéseket vagy fizetési adatokat későbbi fizetési futtatás során is lekéri használatra.

[![Bérlista-integrációs folyamat.](media/hr-admin-integration-payroll-api-introduction-flow.png)](media/hr-admin-integration-payroll-api-introduction-flow-2.png#lightbox)

Az integráció engedélyezéséhez a Human Resources alkalmazás a következő összetevőket tartalmazza:

- [Az alkalmazott fizetésre készként való megjelöléséhez használható funkció.](hr-compensation-payroll.md)
- Integrációs API, amely az új funkciókat megnyitja az alkalmazások integrálása előtt.

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Ez az API Microsoft Dataverse rendszerben (korábbi nevén Common Data Service) működik. Az API-val való minden RESTful interakció az OData rendszert használó Microsoft Dataverse webes API-n keresztül történik. Ez az API a Dataverse webes API alkészlete. A Dataverse webes API definiálja a hitelesítés, a szolgáltatásiszint-szerződések, a köteg, a párhuzamossági vezérlés és a hibakezelés jellemzőit.

További általános információ a Microsoft Dataverse webes API-ról, lásd:

- [Mi az a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [A Microsoft Dataverse webes API használata](/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse fejlesztői iránymutatás](/powerapps/developer/data-platform)

Ez a dokumentáció részletes adatokat és fejlesztői útmutatást tartalmaz a Dataverse webes API használatával kapcsolatban, beleértve a következő témaköröket:

- [Microsoft Dataverse hitelesítés a webes API-val](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Műveletek végrehajtása a webes API segítségével](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Postman használata a webes API-val](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [A változáskövetés használata az adatok külső rendszerekkel történő szinkronizálására](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>A Dataverse for Human Resources számára elérhető virtuális táblák

A bérszámfejtés integrációs API végpontjai a Microsoft Dataverse virtuális tábla platformképességeit használják. Alapértelmezés szerint a virtuális táblák és a hozzájuk kapcsolódó API-végpontok nincsenek telepítve a Human Resources-környezetekben, lehetővé téve a szervezetek számára, hogy ők határozzák meg, hogy mely OData-végpontok lesznek kitéve a környezetnek. Az API használatához létre kell hozni a Human Resources-entitások virtuális tábláit a környezet számára.

Az API virtuális tábláinak létrehozásáról lásd: [Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Adatmodell

A következő ábra az API-n belüli kapcsolatokat illusztrálja. Különböző típusok idegen kulcsokkal rendelkeznek egyéb, itt nem ábrázolt, a Human Resources rendszerben már létező entitásokhoz kapcsolódóan. Ez a dokumentum a bérszámfejtési integrációs helyzetekre jellemző entitásokkal kapcsolatban tartalmaz tájékoztatást. A Human Resources rendszer Dataverse webes API-jában azonban számos más entitás is releváns lehet az integráció szempontjából. Ezen entitások közül néhányra az idegenkulcs-kapcsolatok vagy navigációs tulajdonságok hivatkoznak.

[![Bérszámfejtés-integráció az API adatmodell használatával.](media/hr-admin-payroll-api-data-model.png)](media/hr-admin-payroll-api-data-model.png#lightbox)

## <a name="payroll-employee-and-related-entities"></a>Bérszámfejtési alkalmazott és kapcsolódó entitások

Entitások:

- [Bárlista alkalmazottja](hr-admin-integration-payroll-api-payroll-employee.md)
- [Bérlista dolgozói címe](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Fix kompenzációs konstrukció bérlistája](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md)
- [Változó kompenzációs konstrukció bérlistája](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md)
- [Bérlista szerinti beosztás feladata](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Bérlista szerinti beosztás](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Lásd még

[Bérlistaentitások létrehozása és áttekintése](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[A Human Resources paramétereinek konfigurálása](hr-setup-parameters.md)<br>
[Megosztott Human Resources paraméterek karbantartása](hr-setup-shared-parameters.md)<br>
[Mi az a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[A Microsoft Dataverse webes API használata](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
