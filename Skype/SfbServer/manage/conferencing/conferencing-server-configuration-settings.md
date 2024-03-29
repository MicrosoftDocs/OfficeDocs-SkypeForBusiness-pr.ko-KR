---
title: 회의 서버 구성 설정 관리 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '요약: 각 서버에서 회의 서버 구성 설정을 관리하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 1435c6bd69624d5097d0377ab920ac9fed577072
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393780"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>회의 서버 구성 설정 관리 비즈니스용 Skype 서버
 
**요약:** 각 서버에서 회의 서버 구성 설정을 관리하는 비즈니스용 Skype 서버.
  
이 항목에서는 회의 구성 설정을 관리하는 방법에 대해 설명합니다. 회의를 계획하고 배포하는 방법에 대한 자세한 내용은 [Plan for conferencing in 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in 비즈니스용 Skype 서버](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
회의 구성 설정은 모임 콘텐츠 및 유인물에 허용되는 최대 크기와 같은 내용을 확인합니다. 응용 프로그램 공유 회의 서비스의 최대 대역폭 양 저장소 제한 및 만료 기간 지원되는 클라이언트의 내부 및 외부 다운로드 URL 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 URL에 대한 포인터 및 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용되는 포트 이러한 설정을 통해 실제 서버를 직접 관리할 수 있습니다. 이러한 설정은 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다.
  
설치 비즈니스용 Skype 서버 시스템에서는 단일 회의 구성 설정 컬렉션(전역 컬렉션)을 제공합니다. 사이트 또는 서비스의 사용자 지정 설정을 만들어야 하는 경우 **New-CsConferencingConfiguration** cmdlet을 사용하면 됩니다. 새 설정은 사이트 또는 서비스 범위에서만 적용할 수 있습니다. 새 전역 회의 구성 설정 컬렉션을 만들 수는 없지만 **Set-CsConferencingConfiguration** cmdlet을 사용하여 전역 컬렉션을 수정할 수 있습니다. 또한 사이트 또는 서비스는 설정 컬렉션을 두 개 이상 호스팅할 수 없습니다. Redmond 사이트에 대한 새 설정을 만들려고 하여 Redmond 사이트에 회의 구성 설정 컬렉션이 이미 호스트되어 있는 경우 명령이 실패합니다.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 회의 비즈니스용 Skype 서버 관리

비즈니스용 Skype 서버 관리 셸을 사용하여 회의 구성 설정을 관리하려면 다음 cmdlet을 사용합니다.
  
**회의 구성 설정**

|**Cmdlet**|**설명**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |조직의 회의 구성 설정에 대한 정보를 반환합니다.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |회의 구성 설정의 새 컬렉션을 만듭니다.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |지정한 회의 구성 설정 컬렉션을 제거합니다.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |전화 회의 구성 설정의 기존 컬렉션을 수정합니다.  <br/> |
   
다음 명령은 Redmond 사이트(site:Redmond)에 대한 새 회의 구성 설정 컬렉션을 만듭니다. 이 예에서는 Organization 속성의 값을 Litwareinc로 설정하는 데 사용되는 추가 매개 변수(Organization)가 포함되어 있습니다. 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

사이트당 이러한 컬렉션을 하나만 사용할 수 있으므로 Redmond 사이트에 이미 회의 구성 설정 컬렉션이 있는 경우 이 명령이 실패합니다. 
  
다음 예제에서는 처음에 메모리에 저장된 다음 나중에 Redmond 사이트에 적용되는 회의 구성 설정의 새 컬렉션을 정의합니다. 
  
첫 번째 명령은 **New-CsConferencingConfiguration** cmdlet을 사용하여 변수 변수에 저장된 새 메모리 내 설정 컬렉션을 $x. InMemory 매개 변수는 Redmond 사이트에 즉시 적용되는 것이 아니라 메모리에서 컬렉션을 만들어야 한다고 지정합니다.
  
컬렉션을 만든 후에는 두 번째 명령이 Organization 속성 값을 Litwareinc로 설정합니다. 
  
마지막으로 세 번째 명령은 **Set-CsConferencingConfiguration** cmdlet을 사용하여 Redmond 사이트에 새 설정을 실제로 적용합니다.
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

**Set-CsConferencingConfiguration** cmdlet을 호출하지 않는 경우 새 설정이 적용되지 않습니다. 대신 세션을 종료하거나 변수를 삭제하는 Windows PowerShell 즉시 $x.
