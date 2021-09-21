---
title: A készletnapló munkafolyamata soha nem befejezett, és a napló nem dolgozható fel
description: A napló-jóváhagyási munkafolyamat elküldése után a munkafolyamat feldolgozása leáll, és a naplókat nem lehet szerkeszteni és feldolgozni.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9430068f9c2d92c894817db04143297de6c6aa6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476514"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>A készletnapló munkafolyamata soha nem befejezett, és a napló nem dolgozható fel

## <a name="symptoms"></a>Tünetek

A napló-jóváhagyási munkafolyamat elküldése után a munkafolyamat feldolgozása leáll, és a naplókat nem lehet szerkeszteni és feldolgozni.

## <a name="resolution"></a>Megoldás

Több oka is lehet annak, hogy miért nem fejeződött be a munkafolyamat feldolgozása. Ellenőrizze a következő problémákat:

- Ugorjon a **Készletkezelés &gt; Beállítás &gt; Készletkezelési munkafolyamatok** elemhez, és tekintse át az érintett munkafolyamat konfigurációját. A további tudnivalókat lásd: [Készletnapló-jóváhagyási munkafolyamatok](/dynamics365/supply-chain/inventory/inventory-journal-workflow.md).
- Lehet, hogy a munkafolyamat kivételt vagy hibát észlelt. Tekintse át az érintett munkafolyamat munkatétel-előzményeit, és ellenőrizze, hogy tartalmaz-e olyan alkalmazáshibát, amely megszakítja a munkafolyamatot.
- A készletnapló csak jóváhagyás után frissíthető vagy szerkeszthető. Ha a visszahívás aktív, megpróbálhatja visszahívni a naplót. A munkafolyamat kötegelt feladatának végrehajtása több okból is felfüggeszthető. Ezeknek az okoknak egy részét a munkafolyamat-keretrendszer problémája okozhatja.
