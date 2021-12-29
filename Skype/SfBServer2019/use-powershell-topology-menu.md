---
title: 토폴로지 메뉴의 작업에 PowerShell 사용
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
description: '요약: 비즈니스용 Skype 서버 메뉴에 대한 Cmdlet 매핑에 대한 제어판을 제공합니다.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626229"
---
# <a name="topology"></a>토폴로지

이 문서에서는 cmdlet을 사용하여  레거시 제어판의 토폴로지 메뉴 항목과 비슷한 결과를 얻을 수 있는 방법에 대해 설명합니다.

이 문서에서는 다음과 같은 하위 메뉴에 대해 설명합니다.

- [토폴로지](#topology)
  - [상태](#status)
  - [서버 응용 프로그램](#server-application)
  - [단순 URL](#simple-url)
  - [신뢰할 수 있는 응용 프로그램](#trusted-application)

## <a name="status"></a>상태

**STATUS** 하위 메뉴를 사용하면 관리자가 토폴로지의 컴퓨터를 관리할 수 있습니다.

사용자가 STATUS에 대해 수행할 수 있는 다양한 작업을 고려하고 이러한 작업을 매핑하는 비즈니스용 Skype 수 있습니다.

---

> **시나리오 1:** 모든 컴퓨터 및 해당 상태 나열

   ![컴퓨터 및 상태 목록](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***예***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***예***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***예***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>서버 응용 프로그램

서버 응용 프로그램은 서버 응용 프로그램에서 실행되는 개별 비즈니스용 Skype 서버. **SERVER APPLICATION** 하위 메뉴를 사용하면 관리자가 응용 프로그램의 일부로 실행되는 모든 응용 프로그램에 대한 정보를 반환할 수 비즈니스용 Skype 서버.

**사용자가 SERVER APPLICATION** 및 서버 응용 프로그램에서 수행할 수 있는 다양한 작업을 비즈니스용 Skype cmdlet에 매핑합니다.

---
> **시나리오 1:** 모든 서버 응용 프로그램 나열

   ![목록 서버 응용 프로그램](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***예***

```powershell
 Get-CsServerApplication
```

---

> **시나리오 2:** 중요/ 중요 서버 응용 프로그램 선택/사용 안 하도록 설정/사용 안 하도록 설정

   ![서버 응용 프로그램 편집](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***예***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>단순 URL

단순 URL을 사용하면 사용자가 모임 및 회의에 쉽게 참가할 수 있으며 관리자가 비즈니스용 Skype 서버 제어판에 쉽게 로그온할 수 있습니다. **단순 URL** 하위 메뉴를 사용하면 관리자가 해당 URL을 볼 수 있습니다.

사용자가 **SIMPLE URL에** 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 매핑할 수 있습니다.

---
> **시나리오 1:** 모든 단순 URL 구성 나열

   ![목록 단순 URL](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***예***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>신뢰할 수 있는 응용 프로그램

신뢰할 수 있는 응용 프로그램은 신뢰할 수 있는 상태가 제공된 타사에서 개발한 응용 프로그램으로 비즈니스용 Skype 서버 제품의 기본 제공 부분이 아닌 응용 프로그램입니다. 신뢰할 **수 있는 응용 프로그램** 하위 메뉴를 사용하면 관리자가 신뢰할 수 있는 응용 프로그램을 볼 수 있습니다.

사용자가 신뢰할 수 있는 응용 프로그램 및 해당 작업에 매핑되는 비즈니스용 Skype 여러 가지 작업을 고려해 보아야 합니다.

---
> **시나리오 1:** 모든 신뢰할 수 있는 응용 프로그램 나열

   ![신뢰할 수 있는 응용 프로그램 목록](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***예***

```powershell
 Get-CsTrustedApplication
```

---
