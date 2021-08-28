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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 이 문서에서는 온라인 위임의 설정 및 비즈니스용 Skype 방법을 설명합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
ms.openlocfilehash: c461b54bba68cf6570eae6a6b4dc18ab99a63b89
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587850"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>비즈니스용 Skype Online 위임을 설정하고 문제 해결

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 문서에서는 온라인 위임의 설정 및 비즈니스용 Skype 방법을 설명합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
  
## <a name="guidelines-and-requirements"></a>지침 및 요구 사항

### <a name="guidelines-for-delegation"></a>위임에 대한 지침

위임 설정 및 올바르게 작동하려면 다음 지침을 따릅니다.
  
- 최신 업데이트 또는 2016 전체 비즈니스용 Skype 2015 전체 클라이언트를 비즈니스용 Skype 있어야 합니다.
    
- 최신 업데이트 또는 Outlook 클라이언트에서 2013 클라이언트를 Outlook 2016 합니다.
    
- 위임자 및 위임 컴퓨터에 기본 또는 기본 프로필인 Outlook 하나의 메일 프로필이 있는지 확인하세요. 해당 메일 프로필에는 하나의 계정만 포함되어야 합니다.
    
- 비즈니스용 Skype 위임자에 대한 사용자 및 대리인은 Online 사용자입니다. 또한 각 계정에 Exchange Server 사서함은 Online이거나 둘 다온-프레미스일 수 있어야 합니다.
    
- 위임자 및 대리인은 모두 동일한 주 버전 Outlook.
    
- **EnableExchangeDelegateSync** 특성 값은 클라이언트 정책에서 **true로** 설정해야 합니다. 온라인 PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행하여 이 비즈니스용 Skype 확인할 수 있습니다.
    
- 위임자 및 대리인은 서로 다른 비즈니스용 Skype 동시에 Outlook 로그인해야 합니다.
    
- 공유 사서함은 온라인 위임에 비즈니스용 Skype 지원되지 않습니다. 공유 사서함에 **ACL(sendonbehalf 액세스** 제어 목록)이 없습니다.
    
### <a name="skype-for-business-client-version-support"></a>비즈니스용 Skype 버전 지원

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/비즈니스용 Skype 기본 클라이언트**| 지원되지 않음 |지원되지 않음
|**비즈니스용 Skype 2015**|지원되는| 지원되는|
|**비즈니스용 Skype 2016**|지원되는| 지원되는|

   
### <a name="licensing-requirements"></a>라이선스 요구 사항

**Enterprise E3 라이선스 시나리오**

|**라이선스**|**클라이언트**|**참고**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016  <br/> 비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016  <br/> |비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
|Enterprise xCalling Office 365 전화 시스템 + Office 365 E3  <br/> |2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016  <br/> 비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
   
**Enterprise E5 라이선스 시나리오**

|**라이선스**|**클라이언트**|**참고**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013(비즈니스용 Skype 2015)은 Outlook 2013 또는 Outlook 2016.  <br/> 비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016  <br/> |비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
|Enterprise E5 및 Office 365 요금제  <br/> |비즈니스용 Skype for Mac 2016  <br/> 2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016  <br/> 비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016  <br/> Mac용 Lync 2011  <br/> |비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.  <br/> Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>위임 설정 및 확인

온라인 위임 비즈니스용 Skype 설정하기 위해 다음 단계를 수행합니다.
  
### <a name="for-windows-clients"></a>Windows 클라이언트의 경우

 **통화 전달 탭**
  
1. 에서 **도구**  >  **옵션**  >  **호출 전달을 설정.**
    
2. 내 **대리인 멤버 편집을 선택합니다.**
    
3. **추가를** 선택하고 추가할 대리자를 선택한 다음 확인 **을 선택합니다.**
    
 **통화 전달 탭 없음**
  
1. Outlook **에서** 위임  >  **액세스 설정**  >  **파일 계정을**  >  **선택합니다.**
    
2. 를 찾아서 대리인이 될 사람의 이름을 추가합니다.
    
3. 일정 **메뉴를** 선택한 다음 **편집기(항목을 읽고, 만들고, 수정할 수 있습니다)를 선택합니다.**
    
### <a name="for-mac-clients---lync"></a>Mac 클라이언트의 경우 - Lync

 **통화 전달 탭**
  
- 클라이언트에 내 대리인 멤버  편집 링크가 있는  호출 전달 탭이 없는 경우 위임자가 Mac 컴퓨터에 있는 경우 위임자는 위임자를 Windows 설정하기 위해 Windows 컴퓨터에 로그인해야 합니다. Mac 클라이언트가 MAPI 연결을 만들 수 없는 것이기 때문에 이 비즈니스용 Skype 위임이 Outlook.
    
### <a name="verify-success"></a>성공 확인

설정이 성공하면 대리자는 사용자 이름 < 메시지에 **대한** 대리인으로>그룹에서 호출을  관리하는 사용자도 생성됩니다. 위임자는 대리인 그룹이 **생성되는지** 봐야 합니다.
  
> [!NOTE]
> 위임 권한은 일반적으로 설정 프로세스의 30분 이내에 표시됩니다. 그러나 이 프로세스를 완료하는 데 최대 24시간이 걸릴 수 있습니다. 
  
## <a name="troubleshooting"></a>문제 해결

### <a name="common-issues"></a>일반적인 문제

- > **문제 1** 위임자가 해당 클라이언트에서  대리인을 제거한 후에도 대리자 항목은 호출 관리 그룹에서 계속 Outlook 있습니다.
    
  - > **해결 1** 비즈니스용 Skype 클라이언트에서 대리인 그룹에서 대리인을 마우스  오른쪽 단추로 클릭한 다음 그룹에서 **제거를 선택합니다.**
    
- > **문제 2** 대리자 액세스가 Outlook 클라이언트를 통해 부여된 후 대리인에  대한 확인 메시지와 내가 호출을 관리하는 사람도 나타나지 않습니다.
    
  - > **해결 2** 클라이언트에서 위임 Outlook 복제를 위해 15분 정도 기다렸다가 대리인을 다시 추가합니다.
    
### <a name="other-common-issues"></a>기타 일반적인 문제

- 25개 위임자 및 25개 대리인의 임계값을 초과하면 위임이 작동하지 않습니다.
    
- 기본 비즈니스용 Skype 지원되지 않습니다.
    
    > [!NOTE]
    > 기본 클라이언트를 비즈니스용 Skype 위임이 제거됩니다. 
  
- **MAPI 상태 값이** 확인되지 않은 경우 **SIP** 및 **SMTP** 값이 일치해야 합니다.
    
    > [!NOTE]
    > 처음 시작한 후 MAPI 상태가 확인으로 표시되는 데 몇 분 정도 걸릴 비즈니스용 Skype Outlook. 
  
- 보안 그룹을 만들고 해당 보안 그룹에 대한 위임 권한을 추가하는 것은 지원되지 않습니다.
    
- MAPI를 사용할 수 없습니다. 2016 클라이언트에서 ["MAPI를 사용할 수 없음" 비즈니스용 Skype 를 참조합니다.](https://support.microsoft.com/help/3147130)
    
- Exchange Online 클라이언트를 통해 사서함에 액세스할 수 비즈니스용 Skype 없습니다. 이 경우 Outlook [](https://testconnectivity.microsoft.com/) 연결 테스트를 실행하여 통과하는지 확인합니다.
    
## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
