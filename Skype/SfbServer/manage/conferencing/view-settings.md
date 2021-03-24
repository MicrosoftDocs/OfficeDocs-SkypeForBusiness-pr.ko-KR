---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096704"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 보기
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법을 확인합니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 볼 수 있습니다.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 보기
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
4. 모임 **구성 페이지에서** 보게 될 모임 구성을 클릭합니다.
    
5. 파일 **필터 편집에서** 자세한 정보 **표시 확인란을** 선택합니다.
    
    **모임 구성 \<policy\> 편집 -** 를 열면 선택한 정책에 대한 설정이 표시됩니다.
    
    설정을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 모임 구성 설정 [만들기를 참조하세요.](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 보기
<a name="BKMK_ViewJoinSettings"> </a>

모든 모임 구성 설정에 대한 정보를 확인하려면 **Get-CsMeetingConfiguration** cmdlet을 사용합니다.
  
```
Get-CsMeetingConfiguration
```

이 명령은 다음과 같은 정보를 반환합니다.
  
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

전체 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
