---
title: Mac 클라이언트 요구 사항에 대 한 비즈니스용 Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Mac에서 비즈니스용 Skype를 실행 하는 데 필요한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대해 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013461"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 클라이언트 요구 사항에 대 한 비즈니스용 Skype
 
Mac에서 비즈니스용 Skype를 실행 하는 데 필요한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대해 알아보려면이 항목을 읽어 보십시오.
  
[Mac 용 비즈니스용 Skype 클라이언트](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) 를 다운로드할 수 있습니다.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac의 비즈니스용 Skype에 대 한 하드웨어 및 소프트웨어 요구 사항

Mac 용 비즈니스용 Skype 클라이언트는 Mac OS X El Capitan 이상 이어야 하며 최소한 100MB의 디스크 공간을 사용 해야 합니다. 기본적으로 제공 되는 모든 오디오 및 비디오 장치를 사용할 수 있습니다. 외부 장치는 [비즈니스용 Skype 솔루션 카탈로그](https://partnersolutions.skypeforbusiness.com/solutionscatalog)에 있어야 합니다. 
  
> [!NOTE]
> 이 목록은 임시이 고 일부 장치는 Lync에서 한정 될 수 있지만 Mac의 비즈니스용 Skype에서는 지원 되지 않습니다. 필요한 최소 하드웨어에 대 한 [시스템 요구 사항을](https://products.office.com/office-system-requirements) 참조 하세요.
  
### <a name="legacy-mac-clients"></a>레거시 Mac 클라이언트

또한 비즈니스용 Skype 서버 2015은 Mac OS 10.5.8 또는 최신 서비스 팩 또는 릴리스 (Intel 기반) 운영 체제를 실행 하는 컴퓨터에서 다음과 같은 레거시 클라이언트만 지원 합니다 (Mac OS 10.9 운영 체제가 현재 지원 되지 않음). 지원 되는 기능에 대 한 자세한 내용은 [비즈니스용 Skype에 대 한 데스크톱 클라이언트 기능 비교](desktop-feature-comparison.md)를 참조 하세요.
  
- Mac 용 Microsoft Lync 2011 ( [mac 용 Lync 2011 배포 가이드](https://go.microsoft.com/fwlink/p/?LinkId=268786)참조)
    
- Mac 용 Microsoft Communicator 2011 ( [mac 용 communicator 2011 배포 가이드](https://go.microsoft.com/fwlink/p/?LinkId=268787)참조)
 
이러한 클라이언트는 비즈니스용 Skype 서버 2019에서 지원 되지 않습니다.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac의 비즈니스용 Skype에 대 한 인프라 요구 사항
<a name="Infrastructure"> </a>

Mac 용 비즈니스용 Skype 클라이언트는 모바일 클라이언트에서 사용 하는 통합 커뮤니케이션 관리 플랫폼 (c 지 MP) 뿐만 아니라 통합 Communications Web API (WA)를 모두 활용 합니다.
  
클라이언트는 모바일 클라이언트와 동일한 요구 사항을 충족 하며, 액세스에 지 서버 및 역방향 프록시가 지원 되는 구성에 배포 되어 있어야 합니다. 
  
### <a name="authentication"></a>인증

Mac 용 비즈니스용 Skype 클라이언트는 인증서 기반 인증, Microsoft 최신 인증 및 배포 및 사용이 가능 하 게 다단계 인증을 지원 합니다.
  
> [!NOTE]
> 현재 한계로 인해 사용자의 Exchange 자격 증명은 비즈니스용 Skype 자격 증명과 동일 해야 합니다. 
  
### <a name="certificates"></a>인증서

액세스에 지에서 사용 중인 인증서, 역방향 프록시 및 프런트 엔드 서버는 SHA-512 해시 알고리즘을 사용 하지 않아야 합니다.
  
HTTP 인증서 해지 목록은 클라이언트에서 정의 되 고 액세스 가능 해야 합니다. 예를 들어 인증서 해지 목록으로 인증서의 LDAP 항목을 지원 하지 않습니다.
  
### <a name="dns"></a>DNS

Mac 클라이언트에서 비즈니스용 Skype에 대 한 이동성을 제대로 배포 해야 올바르게 작동 합니다. 일반적인 실패 시나리오는 내부 네트워크에서 다음 DNS 항목을 모두 확인할 수 있도록 하는 것입니다.
  
- lyncdiscoverinternal. \<microsoft.rtc.management.xds.sipdomain object\>
    
- lyncdiscover. \<microsoft.rtc.management.xds.sipdomain object\>
    
자세한 내용은 [Lync server 2013의 모바일 기능 배포](https://go.microsoft.com/fwlink/p/?LinkId=798224)및 [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226)를 참조 하십시오.
  
## <a name="see-also"></a>참고 항목
<a name="Infrastructure"> </a>

[비즈니스용 Skype 서버에 대 한 DNS 요구 사항](../../plan-your-deployment/network-requirements/dns.md)

[자주하는 질문](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[알려진 문제](https://go.microsoft.com/fwlink/p/?LinkId=798228)
