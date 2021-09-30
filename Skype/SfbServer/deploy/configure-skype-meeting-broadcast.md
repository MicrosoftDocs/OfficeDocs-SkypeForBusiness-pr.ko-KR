---
title: 브로드캐스트에 대한 Skype 모임 배포 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '요약: 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 비즈니스용 Skype 서버 단계에 대해 설명합니다.'
ms.openlocfilehash: 99ba1733dc8c353dc17f9a4c9a51a9ed00410d27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013712"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>브로드캐스트에 대한 Skype 모임 배포 구성
 
**요약:** 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 비즈니스용 Skype 서버 대해 설명합니다.
  
Skype 모임 브로드캐스트는 브로드캐스트의 일부인 온라인 Office 365. 비즈니스용 Skype 서버 실행 중이고 환경에서 Skype 모임 Broadcast를 사용하려는 경우 이 항목의 구성 단계를 따라야 합니다. 시작하기 전에 온라인에서 하이브리드 환경으로 환경을 비즈니스용 Skype 합니다. 자세한 내용은 비즈니스용 Skype 서버 online과 비즈니스용 Skype [Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버 및 비즈니스용 Skype Online 간에 하이브리드 [연결 배포를 참조하세요.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>브로드캐스트에 대한 하이브리드 Skype 모임 구성

브로드캐스트를 사용할 수 있도록 환경을 준비하려면 다음을 Skype 모임 합니다.
  
- 온라인 리소스와의 비즈니스용 Skype 구성
    
- SIP 페더전된 도메인 구성
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>온라인 리소스와의 비즈니스용 Skype 구성

온라인 리소스와의 비즈니스용 Skype 사용하도록 설정하려면 SIP 페더임 공급자에 대해 외부 액세스를 구성해야 합니다. 이 작업을 수행하기 위해 비즈니스용 Skype 서버 다음 단계를 수행합니다.
  
1. 제어판 비즈니스용 Skype 서버 시작하고 **왼쪽에서 외부** 액세스를 선택합니다.
    
2. **SIP 페더리트 공급자를 선택하고** 새로 **고치기 를 클릭합니다.**
    
3. 다음 설정을 사용하여 새 공급자를 구성합니다.
    
   - **이 공급자와의 통신을 사용하도록 설정:** 선택
   - **공급자 이름:** LyncOnlineResources
   - **액세스 에지 서비스(FQDN): sipfed.resources.lync.com**
   - **기본 확인 수준:** 사용자가 이 공급자를 사용하는 모든 사용자와 통신할 수 있도록 허용합니다. 
   
또한 비즈니스용 Skype 관리 셸에서 다음 cmdlet을 실행하여 비즈니스용 Skype 서버 있습니다.
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP 페더전된 도메인 구성

다음으로, 허용 도메인 목록에 SIP 페더리드 도메인을 추가해야 합니다. 나열된 각 도메인에 대해 이 단계를 반복하여 4개 새 SIP 페더타임 도메인을 생성합니다. 이러한 도메인은 온라인에서 사용되는 지역별 데이터 센터에 비즈니스용 Skype 있습니다.
  
1. 제어판 비즈니스용 Skype 서버 시작하고 **왼쪽에서 외부** 액세스를 선택합니다.
    
2. **SIP 페더전 도메인을 선택하고** 새로 **고치기 를 클릭합니다.**
    
3. 도메인 **이름(또는 FQDN):** 에 대해 도메인을 입력하고 다음 각 도메인에 대해 이 절차를 반복합니다.
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 SIP 페더티드 도메인에 대한 외부 액세스를 구성할 비즈니스용 Skype 서버 있습니다.
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

이러한 구성 단계를 완료한 후 배포에서 Skype 모임 브로드캐스트를 사용할 수 있습니다. 브로드캐스트에 대한 Skype 모임 브로드캐스트란? 및 Skype 모임 관리자 [](https://go.microsoft.com/fwlink/?LinkId=617071) [가이드를 Skype 모임 참조하세요.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)
