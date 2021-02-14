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
description: 이 문서에서는 비즈니스용 Skype Online 위임 설정 및 문제 해결 방법을 설명하고 있습니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010801"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>비즈니스용 Skype Online 위임을 설정하고 문제 해결

이 문서에서는 비즈니스용 Skype Online 위임 설정 및 문제 해결 방법을 설명하고 있습니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
  
## <a name="guidelines-and-requirements"></a>지침 및 요구 사항

### <a name="guidelines-for-delegation"></a>위임 지침

위임이 올바르게 작동하려면 다음 지침을 따릅니다.
  
- 최신 업데이트가 있는 비즈니스용 Skype 2015 전체 클라이언트 또는 비즈니스용 Skype 2016 전체 클라이언트를 사용하고 있어야 합니다.
    
- 최신 업데이트가 있는 Outlook 2013 클라이언트 또는 Outlook 2016 클라이언트를 사용하고 있어야 합니다.
    
- 위임자 및 대리인 컴퓨터에 기본 프로필 또는 기본 프로필인 Outlook 메일 프로필이 하나 있는지 확인 해당 메일 프로필에는 하나의 계정만 포함되어야 합니다.
    
- 위임자 및 대리인을 위한 비즈니스용 Skype는 온라인 사용자입니다. 또한 각 Exchange Server 사서함은 모두 온라인 또는 둘 다에 있어야 합니다.
    
- 위임자 및 대리인은 모두 동일한 주 버전의 Outlook을 사용 중입니다.
    
- 클라이언트 **정책에서 EnableExchangeDelegateSync** 특성 값을 **true로** 설정해야 합니다. 비즈니스용 Skype Online PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행하여 이 설정을 확인할 수 있습니다.
    
- 위임자 및 대리인은 모두 서로 다른 작업소에서 비즈니스용 Skype 및 Outlook에 동시에 로그인해야 합니다.
    
- 공유 사서함은 비즈니스용 Skype Online 위임에서 지원되지 않습니다. 공유 사서함에 보낸 사람 대신  ACL(액세스 제어 목록)이 있기 때문에입니다.
    
### <a name="skype-for-business-client-version-support"></a>비즈니스용 Skype 클라이언트 버전 지원

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/비즈니스용 Skype 기본 클라이언트**| 지원되지 않음 |지원되지 않음
|**비즈니스용 Skype 2015**|지원| 지원|
|**비즈니스용 Skype 2016**|지원| 지원|

   
### <a name="licensing-requirements"></a>라이선스 요구 사항

**Enterprise E3 라이선스 시나리오**

|**라이선스**|**클라이언트**|**참고**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016  <br/> |비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
|Office 365 Phone System + Office 365 xCalling 요금제가 있는 Enterprise E3  <br/> |Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
   
**Enterprise E5 라이선스 시나리오**

|**라이선스**|**클라이언트**|**참고**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016  <br/> |비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
|Enterprise E5 및 Office 365 통화 요금제  <br/> |비즈니스용 Skype for Mac 2016  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)  <br/> Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>위임 설정 및 확인

비즈니스용 Skype Online 위임 설정은 다음 단계를 수행합니다.
  
### <a name="for-windows-clients"></a>Windows 클라이언트의 경우

 **전달 탭**
  
1. 도구 **옵션**  >    >  **호출 전달 설정을 선택합니다.**
    
2. 내 **대리인 구성원 편집을 선택합니다.**
    
3. 추가를 **선택하고** 추가할 대리인을 선택한 다음 확인을 **선택합니다.**
    
 **전달 탭 없음**
  
1. Outlook에서 **파일** 계정  >  **설정** 대리인  >  **액세스**  >  **추가를 선택합니다.**
    
2. 대리인이 될 사람의 이름을 찾아 추가합니다.
    
3. 일정 **메뉴를** 선택한 다음 편집기(항목을 읽고 **만들고 수정할 수 있습니다)를 선택합니다.**
    
### <a name="for-mac-clients---lync"></a>Mac 클라이언트 - Lync

 **전달 탭**
  
- 클라이언트에 내 대리인 구성원  편집 링크가 있는  통화 전달 탭이 없는 경우 위임자가 Mac 컴퓨터에 있는 경우 위임자는 위임을 설정하기 위해 Windows 기반 컴퓨터에 로그인해야 합니다. Mac 클라이언트가 MAPI 연결을 설정할 수 없는 경우 Outlook에서 비즈니스용 Skype 위임이 설정될 수 있기 위한 요구 사항입니다.
    
### <a name="verify-success"></a>성공 확인

설정이 성공하면 대리인이 사용자  이름 < 메시지에 대한 대리인으로>그룹 통화를 관리하는  사람도 만들어졌다는 메시지가 표시됩니다. 위임자는 대리인 그룹이 **생성되는지** 볼 수 있습니다.
  
> [!NOTE]
> 위임 권한은 일반적으로 설정 프로세스 후 30분 이내에 표시됩니다. 그러나 이 프로세스를 완료하는 데 최대 24시간이 걸릴 수 있습니다. 
  
## <a name="troubleshooting"></a>문제 해결

### <a name="common-issues"></a>일반적인 문제

- > **문제 1** 위임자가 Outlook 클라이언트에서  대리인을 제거한 후에도 대리인 항목은 내가 통화를 관리하는 사람 그룹에 계속 표시됩니다.
    
  - > **해결 1** 비즈니스용 Skype 클라이언트에서 대리인 그룹의 대리인을  마우스 오른쪽 단추로 클릭한 다음 그룹에서 **제거를 선택합니다.**
    
- > **문제 2** Outlook 클라이언트를 통해 대리인 액세스 권한이 부여된 후  대리인에게는 확인 메시지와 내가 통화를 관리하는 사람이 나타나지 않습니다.
    
  - > **해결 2** Outlook 클라이언트에서 위임을 제거하고 복제를 위해 15분 정도 기다렸다가 대리인을 다시 추가합니다.
    
### <a name="other-common-issues"></a>기타 일반적인 문제

- 위임은 위임자 25명 및 대리인 25명 임계값을 초과하는 경우 작동하지 않습니다.
    
- 비즈니스용 Skype Basic 클라이언트는 지원되지 않습니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Basic 클라이언트를 설치하면 위임이 제거 및 중단됩니다. 
  
- **MAPI 상태 값이** 확인되지 않는 경우 **SIP** 및 **SMTP** 값이 일치하는지 확인 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype 및 Outlook을 처음 시작한 후 MAPI 상태가 OK로 표시될 때 몇 분 정도 걸릴 수 있습니다. 
  
- 보안 그룹 만들기 및 해당 보안 그룹에 대한 위임 권한 추가는 지원되지 않습니다.
    
- MAPI를 사용할 수 없습니다. 비즈니스용 [Skype 2016 클라이언트에서 "MAPI를](https://support.microsoft.com/help/3147130)사용할 수 없음" 오류를 참조하세요.
    
- Exchange Online 사서함은 비즈니스용 Skype 클라이언트를 통해 액세스할 수 없습니다. 이 경우 Outlook 연결 [테스트를 실행하여](https://testconnectivity.microsoft.com/) 통과하는지 확인 합니다.
    
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
