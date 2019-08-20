---
title: Dokumentumok nyomtatása
description: A Microsoft Dynamics 365 for Finance and Operations alkalmazásban a dokumentumok nyomtathatók helyi nyomtató vagy a hálózathoz csatlakoztatott eszköz használatával. A cikk a dokumentumok nyomtatási módjainak áttekintését nyújtja.
author: TJVass
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbc45865b55b4794202408ca19a0776440382fdd
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850071"
---
# <a name="document-printing"></a>Dokumentumok nyomtatása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations alkalmazásban a dokumentumok nyomtathatók helyi nyomtató vagy a hálózathoz csatlakoztatott eszköz használatával. A cikk a dokumentumok nyomtatási módjainak áttekintését nyújtja.

## <a name="printing-overview"></a>Nyomtatás áttekintése

A Microsoft Dynamics 365 for Finance and Operations beépített szolgáltatásokat és ügyfélalkalmazásokat tartalmaz, amelyek megkönnyítik az üzleti tevékenységeket támogató dokumentumok előállítását, tárolását és terjesztését. A Finance and Operations alkalmazásban a dokumentumok nyomtathatók helyi nyomtató vagy a hálózathoz csatlakoztatott eszköz használatával. Ezenkívül exportálhatja a Finance and Operations lapokat és jelentéseket közvetlenül az ügyfélből PDF-fájlként vagy Microsoft Office-dokumentumokként. Végül az elosztott terhelés lehetővé teszi az üzleti dokumentumok nyomtatását közvetlenül mobileszközről a hálózati erőforrások használatával. Annak ellenére, hogy a nyomtatási követelmények eltérőek lehetnek, általában minden iparágban létre kell hozni az üzleti dokumentumok nyomtatott példányait a Finance and Operations használatával. Egyedi kihívás szolgáltatott alkalmazásokból hálózati eszközökön dokumentumokat nyomtatni. Íme néhány példa:

- A nyomtató-illesztőprogramok nem mindig érhetők el a felhasználó eszközén.
- Előfordulhat, hogy a felhasználó eszköze nem kapcsolódik a vállalati hálózatra.

Erre a célra kijelölt állomás használatával és a következő pár egyszerű lépés végrehajtásával a rendszergazdák úgy konfigurálhatják a telepítéseket, hogy a felhasználók közvetlenül az üzleti alkalmazásokból nyomtathassanak a hálózati eszközökön.

### <a name="printing-scenarios-in-finance-and-operations-applications"></a>Nyomtatási esetek a Finance and Operations alkalmazásokban

A következő táblázat leírja a három elsődleges nyomtatási esetet a Finance and Operations alkalmazásokban.

| Eset                        | Cél                                                      | Megoldás |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. Annak a nyomtatása, ami látható        | A böngésző jelenleg látható tartalmának nyomtatása             | A böngésző számára a weblap „nyomtatásra optimalizált” verziója jön létre. |
| 2. interaktív nyomtatása         | A helyben csatlakoztatott eszközön pontos dokumentum nyomtatása. | A jelentés a PDF-verzió exportálható, és letölthető a böngészőbe. |
| 3. Nyomtatás egy hálózati eszközön | Pontos dokumentumok küldése a tartomány egyik nyomtató eszközére.     | A vevő tartományban üzemeltetett kiszolgálón futó ügyfélalkalmazásba pontos dokumentum lett elküldve. |

Mivel a megoldás változó, a helyzettől függően a Finance and Operations alkalmazások beépített szolgáltatásokkal és eszközökkel segítik a felhasználókat céljaik elérésében:

- **1. eset** – a böngésző HTML5-ügyfél megjelenítése támogatja.
- **2. eset** – ügyfélalkalmazásokat és a Microsoft Office 365 szolgáltatásokat használja.
- **3. eset** – ügyfélalkalmazások és a Microsoft Azure által üzemeltetett szolgáltatások támogatását igényli.

Az Azure előfizetésbe telepített platform mellett a Finance and Operations integrált, első fél Azure alkalmazást nyújt az ügyfeleknek,amely segítségével könnyebben használhatják a tartomány által szolgáltatott eszközöket dokumentumok nyomtatására.

## <a name="service-overview"></a>Szolgáltatás áttekintése
Miközben a dokumentumok, amelyeket az üzemeltetett alkalmazások hoztak létre, a hálózathoz csatlakoztatott eszközön nyomtatásra várnak, egy Azure blob-tárolóban tárolódnak. A [dokumentum útvonaltervezési ügynök](install-document-routing-agent.md) Azure hitelesítést használ biztonságos csatorna létrehozására az Azure-szolgáltatásokhoz.

**Végrehajtási sorrend**

1. A jelentés létrehozója a Microsoft SQL Server Reporting Services (SSRS), és az Azure blob-tároló tárolja. A csatlakoztatott nyomtatóbeállítások tárolása a dokumentummal együtt történik.
2. A dokumentum útvonaltervezési ügynök lekérdezi az Azure szolgáltatási busz várólistáját az aktív feladatokért.
3. A dokumentumot letölti a dokumentum útvonaltervezési ügynök, és a hálózati nyomtató nyomtatási sorába kerül.

Az ügyfélalapú megoldással a vevők kezelhetik a nyomtatási igények mértékét. A nagy mennyiségű nyomtatási feladattal rendelkező ügyfelek sok dokumentum útvonaltervezési ügynököt telepíthetnek az egyidejű nyomtatási műveletek számának növelésére. Az is előfordul, hogy egyes vevők nagyon kevés telepített dokumentum útvonaltervezési ügynököt alkalmaznak a várható nyomtatási igényekhez.

### <a name="service-components-for-network-printing"></a>Hálózati nyomtatás szolgáltatás-összetevői

A következő ábra bemutatja az alapvető összetevőket, amelyek segítik a hálózati nyomtatási műveletek támogatását.

[![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

Vegye figyelembe, hogy egyetlen nyomtatót több dokumentumot útválasztás ügynökhöz is lehet regisztrálni. A nyomtatóbeállítások feloldásához az üzemeltetett szolgáltatás a hálózati elérési utat használja, amely egyedileg azonosítja az összes hálózati nyomtatót. Emiatt akkor is, ha a nyomtató több ügyféllel van regisztrálva, egyetlen kiválasztható elemként jelenik meg a Finance and Operations alkalmazásokban rendelkezésre álló nyomtatók listáján.
