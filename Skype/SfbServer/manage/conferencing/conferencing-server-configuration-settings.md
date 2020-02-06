---
title: 비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '요약: 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818639"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 서버 구성 설정 관리
 
**요약:** 비즈니스용 Skype 서버에서 회의 서버 구성 설정을 관리 하는 방법에 대해 알아봅니다.
  
이 항목에서는 회의 구성 설정을 관리 하는 방법에 대해 설명 합니다. 회의를 계획 하 고 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md) 및 비즈니스용 [skype 서버에서 회의 배포](../../deploy/deploy-conferencing/deploy-conferencing.md)를 참조 하세요.
  
회의 구성 설정에서는 모임 콘텐츠 및 유인물에 허용 되는 최대 크기와 같은 항목을 결정 합니다. 응용 프로그램 공유 회의 서비스에 대 한 최대 대역폭 양 저장소 용량 한도 및 만료 기간 지원 되는 클라이언트의 내부 및 외부 다운로드에 대 한 Url입니다. 사용자가 회의 도움말 및 리소스를 얻을 수 있는 내부 및 외부 Url에 대 한 포인터 응용 프로그램 공유, 클라이언트 오디오, 파일 전송 및 미디어 트래픽에 사용 되는 포트. 이러한 설정을 통해 실제 서버 자체를 관리할 수 있습니다. 이 설정은 비즈니스용 Skype 서버 관리 셸을 사용 하 여 설정할 수 있습니다.
  
비즈니스용 Skype 서버를 설치 하면 시스템에서 하나의 회의 구성 설정 (전역 컬렉션) 모음을 제공 합니다. 사이트 또는 서비스에 대 한 사용자 지정 설정을 만들어야 하는 경우 **CsConferencingConfiguration** cmdlet을 사용 하 여 설정할 수 있습니다. 새 설정은 사이트 또는 서비스 범위에만 적용할 수 있습니다. 새 회의 구성 설정 집합을 만들 수는 없지만 **CsConferencingConfiguration** cmdlet을 사용 하 여 전역 컬렉션을 수정할 수 있습니다. 또한 사이트 또는 서비스는 둘 이상의 설정 모음을 호스트할 수 없습니다. Redmond 사이트에 대 한 새 설정을 만들려고 할 때 레드먼드 사이트가 이미 회의 구성 설정 모음을 호스트 하는 경우에는 명령이 실패 합니다.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 회의 구성 설정 관리

비즈니스용 Skype Server Management Shell을 사용 하 여 회의 구성 설정을 관리 하려면 다음 cmdlet을 사용 합니다.
  
**회의 구성 설정**

|**은**|**설명**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |조직의 회의 구성 설정에 대 한 정보를 반환 합니다.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |새 회의 구성 설정 모음을 만듭니다.  <br/> |
|[제거-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |지정 된 회의 구성 설정 모음을 제거 합니다.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |기존 회의 구성 설정 컬렉션을 수정 합니다.  <br/> |
   
다음 명령은 Redmond 사이트 (사이트: Redmond)에 대 한 새 회의 구성 설정 모음을 만듭니다. 이 예제에서는 조직 속성의 값을 Litwareinc로 설정 하는 데 사용 되는 추가 매개 변수 하나 (조직)가 포함 되어 있습니다. 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

사이트 마다 이러한 컬렉션을 하나만 가질 수 있으므로 Redmond 사이트에 이미 회의 구성 설정 모음이 있는 경우에는이 명령이 실패 합니다. 
  
다음 예에서는 처음에 메모리에 저장 된 다음 나중에 Redmond 사이트에 적용 되는 회의 구성 설정의 새 컬렉션을 정의 합니다. 
  
첫 번째 명령은 **CsConferencingConfiguration** cmdlet을 사용 하 여 변수 $x에 저장 된 새 설정의 메모리 내 컬렉션을 만듭니다. InMemory 매개 변수는 컬렉션이 Redmond 사이트에 즉시 적용 되지 않고 메모리에 만들어지도록 지정 합니다.
  
컬렉션을 만든 후 두 번째 명령은 조직 속성의 값을 Litwareinc로 설정 합니다. 
  
마지막으로 세 번째 명령은 **CsConferencingConfiguration** cmdlet을 사용 하 여 새 설정을 Redmond 사이트에 실제로 적용 합니다.
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

**Set-CsConferencingConfiguration** cmdlet을 호출 하지 않으면 새 설정이 적용 되지 않습니다. 대신 Windows PowerShell 세션을 종료 하거나 변수 $x 삭제 하는 즉시 사라집니다.
  

