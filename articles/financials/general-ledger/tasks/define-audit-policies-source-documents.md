--- 
title: "Naplózási házirendek meghatározása a forrásbizonylatok számára"
description: "Ez az eljárás bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok."
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Naplózási házirendek meghatározása a forrásbizonylatok számára

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok. A példa költségjelentéseket használ szállodai költségtípussal. Ez az eljárás az USMF bemutatócéget használja. A könyvvizsgáló szerepkör tartalmazza a megfelelő engedélyeket ezen műveletek elvégzése érdekében.

1. Ugrás a Könyvvizsgálati munkaterület > Beállítás > Irányelvszabály-típus menüpontokra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szabály neve mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Lekérdezés neve mezőben válassza ki a Költségjelentés sort
6. A lekérdezés típusa mezőben válassza ki az Összesítés parancsot
7. A Jogi személy mezőben válasszon egy Jogi személyt.
8. A Dokumentum dátumreferenciája mezőben válassza ki a Módosítás dátuma és időpontja elemet
9. Kattintson a Mentés gombra.
10. Ugrás a Könyvvizsgálati munkaterület > Beállítás > Könyvviteli irányelvek menüpontokra.
11. Kattintson az Új lehetőségre.
12. Írjon be egy értéket a Név mezőbe.
13. Bontsa ki az Irányelv szervezetei szakaszt.
14. A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.
15. Kattintson a Hozzáadás gombra.
16. A fán válassza ki a „Contoso Consulting USA” lehetőséget.
17. Kattintson a Hozzáadás gombra.
18. A fán válassza ki a „Contoso Retail USA” lehetőséget.
19. Kattintson a Hozzáadás gombra.
20. Csukja be az Irányelv szervezetei szakaszt.
21. Bontsa ki az Irányelvszabályok szakaszt.
22. A listában keresse meg és válassza ki a korábban létrehozott Irányelvszabályt.
23. Kattintson az Irányelvszabályra.
24. Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.
25. Kattintson a Szűrő parancsra.
26. A listában válassza ki a Költségkategória sort, és adja meg a Szálloda adatait
27. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
28. Kattintson az Összesítés fülre.
29. Kattintson a Hozzáadás gombra.
30. A listában válassza ki a Tranzakció összege mezőértékét
31. A Mező mezőben adjon meg vagy válasszon ki egy értéket.
32. Az Összesítő funkcióban válassza ki az „Összeg”lehetőséget.
33. Kattintson a Csoport lapra.
34. Kattintson a Hozzáadás gombra.
35. A listából válasszon egy Alkalmazott értéket. 
36. Kattintson a Hozzáadás gombra.
37. A listából válasszon egy Költségkategória értéket.
38. A Mező mezőben adjon meg vagy válasszon ki egy értéket.
39. Kattintson a Megvan fülre.
40. Kattintson a Hozzáadás gombra.
41. Tranzakcióösszegek kijelölése
42. A Mező mezőben adjon meg vagy válasszon ki egy értéket.
43. Az Összesítő funkcióban válassza ki az „Összeg”lehetőséget.
44. A Feltétel mezőbe írja be a „>2000” értéket.
45. Kattintson az OK gombra.
46. Kattintson a Teszt gombra.
47. A Bizonylatkijelölés kezdő dátuma mezőben adjon meg egy dátumot és egy időpontot.
48. A Bizonylatkijelölés záró dátuma mezőben adjon meg egy dátumot és egy időpontot.
49. Kattintson a Teszt futtatása lehetőségre.
50. A Művelet panelen kattintson a Könyvvizsgálati irányelv elemre.
51. Kattintson a további beállítások lehetőségre.
52. A „Kezdő dátum” mezőben adjon meg egy dátumot és időpontot.
53. A Záró dátum mezőben adjon meg egy dátumot és időpontot.
54. Kattintson a Kötegre.
55. Bontsa ki a Futtatás a háttérben szakaszt.
56. Válassza az Igen lehetőséget a Kötegelt feldolgozás mezőben.
57. Kattintson az OK gombra.
58. Ugrás a Könyvvizsgálati munkaterület > Könyvvizsgálati esetek menüpontokra.
59. Keresse meg és jelölje ki a kívánt rekordot a listán.
60. A listában kattintson a kijelölt sorban lévő hivatkozásra.
61. Bontsa ki a Társítás szakaszt.
62. Keresse meg és jelölje ki a kívánt rekordot a listán.
63. A listában kattintson a kijelölt sorban lévő hivatkozásra.


