---
title: 비즈니스용 Skype Online 위임을 설정하고 문제 해결
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 이 문서에서는 비즈니스용 Skype Online 위임을 설정 하 고 문제를 해결 하는 방법을 설명 합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대 한 지침을 제공 합니다.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010801"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>비즈니스용 Skype Online 위임을 설정하고 문제 해결

이 문서에서는 비즈니스용 Skype Online 위임을 설정 하 고 문제를 해결 하는 방법을 설명 합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대 한 지침을 제공 합니다.
  
## <a name="guidelines-and-requirements"></a>지침 및 요구 사항

### <a name="guidelines-for-delegation"></a>위임에 대 한 지침

위임을 올바르게 작동 하도록 설정 하는 방법은 다음 지침에 따라 달라 집니다.
  
- 최신 업데이트 또는 비즈니스용 Skype 2016 정식 클라이언트에는 비즈니스용 Skype 2015 정식 클라이언트를 사용 해야 합니다.
    
- 최신 업데이트 또는 Outlook 2016 클라이언트로 Outlook 2013 클라이언트를 사용 해야 합니다.
    
- 대리인 및 대리인 컴퓨터에 기본 프로필 또는 기본 프로필로 해당 하는 Outlook 메일 프로필이 하나 이상 있는지 확인 합니다. 해당 메일 프로필에는 하나의 계정만 포함 되어야 합니다.
    
- 대리인에 게 비즈니스용 Skype를 이용 하는 것은 온라인 사용자 여야 합니다. 또한 각 계정에 대 한 Exchange Server 사서함이 모두 온라인 또는 온-프레미스 중 하나 여야 합니다.
    
- 위임자와 대리인 모두 Outlook의 동일한 주요 버전을 사용 해야 합니다.
    
- 클라이언트 정책에서 **EnableExchangeDelegateSync** 특성 값을 **true** 로 설정 해야 합니다. 비즈니스용 Skype Online PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행 하 여이 설정을 확인할 수 있습니다.
    
- 위임자와 대리인 모두 다른 워크스테이션에서 동시에 비즈니스용 Skype 및 Outlook에 로그인 해야 합니다.
    
- 비즈니스용 Skype Online 위임용으로는 공유 사서함이 지원 되지 않습니다. 공유 사서함에 **sendonbehalf** ACL (액세스 제어 목록)이 없기 때문입니다.
    
### <a name="skype-for-business-client-version-support"></a>비즈니스용 Skype 클라이언트 버전 지원

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/비즈니스용 Skype Basic 클라이언트**| 지원되지 않음 |지원되지 않음
|**비즈니스용 Skype 2015**|지원| 지원|
|**비즈니스용 Skype 2016**|지원| 지원|

   
### <a name="licensing-requirements"></a>라이선스 요구 사항

**엔터프라이즈 E3 라이선스 시나리오**

|**동의**|**클라이언트**|**상속자**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016  <br/> |비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.  <br/> Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.  <br/> |
|Office 365 전화 시스템 + Office 365 xCalling 요금제를 사용 하는 Enterprise E3  <br/> |Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.  <br/> Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.  <br/> |
   
**Enterprise E5 라이선스 시나리오**

|**동의**|**클라이언트**|**상속자**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (비즈니스용 Skype 2015)가 Outlook 2013 또는 Outlook 2016와 함께 사용 됩니다.  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016  <br/> |비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.  <br/> Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.  <br/> |
|Enterprise E5 plus Office 365 통화 요금제  <br/> |Mac 용 비즈니스용 Skype 2016  <br/> Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.  <br/> Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>대리인 설정 및 확인

비즈니스용 Skype Online 위임을 설정 하려면 다음 단계를 따르세요.
  
### <a name="for-windows-clients"></a>Windows 클라이언트

 **착신 전환 탭**
  
1. **도구** > **** 옵션 > 착신**전환 설정을**선택 합니다.
    
2. **내 대리인 구성원 편집**을 선택 합니다.
    
3. **추가**를 선택 하 고 추가 하려는 대리인을 선택한 다음 **확인**을 선택 합니다.
    
 **착신 전환 탭 없음**
  
