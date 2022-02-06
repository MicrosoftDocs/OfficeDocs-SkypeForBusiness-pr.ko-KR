---
title: 모임 구성 설정 보기 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '요약: 이 문서에서 모임 구성 설정을 보는 비즈니스용 Skype 서버.'
---

# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>모임 구성 설정 보기 비즈니스용 Skype 서버
 
**요약:** 모임 구성 설정을 보기 위한 방법을 비즈니스용 Skype 서버.
  
모임 구성 설정은 제어판을 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모임 비즈니스용 Skype 서버 설정 보기
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의를 **클릭한** 다음 모임 구성 **을 클릭합니다**.
    
4. 모임 **구성 페이지에서** 보게 될 모임 구성을 클릭합니다.
    
5. 파일 **필터 편집에서** 자세한 정보 **표시 확인** 란을 선택합니다.
    
    **모임 구성 편집 - \<policy\>** 를 열면 선택한 정책에 대한 설정이 표시됩니다.
    
    설정을 구성하는 데 대한 자세한 내용은 [Create meeting configuration settings in 비즈니스용 Skype 서버](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모임 비즈니스용 Skype 서버 보기
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

전체 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsMeetingConfiguration을 참조하십시오](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
