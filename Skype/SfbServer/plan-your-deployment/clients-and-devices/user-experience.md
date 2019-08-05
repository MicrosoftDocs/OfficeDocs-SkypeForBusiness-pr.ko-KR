---
title: 사용자의 비즈니스용 Skype 2015 클라이언트 환경 계획
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '요약: 비즈니스용 Skype에 대해 알아보고, 업데이트를 위해 Skype for business Online, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015, Lync Server 2013을 준비 하기 위해 수행할 수 있는 단계 및 사용자의 환경에 대 한 새로운 정보 Lync 서버 2010.'
ms.openlocfilehash: d5224c628624d6d93d8b3a06cd4c59d246523b1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187872"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>사용자의 비즈니스용 Skype 2015 클라이언트 환경 계획
 
**요약:** Skype for business Online, 비즈니스용 skype 서버 2019, 비즈니스용 skype 서버 2015, Lync server 2013 또는 Lync Server에 대 한 새로운 비즈니스용 Skype 및 업데이트를 위해 수행할 수 있는 단계에 대해 알아보세요. 2010.
  
4 월 14th, Lync 2013의 2015 Office 업데이트에는 새로운 비즈니스용 Skype 사용자 인터페이스가 포함 되어 있습니다. 이 업데이트는 관리자가 클라이언트의 디자인을 제어 하 고 Lync 2013 클라이언트 환경을 유지할지 또는 향상 된 비즈니스용 Skype 클라이언트 환경을 사용할지 여부를 선택할 수 있도록 합니다. 비즈니스용 Skype 클라이언트는 Lync 2013 클라이언트를 효과적으로 대체 하 고 관리자가 기존 Lync 클라이언트 환경 및 새로운 비즈니스용 Skype 클라이언트 환경을 선택할 수 있는 기능을 추가 했습니다. 이 업데이트에 대 한 자세한 내용은 [4 월 14 일 Lync 2013 (비즈니스용 Skype) 용 2015 업데이트 (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)를 참조 하세요.
  
2015 년 5 월 12 일에 업데이트 된 비즈니스용 Skype 클라이언트를 포함 하는 다른 월간 업데이트가 Office에서 제공 됩니다. 4 월 업데이트를 적용 하지 않은 대부분의 고객은 Office 2013의 12 월 업데이트를 선택 합니다. 이 항목의 정보는 조직, 사용자 환경 및 클라이언트 업데이트에 대 한 사용자를 준비 하는 데 도움이 됩니다. 사용자 및 지원 팀에서 쉽게 전환할 수 있도록 하려면이 항목의 정보를 사용 하 여 사용자에 게 제공할 클라이언트 환경을 결정 하 고 조직의 클라이언트 업데이트를 배포 하기 전에 환경을 변경 해야 합니다.
  
- [사용자에 게 어떤 클라이언트 환경을 사용할 수 있나요?](user-experience.md#clientexperience)
    
- [비즈니스용 Skype 클라이언트에 대 한 환경 준비](user-experience.md#usinglync)
    
- [업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다. Lync 2013 클라이언트를 사용 하도록 클라이언트 환경을 구성 하기 전에 클라이언트 버전을 확인 하 여 숫자 16으로 시작 되지 않는지 확인 하세요. 예: x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>사용자에 게 어떤 클라이언트 환경을 사용할 수 있나요?
<a name="clientexperience"> </a>

새로운 비즈니스용 Skype 클라이언트를 사용 하 여 사용자에 게 제공 되는 클라이언트 환경, Lync 또는 비즈니스용 Skype 중 어느 것을 제어할 수 있습니다. 기본 클라이언트 환경은 Lync 또는 비즈니스용 Skype for 온 (온-프레미스 또는 온라인)을 사용 하 고 있는지 여부에 따라 달라 집니다. Skype Online (Lync Online)을 Office 365 ProPlus, office 365 Business Premium 또는 Office 2013과 함께 사용 하는 경우 Skype의 모양과 느낌으로 인 한 업데이트 된 비즈니스용 Skype 클라이언트 환경을 기본 사용자 환경 이라고 할 수 있습니다. 지금 Lync Server 온-프레미스를 사용 하는 경우 Lync 클라이언트 환경이 기본값이 됩니다.
  
사용자가 클라이언트 정책을 사용 하 여 가져오는 클라이언트 환경을 구성할 수 있습니다. 클라이언트 정책은 Lync 또는 비즈니스용 Skype에 로그인 할 때 사용자에 게 적용 되는 구성 설정 집합입니다.
  
### <a name="skype-for-business-client-experience"></a>비즈니스용 Skype 클라이언트 환경

비즈니스용 Skype는 Lync의 모든 기능 외에도 간단한 컨트롤과 Skype의 친숙 한 아이콘과 함께 새로운 기능을 제공 합니다. 비즈니스용 Skype의 몇 가지 새로운 기능은 새로운 비즈니스용 Skype 클라이언트 환경 에서만 사용할 수 있습니다. 비즈니스용 Skype의 새로운 기능에 대해 자세히 알아보려면 비즈니스용 [Skype 검색](https://go.microsoft.com/fwlink/p/?LinkId=528686)을 참조 하세요.
  
### <a name="lync-client-experience"></a>Lync 클라이언트 환경

Lync 클라이언트 환경은 사용자가 이미 익숙한 Lync 2013 클라이언트 환경과 매우 유사 하지만 사용자에 게 알 수 있는 몇 가지 변경 사항이 있습니다. Lync 클라이언트 환경과 Lync 2013 클라이언트의 차이점을 확인 하려면 [lync를 사용할 때 비즈니스용 Skype가 표시 되는 이유](https://go.microsoft.com/fwlink/p/?LinkId=544712) 및이 항목의 뒷부분에 나오는 추가 링크를 참조 하세요.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>비즈니스용 Skype 클라이언트에 대 한 환경 준비
<a name="usinglync"> </a>

환경을 클라이언트 업데이트에 사용할 수 있도록 하려면 몇 가지 작업을 수행 해야 합니다. 클라이언트 환경 구성에 대 한 변경 작업을 시작 하기 전에 먼저 클라이언트 정책 설정을 지 원하는 비즈니스용 Skype Server 또는 Lync Server 버전을 사용 하 고 있는지 확인 해야 합니다.
  
클라이언트 환경을 제어 하기 위해 정책 설정을 지 원하는 비즈니스용 Skype 서버 또는 Lync Server 버전을 사용 하 고 있는지 확인 한 후에는 환경에서 정책 설정을 구성 해야 합니다. 팔 로우 해야 하는 특정 단계는 사용 중인 비즈니스용 Skype 서버 또는 Lync Server의 버전 및 사용자가 온-프레미스 또는 온라인 인지에 따라 달라 집니다. 
  
클라이언트 업데이트를 사용자에 게 전달 하기 전에 이러한 변경을 수행 하 여 비즈니스용 Skype 클라이언트를 처음 시작할 때 클라이언트 환경을 제어할 수 있도록 합니다. 다음 표에서는 사용자를 위해 원하는 클라이언트 환경에 맞게 환경을 구성 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.
  
|**Deployment**|**비즈니스용 Skype 클라이언트 환경**|**Lync 클라이언트 환경**|
|:-----|:-----|:-----|
|비즈니스용 Skype Online  <br/> |클라이언트 빌드 4711.1002 (4 월 2015) 이상을 배포 하는 것 외에는 추가 단계가 없습니다.  <br/> |[비즈니스용 Skype Online에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithSfBO) <br/> |
|비즈니스용 Skype 서버 2015  <br/> |클라이언트 빌드 4711.1002 (4 월 2015) 이상을 배포 하는 것 외에는 추가 단계가 없습니다.  <br/> |[비즈니스용 Skype Server 온-프레미스에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 및 Lync Server 2010  <br/> |[Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경을 사용 합니다.](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 또는 lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 Lync Server 2010 온-프레미스에서 Skype 클라이언트 환경을 사용 합니다.
<a name="SkypewithLynconprem"> </a>

온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 따르세요. 온-프레미스의 기본 환경
  
 **1 단계:** 먼저 클라이언트 정책 설정을 지 원하는 Lync Server 버전을 실행 하 고 있는지 확인 합니다.
  
- **Lync server 2013** -lync server 2013 이상 업데이트에 대해 12 월 2014 누적 업데이트 (5.0.8308.857)를 실행 중 이어야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532772)를 참조 하세요.
    
- **Lync server 2010** -lync server 2010 이상 업데이트에 대해 2 월 2015 누적 업데이트 (4.0.7577.710)를 실행 중 이어야 합니다. 자세한 내용은 [Lync Server 2010에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532771)를 참조 하세요.
    
  **2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트에서 Skype 클라이언트 환경을 설정 합니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하는 데는 **세 가지 옵션이** 있습니다.
  
  **옵션 1:** 글로벌 정책을 사용 하 여 Skype 클라이언트 환경을 설정 합니다. 전역 정책은 배포의 모든 사용자에 게 적용 되지만 사용자 및 사이트 수준 정책은 전역 정책에 우선 합니다.
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Skype 클라이언트 경험을 사용할 수 있도록 설정 합니다. 이렇게 하면 기존 정책이 지정 된 사용자 에게만 Skype 클라이언트 환경을 할당할 수 있습니다.
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **옵션 3:** Skype 클라이언트 경험에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **id** 매개 변수 값으로 제공 합니다.
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

그런 다음 정책 이름 ( **id** 매개 변수에 사용한 값)을 **PolicyName** 매개 변수 값으로 사용 하 여 사용자에 게 정책을 할당 합니다.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **3 단계:** 클라이언트 정책을 구성한 후에는 비즈니스용 Skype 클라이언트를 배포 하 고 4711.1002 (4 월, 2015) 이상을 빌드합니다.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 또는 lync Server 2010 온-프레미스에서 Lync 클라이언트 환경 사용
<a name="LyncwithLynconprem"> </a>

이는 비즈니스용 Skype 클라이언트가 온-프레미스 Lync Server 배포에 배포 된 경우의 기본 환경입니다. Lync 클라이언트 환경을 사용 하도록 클라이언트 정책을 구성할 필요는 없지만 클라이언트의 첫 번째 실행 동작을 제어 하는 것이 좋습니다. 기본적으로 사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하면 Skype 클라이언트 환경이 사용 되며, Lync 클라이언트 환경을 얻기 위해 클라이언트를 다시 시작 하도록 요청 하는 알림이 사용자에 게 표시 됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 환경을 구성 하 고 클라이언트 컴퓨터에서 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 끌 수 있습니다. 비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계는 다음 항목 중 하나를 참조 하세요.
  
- **Lync server 2013**의 lync [Server 2013에서 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성을](https://go.microsoft.com/fwlink/p/?LinkId=532732) 참조 하세요.
    
- **Lync server 2010** [에서 lync server 2010의 비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성을](https://go.microsoft.com/fwlink/p/?LinkId=532733) 참조 하세요.
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>비즈니스용 Skype Server 온-프레미스에서 Lync 클라이언트 환경 사용
<a name="LyncwithSfBServer"> </a>

온-프레미스 비즈니스용 Skype 서버 배포에서 Lync 클라이언트 환경을 구성 하려면이 섹션의 단계를 따르세요.
  
온-프레미스 배포에서 Skype 클라이언트 환경을 구성 하려면이 섹션의 단계를 따르세요. 온-프레미스의 기본 환경
  
 **1 단계:** 먼저 비즈니스용 Skype 서버를 배포 합니다.
  
 **2 단계:** 다음으로, 클라이언트 정책을 사용 하 여 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 설정 합니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하는 데는 **세 가지 옵션이** 있습니다.
  
 **옵션 1:** 전역 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다. 전역 정책은 배포의 모든 사용자에 게 적용 되지만 사용자 및 사이트 수준 정책은 전역 정책에 우선 합니다.
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 설정 하는 설정을 포함 합니다. 이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자에 게 할당할 새 정책을 만듭니다. 먼저 새 클라이언트 정책을 만들고 정책 이름을 **id** 매개 변수 값으로 제공 합니다.
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

그런 다음 정책 이름 ( **id** 매개 변수에 사용한 값)을 **PolicyName** 매개 변수 값으로 사용 하 여 사용자에 게 정책을 할당 합니다.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **3 단계: 선택 사항** -기본적으로 사용자가 비즈니스용 skype 클라이언트를 처음 시작 하면 skype 클라이언트 환경이 사용 되며, 사용자에 게 Lync 클라이언트 환경을 얻기 위해 클라이언트를 다시 시작 하도록 요청 하는 알림이 표시 됩니다. 사용자가 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 하 고 클라이언트 컴퓨터의 시스템 레지스트리를 수정 하 여 클라이언트 자습서를 해제 하는 등의 환경을 구성할 수 있습니다. 비즈니스용 Skype 클라이언트를 배포 하기 전에 수행 해야 하는 단계는 [비즈니스용 skype를 사용 하 여 클라이언트 환경 구성을](../../deploy/deploy-clients/configure-the-client-experience.md)참조 하세요.
  
 **4 단계:** 클라이언트 정책을 구성한 후에는 비즈니스용 Skype 클라이언트를 배포 하 고 4711.1002 (4 월, 2015) 이상을 빌드합니다.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>비즈니스용 Skype Online에서 Lync 클라이언트 환경 사용
<a name="LyncwithSfBO"> </a>

Lync 클라이언트 환경을 구성 하 고 비즈니스용 Skype Online을 사용 하려는 경우이 섹션의 단계를 따릅니다.
  
비즈니스용 Skype Online을 사용 하는 경우에도 원격 PowerShell을 사용 하 여 클라이언트 정책을 구성 하 여 조직의 비즈니스용 Skype 클라이언트에서 Lync 클라이언트 환경을 사용할 수 있습니다. 클라이언트 정책을 사용 하 여 클라이언트 환경을 설정 하는 데는 **세 가지 옵션이** 있습니다. 정책 및 매개 변수 이름은 비즈니스용 Skype 또는 Lync Server 온-프레미스를 사용 하는 경우 클라이언트 환경을 구성 하는 데 사용 하는 설정과 다릅니다.
  
 **옵션 1:** 전역 정책을 사용 하 여 Lync 클라이언트 환경을 설정 합니다. 사용자에 게 적용 되는 클라이언트 및 사이트 정책이 전역 정책 보다 우선 한다는 점에 유의 하세요.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 2:** 환경에서 사용 중인 기존 클라이언트 정책을 수정 하 여 Lync 클라이언트 환경을 설정 하는 설정을 포함 합니다. 이렇게 하면 기존 정책이 할당 된 사용자 에게만 Lync 클라이언트 환경을 할당할 수 있습니다.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **옵션 3:** Lync 클라이언트 환경에 대 한 설정을 포함 하는 사용자 지정 정책 인스턴스를 사용 합니다.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

클라이언트 정책을 구성한 후에는 비즈니스용 Skype 클라이언트를 배포 하 고 4711.1002 (4 월, 2015) 이상을 빌드합니다.
  
환경을 구성 하는 데 사용할 수 있는 첫 번째 실행 환경 및 PowerShell 스크립트를 제어 하는 방법에 대 한 단계를 포함 하 여 비즈니스용 Skype Online으로 클라이언트 환경을 구성 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요. [ 비즈니스용 Skype 및 Lync 클라이언트 사용자 인터페이스](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>업데이트를 위해 지원 팀과 최종 사용자를 준비 하는 데 도움이 되는 리소스
<a name="support"> </a>

사용자와 조직에서 전환을 준비 하는 것을 더욱 쉽게 하기 위해, 최종 사용자를 계획, 교육, 참여 하는 데 도움이 되는 추가 리소스도 여러 개 있습니다.
  
- [비디오: 비즈니스용 Skype 소개](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [비즈니스용 Skype 빠른 시작 가이드 (다운로드)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync는 이제 비즈니스용 Skype-새로운 기능을 참조 하세요.](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [비즈니스용 Skype: 새 사용자를 위한 단계별 가이드](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync를 사용할 때 비즈니스용 Skype가 표시 되는 이유는 무엇 인가요?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

