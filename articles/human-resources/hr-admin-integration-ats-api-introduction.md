---
title: Pályázó követésrendszer integrációs API bevezetése
description: Ez a témakör a Dynamics 365 Human Resources Pályázó követésrendszer (ATS) integrációs API-t írja le.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48e368fe69443a5105ddba78a887bf9159bfe52a
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125593"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Pályázó követésrendszer integrációs API bevezetése

Ez a témakör a Dynamics 365 Human Resources Pályázó követésrendszer (ATS) integrációs API-t írja le. Az API célja a Dynamics 365 Human Resources és az ATS-ek közötti leegyszerűsített integráció engedélyezése.

![ATS integrációs folyamat](media/hr-admin-integration-ats-api-introduction-flow.png)

Az integrált tapasztalat akkor kezdődik a Human Resources rendszerben, amikor egy felvételi vezető toborzási kérelmet hoz létre. A kérelem aktiválásakor az ATS lekéri a toborzási projekt létrehozására vonatkozó kérelem részleteit. Ezután követi a toborzási folyamatot a jelölt pozíció(k)ra történő kiválasztásához és felvételéhez. Végül az ATS úgy fejezi be az oda-vissza integrációt, hogy elküldi a kiválasztott jelölt rekordját a Human Resources rendszerbe. A jelölt rekordja ezután több, felvételre vonatkozó ellenőrzésen és munkafolyamaton mehet át az alkalmazotti rekord létrehozása érdekében.

Az integráció engedélyezéséhez a Human Resources alkalmazás a következő összetevőket adta hozzá:

1.  A toborzási kérelem létrehozására használható funkciók.
2.  Kibővített jelölti profil és a kapcsolódó munkafolyamatok.
3.  Integrációs API, amely az új funkciókat megnyitja az alkalmazások integrálása előtt.

