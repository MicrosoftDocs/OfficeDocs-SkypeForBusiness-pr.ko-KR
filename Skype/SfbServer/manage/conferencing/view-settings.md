---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 보기
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법에 대해 알아보세요.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818459"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 보기
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법에 대해 알아보세요.
  
비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 볼 수 있습니다.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 보기
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.
    
4. **모임 구성** 페이지에서 보려는 모임 구성을 클릭 합니다.
    
5. **파일 편집 필터**에서 **세부 정보 표시** 확인란을 선택 합니다.
    
    **모임 구성 편집- \<정책이\> ** 열리고 선택한 정책에 대 한 설정이 표시 됩니다.
    
    설정을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 모임 구성 설정 만들기](create-settings.md)를 참조 하세요.
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 보기
<a name="BKMK_ViewJoinSettings"> </a>

모든 모임 구성 설정에 대 한 정보를 보려면 **Get-CsMeetingConfiguration** cmdlet을 사용 합니다.
  
```
Get-CsMeetingConfiguration
```

이 명령은 다음과 같은 정보를 반환 합니다.
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

전체 매개 변수 목록을 비롯 한 자세한 내용은 [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)을 참조 하세요.
  

