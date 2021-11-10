---
title: IM 및 현재 상태 메뉴의 작업에 PowerShell 사용
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '요약: 비즈니스용 Skype 서버 및 현재 상태 메뉴에 대한 Cmdlet 매핑에 대한 제어판을 제공합니다.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888787"
---
# <a name="im-and-presence"></a>IM 및 현재 상태

이 문서에서는 cmdlet을 사용하여 레거시 제어판의 **IM** 및 현재 상태 메뉴 항목과 비슷한 결과를 얻을 수 있는 방법에 대해 설명합니다.

이 문서에서는 다음과 같은 하위 메뉴에 대해 설명합니다.

- [IM 및 현재 상태](#im-and-presence)
  - [파일 필터](#file-filter)
  - [URL 필터](#url-filter)

## <a name="file-filter"></a>파일 필터

**관리자는 파일 필터** 하위 메뉴를 사용하여 조직에서 파일 전송 필터 구성을 관리할 수 있습니다. 이러한 구성은 비즈니스용 Skype 서버 클라이언트를 사용하여 특정 파일 형식(예: .vbs 또는 파일 확장명을 사용하는 파일)을 전송하는 .ps1 차단하는 데 사용됩니다.

사용자가 파일 필터에 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype cmdlet을 사용합니다.

---

> **시나리오 1:** 모든 파일 필터 나열

   ![목록 파일 필터](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***예***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **시나리오 2:** 새 파일 필터 만들기

   ![파일 필터 만들기](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***예***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 3:** 선택한 파일 필터에 대한 세부 정보 확인

   ![파일 필터 다운로드](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***예***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 파일 필터 삭제

   ![파일 필터 삭제](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***예***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** 파일 필터 업데이트

   ![파일 필터 업데이트](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***예***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>URL 필터

관리자는 IM 및 현재 상태 아래에 **있는** **URL FILTER** 하위 메뉴 항목을 사용하여 특정 prefix가 있는 하이퍼링크가 차단되거나 활성화되지 않을 수 있도록 URL 필터를 구성할 수 있습니다. 즉, 참가자는 단순히 링크를 클릭하고 URI가 참조하는 사이트로 이동될 수 없습니다. 링크를 수동으로 복사하여 브라우저에 붙여넣아야 합니다.

**사용자가 URL FILTER에** 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 매핑할 수 있습니다.

---
> **시나리오 1:** 모든 웹 URL 필터 나열

   ![목록 URL 필터](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***예***

```powershell
 Get-CsImFilterConfiguration
```

---

> **시나리오 2:** 새 URL 필터 만들기

   ![새 URL 필터](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***예***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 3:** 선택한 URL 필터에 대한 세부 정보 확인

   ![URL 필터 다운로드](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***예***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 URL 필터 삭제

   ![URL 필터 삭제](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***예***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** URL 필터 업데이트

   ![URL 필터 업데이트](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***예***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