A toborzási kérelem és a jelölti funkció beállításával és használatával kapcsolatos további tudnivalókat lásd: [Jelöltek toborzása](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Ez az API Microsoft Dataverse rendszerben (korábbi nevén Common Data Service) működik. Az API-val való minden RESTful interakció az OData rendszert használó Microsoft Dataverse webes API-n keresztül történik. Ez az API a Dataverse webes API alkészlete. A Dataverse webes API definiálja a hitelesítés, a szolgáltatásiszint-szerződések, a köteg, a párhuzamossági vezérlés és a hibakezelés jellemzőit.

További általános információ a Microsoft Dataverse webes API-ról, lásd:

- [Mi az a Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [A Microsoft Dataverse webes API használata](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse fejlesztői iránymutatás](https://docs.microsoft.com/powerapps/developer/data-platform)

A fenti dokumentáció részletes és fejlesztői útmutatásokat tartalmaz a Dataverse webes API használatával kapcsolatban, ilyen például a [hitelesítés kezelése](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), a [műveletek végrehajtása](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), a [Postman és az API használata](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api), valamint [változáskövetési vagy eltérési tokenek használata](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) az API-val.

### <a name="option-sets"></a>Beállításkészletek

Az ATS integrációs API-jának ebben a dokumentumban ismertetett adatmodellje olyan beállításkészleteket tartalmaz, amelyek entitástulajdonságokhoz rendelt, felsorolt értékeket tartalmaznak. A Dataverse webes API-t használó beállításkészletekkel való munka részletes részleteit lásd: [Beállításkészletek létrehozása és frissítése a webes API segítségével](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets). A beállításkészleteket az egyes Dataverse-környezetekhez határozzák meg.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>A Dataverse for Human Resources számára elérhető virtuális táblák

Az ATS integrációs API végpontjai a Microsoft Dataverse virtuális tábla platformképességeit használják. Alapértelmezés szerint a virtuális táblák és a hozzájuk kapcsolódó API-végpontok nincsenek telepítve a Human Resources-környezetekben, lehetővé téve a szervezetek számára, hogy ők határozzák meg, hogy mely OData-végpontok lesznek kitéve a környezetnek. Az API használatához létre kell hozni a Human Resources-entitások virtuális tábláit a környezet számára. 

Az API virtuális tábláinak létrehozásáról lásd: [Dataverse virtuális táblák konfigurálása](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="data-model"></a>Adatmodell

Az adatmodell két fő entitás köré csoportosul:

- A **RecruitingRequest** egy vagy több nyitott beosztásra vonatkozó toborzási kérés egy ATS-nek. Példalekérdezéshez lásd: [Példa lekérdezésre toborzási kérelemhez](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **A CandidateToHire** a pozícióra vonatkozó ajánlatot elfogadó jelölt részletes adatait tartalmazza. A **Személy** a jelöltre vonatkozik. Egy személynek a vállalatnál több szerepköre is lehet, például jelölt, dolgozó, alkalmazott vagy alvállalkozó. Példalekérdezés: [Példa lekérdezésre Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

A következő ábra az API-n belüli kapcsolatokat illusztrálja. Különböző típusok idegen kulcsokkal rendelkeznek egyéb, itt nem ábrázolt, a Human Resources rendszerben már létező entitásokhoz kapcsolódóan. Ez a dokumentum a toborzási integrációs helyzetekre jellemző entitásokkal kapcsolatban tartalmaz tájékoztatást. A Dynamics 365 Human Resources rendszer Dataverse webes API-jában azonban számos más entitás is releváns lehet az integráció szempontjából. Például az itt nem meghatározott dolgozókra, munkakörökre, pozíciókra vagy más entitásokra vonatkozóan is szüksége lehet részletes adatokra. Ezen entitások közül többre az idegenkulcs-kapcsolatok vagy navigációs tulajdonságok hivatkoznak.

![ATS-integráció az API adatmodell használatával](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Toborzási kérelem és a kapcsolódó entitások és beállításkészletek

Példa lekérdezésre: 

- [Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Entitások:

- [Toborzási kérelem](hr-admin-integration-ats-api-recruiting-request.md)
- [Toborzási kérelem beosztása](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Toborzási kérelem – szakértelem](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Toborzási kérelem – végzettség](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Toborzási kérelem helye](hr-admin-integration-ats-api-recruiting-request-location.md)

Beállításkészletek:

- [Munka mentességi állapota](hr-admin-integration-ats-api-job-exempt-status.md)
- [Toborzási kérelem – pozíció állapota](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Toborzási kérelem állapota](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Jogszabállyal kapcsolatos álláskategória](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Felvenni kívánt jelölt és a kapcsolódó entitások és beállításkészletek

Példa lekérdezésre:

- [Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Entitások:

- [Felveendő jelentkező](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Személy](hr-admin-integration-ats-api-person.md)
- [Személy végzettsége](hr-admin-integration-ats-api-person-education.md)
- [Személy szakmai tapasztalata](hr-admin-integration-ats-api-person-professional-experience.md)
- [Személy címe](hr-admin-integration-ats-api-person-address.md)
- [Fél kapcsolattartója](hr-admin-integration-ats-api-party-contact.md)
- [Személy szakértelme](hr-admin-integration-ats-api-person-skill.md)
- [Minősítési szint](hr-admin-integration-ats-api-rating-level.md)
- [Személy tanúsítványa](hr-admin-integration-ats-api-person-certificate.md)
- [Tanúsítvány típusa](hr-admin-integration-ats-api-certificate-type.md)
- [Személy szűrési adatai](hr-admin-integration-ats-api-person-screening.md)
- [Szűréstípusok](hr-admin-integration-ats-api-screening-types.md)
- [Személy személyazonosító száma](hr-admin-integration-ats-api-person-identification-number.md)

Beállításkészletek:

- [Pályázó integrációs eredménye](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Üres Igen Nem](hr-admin-integration-ats-api-blank-yes-no.md)
- [Végrehajtás állapota](hr-admin-integration-ats-api-completion-status.md)
- [Kapcsolattartó típusa](hr-admin-integration-ats-api-contact-type.md)
- [Végzettség jóváírásának alapja](hr-admin-integration-ats-api-education-credit-basis.md)
- [Nem](hr-admin-integration-ats-api-gender.md)
- [Családi állapot](hr-admin-integration-ats-api-marital-status.md)
- [Év hónapjai](hr-admin-integration-ats-api-months-of-year.md)
- [Nem Igen](hr-admin-integration-ats-api-no-yes.md)
- [Időszakegység](hr-admin-integration-ats-api-period-unit.md)
- [Szűrési gyakoriság](hr-admin-integration-ats-api-screening-frequency.md)
- [Szűrési gyakoriság generálása innen:](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Szakértelmi szint típusa](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Lásd még

[Jelöltek toborzása](hr-personnel-recruit.md)<br>
[Mi az a Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[A Microsoft Dataverse webes API használata](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[Beállításkészletek létrehozása és frissítése a webes API segítségével](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]