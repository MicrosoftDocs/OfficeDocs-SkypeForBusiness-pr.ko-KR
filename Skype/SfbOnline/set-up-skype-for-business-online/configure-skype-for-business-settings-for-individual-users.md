---
title: 관리자 개별 사용자를 위한 비즈니스용 Skype 설정 구성
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '오디오 및 비디오 회의, 통화 및 모임 기록과 같은 개별 사용자에 대한 비즈니스용 Skype 설정을 변경하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093392"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>관리자: 개별 사용자에 대한 비즈니스용 Skype 설정 구성

> [!IMPORTANT]
> Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다. 이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다. Teams 관리 센터에서 [비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 글로벌 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다. 자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.

이 문서에서는 관리자가 소수의 사용자를 위해 비즈니스용 Skype를 구성하는 방법을 설명합니다. 이러한 단계를 일괄적으로 수행하기 위해 사용할 수 있는 Windows PowerShell cmdlet에 대한 링크가 포함되어 있습니다.
  
비즈니스의 모든 사용자가 외부 사용자와 통신할 수 있도록 허용하거나 차단하는 경우 다음을 참조합니다.
  
- [사용자가 외부](allow-users-to-contact-external-skype-for-business-users.md)비즈니스용 Skype 사용자에 문의하도록 허용: 조직에서 비즈니스용 고급 Skype 기능(데스크톱 공유, 온라인 사용자 검색 등)을 사용하여 신뢰할 수 있는 특정(페더리드) 비즈니스의 사용자와 통신하도록 허용할 수 있습니다. 또한 이 문서에서는 특정 도메인과의 통신을 차단하는 방법을 설명합니다.
    
- [비즈니스용 Skype 사용자가 Skype 연락처를 추가하게 합니다.](let-skype-for-business-users-add-skype-contacts.md) 조직에서 비즈니스용 Skype를 사용하여 무료 앱인 Skype를 사용하는 사용자 및 IM 사용자 검색을 할 수 있습니다.
    
## <a name="configure-general-settings-for-one-user"></a>한 사용자에 대한 일반 설정 구성
<a name="__toc325019204"> </a>

이러한 단계를 [수행하려면](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 관리자 권한이 있어야 합니다.

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**
  
1. 직장 또는 학교 계정으로 로그인합니다.
    
2. 비즈니스용   >  **Skype 센터를 선택하세요.**
    
3. 사용자를 **선택 합니다.**
    
    ![비즈니스용 Skype 관리 센터에서 사용자를 선택하세요.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 편집할 사용자를 선택해야 합니다.
    
5. 오른쪽 패널에서 편집을 **선택 합니다.**
    
    ![편집 아이콘을 선택 합니다.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 일반 **옵션** 페이지에서 변경하려는 기능 옆에 있는 확인란을 선택하거나 선택 취소한 다음 저장을 **선택합니다.**
    
|**옵션**|**세부 정보**|
|:-----|:-----|
|오디오 및 HD 비디오  <br/> |이 사용자가 오디오 모임, 오디오 및 비디오 모임을 녹화할 수 있도록 허용하거나 모임 예약을 허용하지 않습니다(없음).  <br/> |
|대화 및 모임 기록  <br/> |이 사용자가 기록할 수 있는 것을 선택해야 합니다.  <br/> 비즈니스용 Skype Basic에서 이 옵션을 사용할 수 없습니다.  <br/> |
|규정 준수를 위해 보관되지 않은 기능을 해제합니다.  <br/> | 전자적으로 저장된 정보를 보존하는 데 법적으로 필요한 경우 이 옵션을 선택합니다. <br/>  이 옵션을 선택하면 Exchange 관리 센터에 현재 보류가 [](/exchange/security-and-compliance/in-place-and-litigation-holds) 설정되어 있는 경우 캡처되지 않은 기능이 해제됩니다. 다음 기능을 해제합니다. <br/>  인스턴트 메시징을 사용하여 파일 전송 <br/>  공유 OneNote 페이지 <br/>  PowerPoint 주석 <br/> |
   
이러한 설정을 일괄적으로 구성하려면 PowerShell을 사용합니다. 에 [대한 컴퓨터 Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>외부 통신 차단
<a name="__toc325019206"> </a>

비즈니스용 Skype 사용자가 회사 내 모든 사용자에 대한 [Skype](let-skype-for-business-users-add-skype-contacts.md) 연락처를 추가하도록 설정한 후 다음 단계를 사용하여 특정 개인에 대한 외부 통신을 선택적으로 차단할 수 있습니다.
  
1. 사용자를 **선택하고** 비활성화할 사용자를 선택한 다음 편집 **을** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 선택합니다.
    
2. 외부 **통신을 선택한** 다음 적절한 옵션을 선택 취소합니다.
    
   - **비즈니스용 외부** Skype 사용자: 사용자가 페더리드 도메인에서 비즈니스용 Skype 사용자와 통신하지 못하도록 하려는 경우 이 상자를 선택 취소합니다.
    
   - **외부 Skype 사용자:** 사용자가 freeSkype 앱을 사용하는 사용자와 통신하지 못하도록 하려는 경우 이 상자를 선택 취소합니다.
    
3. **저장** 을 클릭합니다.
    
이러한 설정을 일괄적으로 구성하려면 PowerShell을 사용합니다. 에 [대한 컴퓨터 Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>한 사용자에 대한 오디오 회의 설정 편집
<a name="__toc314837483"> </a>

1. 사용자를 **선택하고** 편집할 오디오 회의 설정을 선택한 다음 편집을  ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 선택합니다.
    
2. 오디오 **회의를** 선택하고 오디오 회의 공급자를 선택하고, 요청된 정보를 입력하거나 변경한 다음 저장을 **클릭합니다.**
    
|**오디오 회의 설정**|**설명**|
|:-----|:-----|
|**공급자 이름** <br/> |목록에서 공급자를 선택합니다.  <br/> |
|**전화** 번호(필수) <br/> |타사 ACP의 경우 이러한 전화 번호는 오디오 회의 공급자에서 받은 전화 번호입니다. 사용자가 Microsoft를 오디오 회의 공급자로 사용하는 경우 오디오 회의 브리지에 설정된 숫자가 됩니다. 비즈니스용 Skype 및 Microsoft Teams 모임 요청에 표시하려는 숫자의 서식을 지정합니다.  <br/> |
|**무료 전화 번호** <br/> |타사 ACP의 경우 이러한 전화 번호는 오디오 회의 공급자에서 받은 전화 번호입니다. 사용자가 Microsoft를 오디오 회의 공급자로 사용하는 경우 오디오 회의 브리지에 설정된 숫자가 됩니다. 비즈니스용 Skype 및 Microsoft Teams 모임 요청에 표시하려는 숫자의 서식을 지정합니다.  <br/> |
|**회의 ID 및** PIN(필수) <br/> |이 사용자가 예약하고 타사 오디오 회의 공급자에서 제공하는 모임에 참가하는 데 사용되는 참가자 PIN 또는 컨퍼런스 코드입니다. 사용자가 Microsoft를 오디오 회의 공급자로 사용하는 경우 필요하지 않습니다.  <br/> |
   
이러한 설정을 일괄적으로 구성하려면 PowerShell을 사용합니다. 초대에 포함된 전화 번호 설정 [을](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>관련 항목 

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
