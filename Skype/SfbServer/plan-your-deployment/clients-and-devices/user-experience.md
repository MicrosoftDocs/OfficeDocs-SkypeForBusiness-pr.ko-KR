---
title: 사용자를 비즈니스용 Skype 2015 클라이언트 환경 계획
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '요약: 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019 비즈니스용 Skype, 비즈니스용 Skype 서버 2015, Lync Server 2013 또는 Lync Server 2010을 사용 중이든지 여부에 따라 새로운 비즈니스용 Skype 및 사용자와 업데이트 준비를 위해 취할 수 있는 단계에 대해 자세히 알아보십시오.'
ms.openlocfilehash: b9ead36cb38c41376c80a85f1356e24e78b51eb7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586870"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>사용자를 비즈니스용 Skype 2015 클라이언트 환경 계획
 
**요약:** 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015, Lync Server 2013 또는 Lync Server 2010을 사용 중이든지 여부에 따라 사용자 환경과 사용자를 업데이트 준비하기 위해 취할 수 있는 단계와 새로운 설정에 대해 자세히 알아보십시오. 비즈니스용 Skype
  
Lync 2013용 2015년 4월 14일 Office 업데이트에는 새로운 사용자 비즈니스용 Skype 포함되어 있습니다. 이 업데이트를 통해 관리자는 클라이언트의 모양과 느낌을 제어하고 Lync 2013 클라이언트 환경을 유지할지 또는 향상된 클라이언트 환경을 사용할지 비즈니스용 Skype 있습니다. 비즈니스용 Skype 클라이언트는 Lync 2013 클라이언트를 효과적으로 대체하고 관리자가 기존 Lync 클라이언트 환경과 새로운 비즈니스용 Skype 클라이언트 환경 간에 선택할 수 있는 기능을 추가했습니다. 이 업데이트에 대한 자세한 내용은 [Lync 2013용 2015년 4월 14일 업데이트(비즈니스용 Skype)(KB2889923)를 참조하세요.](https://support.microsoft.com/kb/2889923/)
  
2015년 5월 12일에는 업데이트된 클라이언트를 포함하는 Office 월별 업데이트가 비즈니스용 Skype 있습니다. 4월 업데이트를 적용하지 않은 많은 고객은 2013년 5월 12일 업데이트를 Office 있습니다. 이 항목의 정보는 클라이언트 업데이트를 위해 조직, 환경 및 사용자를 준비하는 데 도움이 됩니다. 사용자 및 지원 팀이 쉽게 전환할 수 있도록 이 항목의 정보를 사용하여 사용자에게 원하는 클라이언트 환경을 결정한 다음 조직에 클라이언트 업데이트를 배포하기 전에 환경을 변경하는 데 도움이 됩니다.
  
- [사용자에게 어떤 클라이언트 환경을 원하나요?](user-experience.md#clientexperience)
    
- [클라이언트를 위한 환경 비즈니스용 Skype 준비](user-experience.md#usinglync)
    
- [지원 팀과 최종 사용자가 업데이트를 준비하는 데 도움이 되는 리소스](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 클라이언트 환경은 2016 클라이언트 비즈니스용 Skype 옵션이 아닙니다. Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>사용자에게 어떤 클라이언트 환경을 원하나요?
<a name="clientexperience"> </a>

새 비즈니스용 Skype 클라이언트를 사용하면 Lync 또는 Lync 클라이언트와 같은 클라이언트 환경을 비즈니스용 Skype. 기본 클라이언트 환경은 온-프레미스 또는 온라인에서 Lync를 사용 비즈니스용 Skype 여부에 따라 결정됩니다. 현재 엔터프라이즈용 Microsoft 365 앱, Microsoft 365 Business Standard 또는 Office 2013에서 비즈니스용 Skype Online(Lync Online)을 사용하는 경우 Skype 디자인에서 영감을 받은 업데이트된 비즈니스용 Skype 클라이언트 환경이 기본 사용자 환경이 됩니다. 현재 온-프레미스에서 Lync Server를 사용하는 경우 Lync 클라이언트 환경이 기본값이 됩니다.
  
클라이언트 정책을 사용하여 사용자가 얻을 수 있는 클라이언트 환경을 구성할 수 있습니다. 클라이언트 정책은 사용자가 Lync 또는 Lync에 로그인할 때 적용되는 구성 설정 비즈니스용 Skype.
  
### <a name="skype-for-business-client-experience"></a>비즈니스용 Skype 환경

Lync의 모든 기능 외에도 비즈니스용 Skype 간단한 컨트롤과 친숙한 아이콘을 사용하여 새로운 기능을 Skype. 비즈니스용 Skype 일부 새 기능은 새로운 클라이언트 비즈니스용 Skype 사용할 수 있습니다. 비즈니스용 Skype 새로운 기능에 대한 자세한 내용은 [비즈니스용 Skype.](https://go.microsoft.com/fwlink/p/?LinkId=528686)
  
### <a name="lync-client-experience"></a>Lync 클라이언트 환경

Lync 클라이언트 환경은 사용자가 이미 익숙한 Lync 2013 클라이언트 환경과 매우 유사하지만 사용자에게 알려야 할 몇 가지 변경 사항이 있습니다. Lync 클라이언트 환경과 Lync 2013 클라이언트 간의 다른 기능을 자세한 내용은 [Lync를](https://go.microsoft.com/fwlink/p/?LinkId=544712) 사용할 때 비즈니스용 Skype 왜 표시합니까? 및 이 항목의 뒤부분에 있는 추가 링크를 참조하세요.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>클라이언트를 위한 환경 비즈니스용 Skype 준비
<a name="usinglync"> </a>

클라이언트 업데이트에 대한 환경을 준비하기 위해 몇 가지 작업을 해야 합니다. 클라이언트 환경을 구성하기 위해 변경을 시작하기 전에 먼저 클라이언트 정책 설정을 지원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용하고 있는지 확인합니다.
  
클라이언트 환경을 제어하기 위해 정책 설정을 지원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용하고 있는지 확인한 후 환경에서 정책 설정을 구성해야 합니다. 따라야 하는 특정 단계는 사용하는 비즈니스용 Skype 서버 또는 Lync Server 버전과 사용자가 온-프레미스인지 온라인인지에 따라 결정됩니다. 
  
클라이언트 업데이트가 사용자에게 전달되기 전에 이러한 변경을 적용하여 사용자가 클라이언트를 처음 시작할 때부터 클라이언트 환경을 제어할 비즈니스용 Skype 있습니다. 다음 표에서는 사용자에 대해 원하는 클라이언트 환경에 맞게 환경을 구성하기 위해 필요한 단계를 제공합니다.
  
|**배포**|**비즈니스용 Skype 환경**|**Lync 클라이언트 환경**|
|:-----|:-----|:-----|
|비즈니스용 Skype Online  <br/> |클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포하는 것 외의 추가 단계는 없습니다.  <br/> |[온라인에서 Lync 클라이언트 환경 비즈니스용 Skype 사용](user-experience.md#LyncwithSfBO) <br/> |
|Business Server 2015용 Skype  <br/> |클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포하는 것 외의 추가 단계는 없습니다.  <br/> |[온-프레미스에서 Lync 비즈니스용 Skype 서버 환경 사용](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 및 Lync Server 2010  <br/> |[Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용
<a name="SkypewithLynconprem"> </a>

프레미스 배포에서 Skype 클라이언트 환경을 구성하려는 경우 이 섹션의 단계를 따릅니다. On-premises의 기본 환경
  
 **1단계:** 먼저 클라이언트 정책 설정을 지원하는 Lync Server 버전을 실행하고 있는지 확인합니다.
  
- **Lync Server 2013** - Lync Server 2013 이상 업데이트에 대한 2014년 12월 누적 업데이트(5.0.8308.857)를 실행해야 합니다. 자세한 내용은 [Updates for Lync Server 2013을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
- **Lync Server 2010 - Lync Server 2010** 이상 업데이트에 대한 2015년 2월 누적 업데이트(4.0.7577.710)를 실행해야 합니다. 자세한 내용은 [Updates for Lync Server 2010을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
  **2단계:** 그런 다음 클라이언트 정책을 사용하여 Skype 클라이언트와의 비즈니스용 Skype 합니다. 클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다.
  
  **옵션 1:** 전역 Skype 사용하여 클라이언트 환경을 설정할 수 있습니다. 전역 정책은 배포의 모든 사용자에게 적용되지만 사용자 및 사이트 수준 정책은 전역 정책보다 우선합니다.
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **옵션 2:** 사용자 환경에서 사용하는 기존 클라이언트 정책을 수정하여 클라이언트 환경을 사용하도록 설정하는 Skype 수정합니다. 이렇게 하면 기존 정책이 Skype 사용자에게만 Skype 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **옵션 3:** 클라이언트 환경 설정이 포함된 사용자에게 할당할 새 정책을 Skype 합니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수 값으로 제공합니다.
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

그런 다음 **PolicyName** 매개 변수의 값으로 정책 **이름(Identity** 매개 변수에 사용한 값)을 사용하여 사용자에게 정책을 할당합니다.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **3단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용
<a name="LyncwithLynconprem"> </a>

이 환경은 온-프레미스 비즈니스용 Skype 배포 시 기본 환경입니다. Lync 클라이언트 환경을 사용하도록 클라이언트 정책을 구성할 필요는 없지만 클라이언트의 첫 번째 실행 동작을 제어해야 할 수 있습니다. 기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작하면 Skype 클라이언트 환경이 사용되고 Lync 클라이언트 환경을 얻기 위해 클라이언트를 다시 시작해야 하다는 알림이 표시됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시되고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정하여 클라이언트 자습서를 해제하도록 환경을 구성할 수 있습니다. 비즈니스용 Skype 배포하기 전에 수행해야 하는 단계에 대한 자세한 내용은 다음 항목 중 하나를 참조하십시오.
  
- **Lync Server 2013**, [Configure the client experience with 비즈니스용 Skype in Lync Server 2013을 참조하세요.](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010은** [Configure the client experience with 비즈니스용 Skype in Lync Server 2010을 참조하세요.](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>온-프레미스에서 Lync 비즈니스용 Skype 서버 환경 사용
<a name="LyncwithSfBServer"> </a>

온-프레미스 배포에서 Lync 클라이언트 환경을 구성하려는 경우 이 비즈니스용 Skype 서버 수행합니다.
  
프레미스 배포에서 Skype 클라이언트 환경을 구성하려는 경우 이 섹션의 단계를 따릅니다. On-premises의 기본 환경
  
 **1단계:** 먼저 배포 비즈니스용 Skype 서버.
  
 **2단계:** 그런 다음 클라이언트 정책을 사용하여 클라이언트 클라이언트에서 Lync 클라이언트 환경을 비즈니스용 Skype. 클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다.
  
 **옵션 1:** 전역 정책을 사용하여 Lync 클라이언트 환경을 설정할 수 있습니다. 전역 정책은 배포의 모든 사용자에게 적용되지만 사용자 및 사이트 수준 정책은 전역 정책보다 우선합니다.
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **옵션 2:** Lync 클라이언트 환경을 사용하도록 설정하는 설정을 포함하도록 환경에서 사용하는 기존 클라이언트 정책을 수정합니다. 이렇게 하면 기존 정책이 할당된 사용자에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **옵션 3:** Lync 클라이언트 환경 설정이 포함된 사용자에게 할당할 새 정책을 만들 수 있습니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수 값으로 제공합니다.
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

그런 다음 **PolicyName** 매개 변수의 값으로 정책 **이름(Identity** 매개 변수에 사용한 값)을 사용하여 사용자에게 정책을 할당합니다.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **3단계:** 선택 사항 - 기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작할 때 Skype 클라이언트 환경이 사용되고 Lync 클라이언트 환경을 얻게 하여 클라이언트를 다시 시작해야 하는 사용자에게 알림이 표시됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시되고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정하여 클라이언트 자습서를 해제하도록 환경을 구성할 수 있습니다. 비즈니스용 Skype 클라이언트를 배포하기 전에 수행해야 하는 단계는 [Configure the client experience with 비즈니스용 Skype.](../../deploy/deploy-clients/configure-the-client-experience.md)
  
 **4단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>온라인에서 Lync 클라이언트 환경 비즈니스용 Skype 사용
<a name="LyncwithSfBO"> </a>

Lync 클라이언트 환경을 구성하고 온라인에서 Lync 클라이언트 환경을 사용하려는 경우 이 비즈니스용 Skype 수행합니다.
  
비즈니스용 Skype Online을 사용하는 경우 원격 PowerShell을 사용하여 클라이언트 정책을 구성하여 조직의 비즈니스용 Skype 클라이언트와 Lync 클라이언트 환경을 계속 사용할 수 있습니다. 클라이언트 정책을 **사용하여** 클라이언트 환경을 설정하는 세 가지 옵션이 있습니다. 정책 및 매개 변수 이름은 온-프레미스 또는 Lync Server를 사용할 때 클라이언트 환경을 구성하는 데 비즈니스용 Skype 설정과 다릅니다.
  
 **옵션 1:** 전역 정책을 사용하여 Lync 클라이언트 환경을 설정할 수 있습니다. 사용자에게 적용된 클라이언트 및 사이트 정책은 전역 정책보다 우선합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 2:** Lync 클라이언트 환경을 사용하도록 설정하는 설정을 포함하도록 환경에서 사용하는 기존 클라이언트 정책을 수정합니다. 이렇게 하면 기존 정책이 할당된 사용자에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 3:** Lync 클라이언트 환경의 설정을 포함하는 사용자 지정 정책 인스턴스를 사용하세요.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트 빌드 4711.1002(2015년 4월) 이상을 배포합니다.
  
비즈니스용 Skype Online에서 클라이언트 환경을 구성하는 방법에 대한 자세한 내용과 첫 실행 환경을 제어하는 방법 및 환경을 구성하는 데 사용할 수 있는 PowerShell 스크립트에 대한 자세한 내용은 비즈니스용 Skype 및 [Lync](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)클라이언트 사용자 인터페이스 간 전환을 참조하세요.
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>지원 팀과 최종 사용자가 업데이트를 준비하는 데 도움이 되는 리소스
<a name="support"> </a>

사용자와 조직이 보다 쉽게 전환을 준비할 수 있도록 최종 사용자를 계획, 교육 및 참여하는 데 도움이 되는 많은 추가 리소스가 있습니다.
  
- [비디오: 비즈니스용 Skype 소개](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [비즈니스용 Skype 빠른 시작 가이드(다운로드)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [이제 Lync가 비즈니스용 Skype 새로운 기능을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [비즈니스용 Skype: 새 사용자를 위한 단계별 가이드](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync를 비즈니스용 Skype 때 이 보기가 표시되는 이유는 무엇입니까?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
