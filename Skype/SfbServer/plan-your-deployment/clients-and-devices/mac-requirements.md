---
title: 비즈니스용 Skype for Mac 클라이언트 요구 사항
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
description: Mac에서 비즈니스용 Skype를 실행 하기 위한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803598"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>비즈니스용 Skype for Mac 클라이언트 요구 사항
 
Mac에서 비즈니스용 Skype를 실행 하기 위한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대 한 자세한 내용은이 항목을 참조 하세요.
  
[Mac 클라이언트의 비즈니스용 Skype](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) 를 다운로드할 수 있습니다.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac의 비즈니스용 Skype에 대 한 하드웨어 및 소프트웨어 요구 사항

Mac 용 비즈니스용 Skype 클라이언트는 Mac OS X El Capitan 이상이 필요 하며 최소 100MB의 디스크 공간을 사용 합니다. 모든 기본 제공 오디오 및 비디오 장치 사용이 지원 됩니다. 외부 장치는 [비즈니스용 Skype 솔루션 카탈로그](https://partnersolutions.skypeforbusiness.com/solutionscatalog)에 있어야 합니다. 
  
> [!NOTE]
> 이 목록은 임시 이며 일부 장치는 Lync에 한정 될 수 있지만 Mac의 비즈니스용 Skype에서는 지원 되지 않습니다. 필요한 최소 하드웨어에 대 한 [시스템 요구 사항을](https://products.office.com/en-us/office-system-requirements) 참조 하세요.
  
### <a name="legacy-mac-clients"></a>레거시 Mac 클라이언트

또한 Mac OS 10.5.8 이상과 또는 최신 서비스 팩 또는 릴리스 (Intel 기반) 운영 체제를 실행 하는 컴퓨터에서 다음과 같은 레거시 클라이언트를 지원 합니다 (Mac OS 10.9 운영 체제는 현재 지원 되지 않음). 2015 지원 되는 기능에 대 한 자세한 내용은 [비즈니스용 Skype의 데스크톱 클라이언트 기능 비교](desktop-feature-comparison.md)를 참조 하세요.
  
- Mac 용 Microsoft Lync 2011 ( [mac 용 Lync 2011 배포 가이드](https://go.microsoft.com/fwlink/p/?LinkId=268786)참조)
    
- Mac 용 Microsoft Communicator 2011 ( [mac 용 communicator 2011 배포 가이드](https://go.microsoft.com/fwlink/p/?LinkId=268787)참조)
 
이러한 클라이언트는 비즈니스용 Skype 서버 2019에서 지원 되지 않습니다.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac에서 비즈니스용 Skype의 인프라 요구 사항
<a name="Infrastructure"> </a>

Mac 클라이언트의 비즈니스용 Skype는 통합 커뮤니케이션 관리 플랫폼 (c MP) 및 모바일 클라이언트가 사용 하는 통일 된 커뮤니케이션 웹 API (와)를 모두 활용 합니다.
  
클라이언트에는 모바일 클라이언트와 동일한 요구 사항이 있으므로 지원 되는 구성으로 액세스에 지 서버 및 리버스 프록시를 배포 해야 합니다. 
  
### <a name="authentication"></a>인증

Mac 용 비즈니스용 Skype 클라이언트는 인증서 기반 인증, Microsoft 최신 인증, 배포 및 활성화 시 Multi-factor Authentication을 지원 합니다.
  
> [!NOTE]
> 현재 제한 사항으로 인해 사용자의 Exchange 자격 증명은 비즈니스용 Skype 자격 증명과 동일 해야 합니다. 
  
### <a name="certificates"></a>인증

액세스에 지에 사용 되는 인증서, 역방향 프록시 및 프런트 엔드 서버는 SHA-512 해시 알고리즘을 사용 하지 않아야 합니다.
  
HTTP 인증서 해지 목록은 클라이언트에서 정의 하 고 액세스할 수 있어야 합니다. 예를 들어 인증서 해지 목록으로 인증서의 LDAP 항목을 지원 하지 않습니다.
  
### <a name="dns"></a>DNS

Mac 클라이언트의 비즈니스용 Skype가 제대로 작동 하려면 이동성을 적절히 배포 해야 합니다. 일반적인 실패 시나리오는 다음 DNS 항목을 모두 내부 네트워크에서 확인할 수 있도록 하는 것입니다.
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
자세한 내용은 [Lync server 2013의 이동성 배포](https://go.microsoft.com/fwlink/p/?LinkId=798224)및 [Microsoft Lync Server 2010 모바일 가이드](https://go.microsoft.com/fwlink//p/?LinkId=798226)를 참조 하세요.
  
## <a name="see-also"></a>참고 항목
<a name="Infrastructure"> </a>

[비즈니스용 Skype 서버에 대 한 DNS 요구 사항](../../plan-your-deployment/network-requirements/dns.md)

[자주 묻는 질문](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[알려진 문제](https://go.microsoft.com/fwlink/p/?LinkId=798228)
