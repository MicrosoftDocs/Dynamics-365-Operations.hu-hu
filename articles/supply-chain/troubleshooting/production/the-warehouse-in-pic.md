---
title: A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron.
description: A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron (BOM).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026566"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron

Tudásbáziscikk száma: 4614848

## <a name="symptoms"></a>Tünetek

A kitárolásilista-naplóban található raktár nem frissül egy anyagjegyzéksoron (BOM).

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. Ha olyan kitárolásilista-naplósor jön létre, amely hivatkozik (a tételazonosítón keresztül) egy termelési anyagjegyzéksorra, a termelési anyagjegyzéksor raktára nem frissül, ha a termelési kitárolásilista-napló sorában később megváltozik a raktár dimenzió.
