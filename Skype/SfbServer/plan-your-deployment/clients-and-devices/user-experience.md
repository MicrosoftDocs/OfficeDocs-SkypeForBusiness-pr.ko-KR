---
title: 사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '요약: 비즈니스용 skype에 대 한 새로운 비즈니스 및 사용자가 온라인으로 Skype를 사용 하 고 있는지 여부, 비즈니스용 skype 서버 2019, 비즈니스용 Skype 서버 2015, lync server 2013 또는 Lync Server 2010에 대 한 업데이트를 준비 하기 위해 수행 해야 하는 단계와 환경에 대해 알아봅니다.'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777753"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>사용자를 위한 비즈니스용 Skype 2015 클라이언트 환경 계획
 
**요약:** 비즈니스용 skype에 대 한 새로운 비즈니스 및 사용자가 온라인으로 Skype를 사용 하 고 있는지 여부, 비즈니스용 skype 서버 2019, 비즈니스용 Skype 서버 2013 2015, lync server 2010 등의 작업을 준비 하기 위해 수행할 수 있는 단계와 환경에 대해 알아봅니다.
  
Lync 2013의 4 월 14th, 2015 Office 업데이트에는 새로운 비즈니스용 Skype 사용자 인터페이스가 포함 되어 있습니다. 관리자는이 업데이트를 사용 하 여 클라이언트의 디자인을 제어 하 고 Lync 2013 클라이언트 환경을 유지할지 또는 향상 된 비즈니스용 Skype 클라이언트 환경을 사용할지를 선택할 수 있습니다. 비즈니스용 Skype 클라이언트는 Lync 2013 클라이언트를 효과적으로 교체 했으며 관리자가 기존 Lync 클라이언트 환경 및 새로운 비즈니스용 Skype 클라이언트 환경 중에서 선택할 수 있는 기능을 추가 했습니다. 이 업데이트에 대 한 자세한 내용은 [4 월 14 일 2015 업데이트 For Lync 2013 (비즈니스용 Skype) (KB2889923)](https://support.microsoft.com/kb/2889923/)을 참조 하십시오.
  
5 월 12 일 2015 업데이트 된 비즈니스용 Skype 클라이언트를 포함 하는 또 다른 월별 업데이트가 Office에서 제공 됩니다. 4 월 업데이트를 적용 하지 않은 대부분의 고객은 Office 2013의 12 월 업데이트를 선택 합니다. 이 항목의 정보는 조직, 환경 및 사용자가 클라이언트 업데이트를 준비 하는 데 도움이 됩니다. 사용자 및 지원 팀이 쉽게 전환할 수 있도록 하려면이 항목의 정보를 참조 하 여 조직에서 클라이언트 업데이트를 배포 하기 전에 사용자에 게 적용할 클라이언트 환경을 결정 하 고 환경을 변경 해야 합니다.
  
- [사용자에 게 필요한 클라이언트 환경](user-experience.md#clientexperience)
    
- [비즈니스용 Skype 클라이언트에 대 한 환경 준비](user-experience.md#usinglync)
    
- [업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다. 클라이언트 환경에서 Lync 2013 클라이언트를 사용 하도록 구성 하기 전에 클라이언트 버전에서 번호 16으로 시작 하지 않는지 확인 하십시오. 예: x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>사용자에 게 필요한 클라이언트 환경
<a name="clientexperience"> </a>

새로운 비즈니스용 Skype 클라이언트를 사용 하 여 Lync 또는 비즈니스용 Skype 중에서 사용자에 게 제공 되는 클라이언트 환경을 제어할 수 있습니다. 기본 클라이언트 환경은 Lync 또는 비즈니스용 Skype 온-프레미스를 사용 중인지, 아니면 온라인 상태에 있는지에 따라 달라 집니다. 비즈니스용 Skype Online (Lync Online)을 사용 하는 경우 microsoft 365 Apps for enterprise (Microsoft 365 Business Standard 또는 Office 2013)를 사용할 경우 업데이트 된 비즈니스용 Skype 클라이언트 환경 (Skype의 모양과 느낌에 따라)이 기본 사용자 환경이 됩니다. 현재 Lync Server 온-프레미스를 사용 하는 경우 Lync 클라이언트 환경이 기본이 됩니다.
  
클라이언트 정책을 사용 하 여 사용자에 게 제공 되는 클라이언트 환경을 구성할 수 있습니다. 클라이언트 정책은 Lync 또는 비즈니스용 Skype에 로그인 할 때 사용자에 게 적용 되는 구성 설정 집합입니다.
  
### <a name="skype-for-business-client-experience"></a>비즈니스용 Skype 클라이언트 환경

Lync의 모든 기능 외에도 비즈니스용 Skype에서는 간소화 된 컨트롤 및 Skype의 익숙한 아이콘을 포함 하는 새로운 기능을 제공 합니다. 비즈니스용 Skype의 몇 가지 새로운 기능은 새로운 비즈니스용 Skype 클라이언트 환경 에서만 사용할 수 있습니다. 비즈니스용 Skype의 새로운 기능에 대 한 자세한 내용은 [비즈니스용 Skype 검색](https://go.microsoft.com/fwlink/p/?LinkId=528686)을 참조 하세요.
  
### <a name="lync-client-experience"></a>Lync 클라이언트 환경

Lync 클라이언트 환경은 사용자가 이미 익숙한 Lync 2013 클라이언트 환경과 매우 유사 하지만 사용자에 게 알리기 위해 몇 가지 사항을 변경 해야 합니다. Lync 클라이언트 환경과 Lync 2013 클라이언트의 차이점을 확인 하려면 [왜 lync 사용 중 비즈니스용 Skype가 표시 되는 이유는 무엇 인가요?](https://go.microsoft.com/fwlink/p/?LinkId=544712) 그리고이 항목의 뒷부분에 나오는 추가 링크를 참조 하세요.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>비즈니스용 Skype 클라이언트에 대 한 환경 준비
<a name="usinglync"> </a>

환경에서 클라이언트 업데이트를 준비 하려면 몇 가지 작업을 수행 해야 합니다. 클라이언트 환경 구성에 대 한 변경 작업을 시작 하기 전에 먼저 클라이언트 정책 설정을 지 원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용 하 고 있는지 확인 해야 합니다.
  
클라이언트 환경을 제어 하기 위해 정책 설정을 지 원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용 하 고 있는지 확인 한 후에는 해당 환경에서 정책 설정을 구성 해야 합니다. 수행 해야 하는 구체적인 단계는 사용 중인 비즈니스용 Skype 서버 또는 Lync Server의 버전과 사용자가 온-프레미스 또는 온라인 인지에 따라 달라 집니다. 
  
클라이언트 환경을 사용자에 게 제공 하기 전에 이러한 변경 작업을 수행 하 여 먼저 비즈니스용 Skype 클라이언트를 시작할 때부터 클라이언트 환경을 제어할 수 있습니다. 다음 표에서는 사용자를 위해 원하는 클라이언트 환경에 맞게 환경을 구성 하기 위해 수행 해야 하는 단계를 안내 합니다.
  
|**배포**|**비즈니스용 Skype 클라이언트 환경**|**Lync 클라이언트 환경**|
|:-----|:-----|:-----|
|비즈니스용 Skype Online  <br/> |클라이언트 빌드 4711.1002 (4 월, 2015) 이상을 배포 하는 것 외에는 추가 단계가 수행 되지 않습니다.  <br/> |[비즈니스용 Skype 온라인에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithSfBO) <br/> |
|비즈니스용 Skype 서버 2015  <br/> |클라이언트 빌드 4711.1002 (4 월, 2015) 이상을 배포 하는 것 외에는 추가 단계가 수행 되지 않습니다.  <br/> |[Lync 클라이언트 환경 사용 (비즈니스용 Skype 서버에서 온-프레미스)](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 및 Lync Server 2010  <br/> |[Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경 사용
<a name="SkypewithLynconprem"> </a>

온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다. 온-프레미스의 기본 환경
  
 **1 단계:** 먼저 클라이언트 정책 설정을 지 원하는 Lync Server 버전을 실행 중인지 확인 합니다.
  
- **Lync server 2013** -lync server 2013 이상 업데이트의 경우 12 월 2014 5.0.8308.857 (누적 업데이트)를 실행 해야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532772)를 참조 하세요.
    
- **Lync server 2010** -lync server 2010 이상 업데이트에 대해 2 월 2015 4.0.7577.710 (누적 업데이트)를 실행 해야 합니다. 자세한 내용은 [Lync Server 2010에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532771)를 참조 하세요.
    
  **2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트에서 Skype 클라이언트 환경을 설정 합니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다.
  
  **옵션 1:** 글로벌 정책을 사용 하 여 Skype 클라이언트 환경을 설정 합니다. 전역 정책은 배포의 모든 사용자에 게 적용 되지만, 사용자 및 사이트 수준 정책은 글로벌 정책 보다 우선 합니다.
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Skype 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다. 이렇게 하면 기존 정책이 할당 된 사용자 에게만 Skype 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **옵션 3:** Skype 클라이언트 환경에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수의 값으로 제공 합니다.
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

그런 다음 정책 이름 ( **Identity** 매개 변수에 사용 된 값)을 사용 하 여 **PolicyName** 매개 변수의 값으로 정책을 사용자에 게 할당 합니다.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **3 단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용
<a name="LyncwithLynconprem"> </a>

이는 비즈니스용 Skype 클라이언트를 온-프레미스 Lync Server 배포에 배포할 때 기본으로 사용 되는 환경입니다. Lync 클라이언트 환경을 사용 하기 위해 클라이언트 정책을 구성할 필요는 없지만 클라이언트에 대 한 첫 번째 실행 동작을 제어할 수도 있습니다. 기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하면 Skype 클라이언트 환경이 사용 되며, 사용자에 게 클라이언트를 다시 시작 하 여 Lync 클라이언트 환경을 가져오기 위해 요청 하는 알림이 표시 됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 하 고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 끌 수 있도록 환경을 구성 해야 합니다. 비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계는 다음 항목 중 하나를 참조 하십시오.
  
- **Lync server 2013**에 [대 한 자세한 내용은 lync Server 2013에서 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성](https://go.microsoft.com/fwlink/p/?LinkId=532732) 를 참조 하세요.
    
- **Lync server 2010** [lync Server 2010에서 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성](https://go.microsoft.com/fwlink/p/?LinkId=532733) 참조
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Lync 클라이언트 환경 사용 (비즈니스용 Skype 서버에서 온-프레미스)
<a name="LyncwithSfBServer"> </a>

온-프레미스 비즈니스용 Skype 서버 배포에서 Lync 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다.
  
온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 수행 합니다. 온-프레미스의 기본 환경
  
 **1 단계:** 먼저 비즈니스용 Skype 서버를 배포 합니다.
  
 **2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트와의 Lync 클라이언트 환경을 설정 합니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다.
  
 **옵션 1:** 글로벌 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다. 전역 정책은 배포의 모든 사용자에 게 적용 되지만, 사용자 및 사이트 수준 정책은 글로벌 정책 보다 우선 합니다.
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다. 이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **Identity** 매개 변수의 값으로 제공 합니다.
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

그런 다음 정책 이름 ( **Identity** 매개 변수에 사용 된 값)을 사용 하 여 **PolicyName** 매개 변수의 값으로 정책을 사용자에 게 할당 합니다.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **3 단계: 선택 사항** -기본적으로 사용자가 비즈니스용 skype 클라이언트를 처음 시작 하면 skype 클라이언트 환경이 사용 되며, 사용자에 게 클라이언트를 다시 시작 하 여 Lync 클라이언트 환경을 확인 하 라는 알림이 표시 됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 하 고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 해제할 수 있도록 환경을 구성 해야 합니다. 비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계에 대해서 [는 비즈니스용 skype를 사용 하 여 클라이언트 환경 구성을](../../deploy/deploy-clients/configure-the-client-experience.md)참조 하세요.
  
 **4 단계:** 클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>비즈니스용 Skype 온라인에서 Lync 클라이언트 환경 사용
<a name="LyncwithSfBO"> </a>

Lync 클라이언트 환경을 구성 하 고 비즈니스용 Skype 온라인을 사용 하려면이 섹션의 단계를 수행 합니다.
  
비즈니스용 Skype Online을 사용 하는 경우에도 원격 PowerShell을 사용 하 여 클라이언트 정책을 구성 하 여 조직의 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 사용할 수 있습니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하기 위한 옵션에는 **3** 가지가 있습니다. 정책과 매개 변수 이름은 비즈니스용 Skype 또는 Lync Server 온-프레미스를 사용 하는 경우 클라이언트 환경을 구성 하는 데 사용 하는 설정과는 다릅니다.
  
 **옵션 1:** 글로벌 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다. 사용자에 게 적용 되는 클라이언트 및 사이트 정책은 전역 정책 보다 우선 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 사용 하도록 설정할 수 있는 설정을 포함 합니다. 이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자 지정 정책 인스턴스를 사용 합니다.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

클라이언트 정책을 구성한 후 비즈니스용 Skype 클라이언트를 배포 하 고 빌드 4711.1002 (4 월, 2015) 이상을 구축 합니다.
  
환경을 구성 하는 데 사용할 수 있는 첫 번째 실행 환경 및 PowerShell 스크립트를 제어 하는 방법에 대 한 단계를 비롯 하 여 비즈니스용 Skype Online에서 클라이언트 환경을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 skype 및 Lync 클라이언트 사용자 인터페이스 간 전환](https://aka.ms/SfBOUI)를 참조 하세요.
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스
<a name="support"> </a>

사용자와 조직에서 전환을 쉽게 준비할 수 있도록 하기 위해 최종 사용자에 게 계획, 교육 및 참여 하는 데 도움이 되는 추가 리소스가 많이 제공 됩니다.
  
- [비디오: 비즈니스용 Skype 소개](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [비즈니스용 Skype 빠른 시작 가이드 (다운로드)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync now 비즈니스용 Skype-새로운 기능 참조](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [비즈니스용 Skype: 새 사용자를 위한 단계별 가이드](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync를 사용 하는 경우 비즈니스용 Skype가 표시 되는 이유는 무엇 인가요?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

