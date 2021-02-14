---
title: Skype 모임 브로드캐스트에 대한 프레미스 배포 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '요약: 비즈니스용 Skype 서버 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 수행하는 단계에 대해 설명합니다.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820708"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트에 대한 프레미스 배포 구성
 
**요약:** 비즈니스용 Skype 서버 하이브리드 배포를 위해 Skype 모임 브로드캐스트를 구성하기 위해 수행하는 단계에 대해 설명합니다.
  
Skype 모임 브로드캐스트는 Office 365의 일부인 온라인 서비스입니다. 비즈니스용 Skype 서버를 실행하고 있으며 사용자 환경에서 Skype 모임 브로드캐스트를 사용하려는 경우 이 항목의 구성 단계를 따라야 합니다. 시작하기 전에 비즈니스용 Skype Online을 통해 하이브리드 환경을 구성해야 합니다. 자세한 내용은 비즈니스용 Skype 서버와 비즈니스용 [Skype Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 간의 하이브리드 연결 계획과 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트에 대한 하이브리드 환경 구성

Skype 모임 브로드캐스트를 위한 환경을 준비하려면 다음을 해야 합니다.
  
- 비즈니스용 Skype Online 리소스와의 페더 연결 구성
    
- SIP 페더전 도메인 구성
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>비즈니스용 Skype Online 리소스와의 페더 연결 구성

비즈니스용 Skype Online 리소스와의 페더전을 사용하도록 설정하려면 SIP 페더타임 공급자에 대해 외부 액세스를 구성해야 합니다. 비즈니스용 Skype 서버 제어판을 사용하여 이 작업을 수행하기 위해 다음 단계를 수행합니다.
  
1. 비즈니스용 Skype 서버 제어판을 시작하고 왼쪽에서 **외부** 액세스를 선택합니다.
    
2. **SIP 페더리트 공급자를 선택하고** 새로 **고치기 를 클릭합니다.**
    
3. 다음 설정을 사용하여 새 공급자를 구성합니다.
    
|||
|:-----|:-----|
|**이 공급자와의 통신을 사용하도록 설정:** <br/> |선택됨  <br/> |
|**공급자 이름:** <br/> |LyncOnlineResources  <br/> |
|**액세스 에지 서비스(FQDN):**    필수 속성입니다. <br/> |sipfed.resources.lync.com  <br/> |
|**기본 확인 수준:** <br/> |사용자가 이 공급자를 사용하는 모든 사용자와 통신할 수 있도록 허용합니다.  <br/> |
   
비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 비즈니스용 Skype Online 리소스와의 페더 관리를 사용하도록 설정할 수 있습니다.
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP 페더전 도메인 구성

그런 다음 허용 도메인 목록에 SIP 페더리 도메인을 추가해야 합니다. 나열된 각 도메인에 대해 이 단계를 반복하여 4개 새 SIP 페더타임 도메인을 생성합니다. 이러한 도메인은 비즈니스용 Skype Online에서 사용되는 지역별 데이터 센터용입니다.
  
1. 비즈니스용 Skype 서버 제어판을 시작하고 왼쪽에서 **외부** 액세스를 선택합니다.
    
2. **SIP 페더리트 도메인을 선택하고** 새로 **고치기 를 클릭합니다.**
    
3. 도메인 이름 **또는 FQDN의** 경우 다음 각 도메인에 대해 이 절차를 반복하여 도메인을 입력합니다.
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행하여 SIP 페더타 도메인에 대한 외부 액세스를 구성할 수도 있습니다.
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

이러한 구성 단계를 완료한 후 배포에서 Skype 모임 브로드캐스트 사용을 시작할 수 있습니다. Skype 모임 브로드캐스트에 대한 자세한 내용은 [Skype](https://go.microsoft.com/fwlink/?LinkId=617071) 모임 브로드캐스트란? 및 Skype 모임 [브로드캐스트 관리자 가이드를 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=617075)
  

