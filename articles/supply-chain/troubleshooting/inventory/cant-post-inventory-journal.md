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
ms.openlocfilehash: 5e8168a20a1fa4f52d28129eebb9931b31157ced
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2022
ms.locfileid: "8488967"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>A készletnapló munkafolyamata soha nem befejezett, és a napló nem dolgozható fel

## <a name="symptoms"></a>Tünetek

A napló-jóváhagyási munkafolyamat elküldése után a munkafolyamat feldolgozása leáll, és a naplókat nem lehet szerkeszteni és feldolgozni.

## <a name="resolution"></a>Megoldás

Több oka is lehet annak, hogy miért nem fejeződött be a munkafolyamat feldolgozása. Ellenőrizze a következő problémákat:

- Ugorjon a **Készletkezelés &gt; Beállítás &gt; Készletkezelési munkafolyamatok** elemhez, és tekintse át az érintett munkafolyamat konfigurációját. A további tudnivalókat lásd: [Készletnapló-jóváhagyási munkafolyamatok](../../inventory/inventory-journal-workflow.md).
- Lehet, hogy a munkafolyamat kivételt vagy hibát észlelt. Tekintse át az érintett munkafolyamat munkatétel-előzményeit, és ellenőrizze, hogy tartalmaz-e olyan alkalmazáshibát, amely megszakítja a munkafolyamatot.
- A készletnapló csak jóváhagyás után frissíthető vagy szerkeszthető. Ha a visszahívás aktív, megpróbálhatja visszahívni a naplót. A munkafolyamat kötegelt feladatának végrehajtása több okból is felfüggeszthető. Ezeknek az okoknak egy részét a munkafolyamat-keretrendszer problémája okozhatja.
