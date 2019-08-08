---
title: Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '요약: 온-프레미스 비즈니스용 skype Server 하이브리드 배포에 대해 Skype 모임 브로드캐스트를 구성 하기 위해 수행 해야 하는 단계에 대해 알아보세요.'
ms.openlocfilehash: bd87c64dd1e54c8092186a3e233557ebd11eec77
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234585"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성
 
**요약:** 온-프레미스 비즈니스용 skype Server 하이브리드 배포에 대해 Skype 모임 브로드캐스트를 구성 하기 위해 수행 해야 하는 단계에 대해 알아보세요.
  
Skype 모임 브로드캐스트는 Office 365의 일부인 온라인 서비스입니다. Skype for Business Server 온-프레미스를 실행 중이 고 해당 환경에서 Skype 모임 브로드캐스트를 사용 하려는 경우이 항목의 구성 단계를 수행 해야 합니다. 시작 하기 전에 비즈니스용 Skype Online을 사용 하 여 하이브리드에 맞게 환경을 구성 해야 합니다. 자세한 내용은 비즈니스용 [Skype 서버 및 비즈니스용 Skype online 간 하이브리드 연결 계획](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 을 참조 하 고 비즈니스용 [skype 서버와 비즈니스용 skype online 간 하이브리드 연결을 배포](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)합니다.
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트를 위한 하이브리드 환경 구성

Skype 모임 브로드캐스트를 위해 환경을 준비 하려면 다음을 수행 해야 합니다.
  
- 비즈니스용 Skype Online 리소스를 사용 하 여 페더레이션 구성
    
- SIP 페더레이션 도메인 구성
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>비즈니스용 Skype Online 리소스를 사용 하 여 페더레이션 구성

비즈니스용 Skype Online 리소스와 페더레이션을 사용 하도록 설정 하려면 SIP 페더레이션 공급자에 대 한 외부 액세스를 구성 해야 합니다. 비즈니스용 Skype 서버 제어판을 사용 하 여이 작업을 수행 하려면 다음 단계를 따르세요.
  
1. 비즈니스용 Skype 서버 제어판을 시작 하 고 왼쪽에서 **외부 액세스** 를 선택 합니다.
    
2. **SIP 페더레이션 공급자** 를 선택 하 고 **새로 만들기**를 클릭 합니다.
    
3. 다음 설정을 사용 하 여 새 공급자를 구성 합니다.
    
|||
|:-----|:-----|
|**이 공급자와 통신 사용:** <br/> |선택한  <br/> |
|**공급자 이름:** <br/> |LyncOnlineResources  <br/> |
|**액세스에 지 서비스 (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**기본 확인 수준:** <br/> |사용자가이 공급자를 사용 하 여 모든 사용자와 통신할 수 있도록 합니다.  <br/> |
   
비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 비즈니스용 Skype Online 리소스에서 페더레이션을 사용 하도록 설정할 수도 있습니다.
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP 페더레이션 도메인 구성

다음으로 허용 된 도메인 목록에 SIP 페더레이션 도메인을 추가 해야 합니다. 나열 된 각 도메인에 대해 이러한 단계를 반복 하 여 4 개의 새로운 SIP 페더레이션 도메인을 만듭니다. 이러한 도메인은 비즈니스용 Skype Online에서 사용 되는 지역 데이터 센터에 포함 되어 있습니다.
  
1. 비즈니스용 Skype 서버 제어판을 시작 하 고 왼쪽에서 **외부 액세스** 를 선택 합니다.
    
2. **SIP 페더레이션 도메인** 을 선택 하 고 **새로 만들기**를 클릭 합니다.
    
3. **도메인 이름 (또는 FQDN):** 다음 각 도메인에 대해이 절차를 반복 하 여 도메인을 입력 합니다.
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 하 여 SIP 페더레이션 도메인에 대 한 외부 액세스를 구성할 수도 있습니다.
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

이러한 구성 단계를 완료 한 후에는 배포에서 Skype 모임 브로드캐스트를 사용 하 여 시작할 수 있습니다. Skype 모임 브로드캐스트에 대 한 자세한 내용은 skype [모임 브로드캐스트 소개](https://go.microsoft.com/fwlink/?LinkId=617071) 및 [Skype 모임 브로드캐스트 관리 가이드](https://go.microsoft.com/fwlink/?LinkId=617075)를 참조 하세요.
  