1. Outlook에서 **파일** > **계정 설정** > **대리인 액세스** > **추가**를 선택 합니다.
    
2. 대리인으로 지정할 사용자의 이름을 찾아 추가 합니다.
    
3. **달력** 메뉴를 선택한 다음 **편집자 (항목을 읽고, 만들고, 고칠 수 있음)** 를 선택 합니다.
    
### <a name="for-mac-clients---lync"></a>Mac 클라이언트의 경우-Lync

 **착신 전환 탭**
  
- 클라이언트가 **내 대리인 구성원 편집** 링크를 포함 하는 착신 **전환** 탭이 없고 대리인이 Mac 컴퓨터에 있는 경우 대리인은 위임을 설정 하기 위해 Windows 기반 컴퓨터에 로그인 해야 합니다. 이것은 Mac 클라이언트가 MAPI 연결을 할 수 없기 때문 이며, Outlook에서 비즈니스용 Skype 위임을 설정 하기 위한 요구 사항입니다.
    
### <a name="verify-success"></a>성공 확인

설정이 성공적으로 수행 되 면 대리인에 **게 < 이름>메시지에 대 한 대리인으로 추가 되었으며** 사용자가 관리 하는 사용자가 그룹 **을 대상** 으로 만들어졌는지도 확인 해야 합니다. 위임자는 **대리인** 그룹을 만들었는지 확인 해야 합니다.
  
> [!NOTE]
> 위임 권한은 일반적으로 설정 프로세스의 30 분 내에 표시 됩니다. 그러나이 프로세스를 완료 하는 데 최대 24 시간이 걸릴 수 있습니다. 
  
## <a name="troubleshooting"></a>해결사

### <a name="common-issues"></a>일반적인 문제

- > **문제 1** 대리인은 Outlook 클라이언트에서 대리인을 제거한 후 그룹 **에 대 한 통화를 관리** 하는 사용자에 게 계속 해 서 참가 항목을 표시 합니다.
    
  - > **해결 방법 1** 비즈니스용 Skype 클라이언트에서 **대리인** 그룹의 대리인을 마우스 오른쪽 단추로 클릭 한 다음 **그룹에서 제거**를 선택 합니다.
    
- > **문제 2** 대리인 액세스가 Outlook 클라이언트를 통해 부여 된 후에는 확인 메시지와 본인 **에 게 내가 관리 하는 사용자가** 대리인에 게 표시 되지 않습니다.
    
  - > **해결 방법 2** Outlook 클라이언트에서 위임을 제거 하 고 복제를 위해 15 분 정도 기다린 다음 대리인을 다시 추가 합니다.
    
### <a name="other-common-issues"></a>기타 일반적인 문제

- 25 delegators 및 25 명의 대리인 임계값을 초과 하는 경우 위임이 작동 하지 않습니다.
    
- 비즈니스용 Skype Basic 클라이언트는 지원 되지 않습니다.
    
    > [!NOTE]
    > 비즈니스용 Skype 기본 클라이언트를 설치 하는 경우 위임을 제거 하 고 끊습니다. 
  
- **MAPI 상태** 값이 **OK**가 아니면 **SIP** 와 **SMTP** 값이 일치 하는지 확인 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype 및 Outlook을 처음 시작한 후 MAPI 상태가 **OK** 로 표시 되는 데 몇 분 정도 걸릴 수 있습니다.
  
- 보안 그룹을 만들고 해당 보안 그룹에 대 한 위임 권한을 추가 하는 것은 지원 되지 않습니다.
    
- MAPI를 사용할 수 없습니다. [비즈니스용 Skype 2016 클라이언트에서 "MAPI를 사용할 수 없음" 오류를](https://support.microsoft.com/help/3147130)참조 하세요.
    
- 비즈니스용 Skype 클라이언트를 통해 Exchange Online 사서함에 액세스할 수 없습니다. 이런 경우 [Outlook 연결 테스트](https://testconnectivity.microsoft.com/) 를 실행 하 여 해당 메시지가 전달 되는지 확인 합니다.
    
## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
