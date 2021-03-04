---
title: Naplózási házirendek meghatározása a forrásbizonylatok számára
description: Ez a témakör bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba720fd1bbbbf8b4f3b936d65d9d7840432f291a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444059"
---
# <a name="define-audit-policies-for-source-documents"></a>Naplózási házirendek meghatározása a forrásbizonylatok számára

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok. A példa költségjelentéseket használ szállodai költségtípussal. Ez az eljárás az USMF bemutatócéget használja. A könyvvizsgáló szerepkör tartalmazza a megfelelő engedélyeket ezen műveletek elvégzése érdekében.

1. A navigációs ablakban nyissa meg **Modulokat > Könyvvizsgálati munkaterület > Beállítás > Irányelv-szabály típusa** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Szabály neve** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Lekérdezés neve** mezőben válassza ki a **Költségjelentés** sort
6. A **lekérdezés típusa** mezőben válassza ki az **Összesítés** parancsot
7. A **Jogi személy** mezőben válasszon egy **Jogi személyt**.
8. A **Dokumentum dátumreferenciája** mezőben válassza ki a **Módosítás dátuma és időpontja** elemet
9. Válassza a **Mentés** lehetőséget.
10. A navigációs ablakban nyissa meg **Modulokat > Könyvvizsgálati munkaterület > Beállítás > Auditirányelvek** lehetőséget.
11. Válassza az **Új** lehetőséget.
12. Írjon be egy értéket a **Név** mezőbe.
13. Bontsa ki az **Irányelv szervezetei** szakaszt.
14. A fán válassza ki a **Contoso Szórakozás rendszer USA** majd a **Hozzáadás** lehetőséget.
15. A fán válassza ki a **Contoso Consulting USA** majd a **Hozzáadás** lehetőséget.
16. A fán válassza ki a **Contoso Retail USA** majd a **Hozzáadás** lehetőséget.
17. Csukja be az **Irányelv szervezetei** szakaszt.
18. Bontsa ki az **Irányelvszabályok** szakaszt.
19. A listában keresse meg és válassza ki a korábban létrehozott Irányelvszabályt.
20. Válassza ki az **Irányelvszabály létrehozása** lehetőséget.
21. Az **Érvényesség dátuma** mezőben adjon meg egy dátumot és időpontot.
22. Válassza ki a **Szűrő** elemet.
23. A listában válassza ki a **Költségkategória** sort, és adja meg a **Szálloda** adatait
24. A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.
25. Válassza ki az **Összesítés** lapot.
26. Válassza a **Hozzáadás** lehetőséget.
27. A listában válassza ki a **Tranzakció összege** mezőértékét
28. A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.
29. Az **Összesítő funkcióban** válassza ki az **Összeg** lehetőséget.
30. A **Csoportosítás alapja** lap kiválasztása
31. Válassza a **Hozzáadás** lehetőséget.
32. A listából válasszon egy **Alkalmazott** értéket.
33. Válassza a **Hozzáadás** lehetőséget.
34. A listából válasszon egy **Költségkategória** értéket.
35. A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.
36. Válassza a **Rendelkezik** lapot.
37. Válassza a **Hozzáadás** lehetőséget.
38. **Tranzakcióösszegek** kijelölése.
39. A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.
40. Az **Összesítő funkcióban** válassza ki az **Összeg** lehetőséget.
41. A **Feltétel** mezőbe írja be a `>2000` értéket.
42. Válassza ki az **OK** lehetőséget.
43. Válassza a **Teszt** lehetőséget.
44. A **Bizonylatkijelölés kezdő dátuma** mezőben adjon meg egy dátumot és egy időpontot.
45. A **Bizonylatkijelölés záró dátuma** mezőben adjon meg egy dátumot és egy időpontot.
46. Válassza a **Teszt futtatása** lehetőséget.
47. A Művelet panelen kattintson a **Könyvvizsgálati irányelv** elemre.
48. Válassza a **További beállítások** lehetőséget
49. A **Kezdő dátum** mezőben adjon meg egy dátumot és időpontot.
50. A **Záró dátum** mezőben adjon meg egy dátumot és időpontot.
51. Válassza a **Köteg** lehetőséget
52. Bontsa ki a **Futtatás a háttérben** szakaszt.
53. Válassza az **Igen** lehetőséget a **Kötegelt feldolgozás** mezőben.
54. Válassza ki az **OK** lehetőséget.
55. A navigációs ablakban nyissa meg **Modulok > Könyvvizsgálati munkaterület > Beállítás > Auditesetek** lehetőséget.
56. Keresse meg és jelölje ki a kívánt rekordot a listán.
57. Bontsa ki a **Társítások** szakaszt.
58. Keresse meg és jelölje ki a kívánt rekordot a listán.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]