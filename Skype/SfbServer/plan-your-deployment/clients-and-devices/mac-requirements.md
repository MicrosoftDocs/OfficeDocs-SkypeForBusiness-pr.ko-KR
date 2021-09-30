---
title: 비즈니스용 Skype 클라이언트 요구 사항
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Mac에서 응용 프로그램 실행을 위한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대해 비즈니스용 Skype 항목을 읽어 읽습니다.
ms.openlocfilehash: e25995173b44cf4f5892c1a34f77529042125c58
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014472"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>비즈니스용 Skype 클라이언트 요구 사항
 
Mac에서 응용 프로그램 실행을 위한 하드웨어, 소프트웨어 및 인프라 요구 사항에 대해 비즈니스용 Skype 항목을 읽어 읽습니다.
  
Mac [비즈니스용 Skype 다운로드할](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) 수 있습니다.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac용 하드웨어 및 비즈니스용 Skype 요구 사항

Mac 비즈니스용 Skype Mac OS X El Capitan 이상이 필요하며 최소 100MB의 디스크 공간을 사용 합니다. 모든 기본 제공 오디오 및 비디오 장치를 사용할 수 있습니다. 외부 장치는 장치 에 [Microsoft Teams 합니다.](https://www.microsoft.com/microsoft-teams/across-devices/devices) 
  
> [!NOTE]
> 이 목록은 초급이지만 일부 장치는 Lync에 대해 자격을 갖춘 것일 수 있지만 Mac의 비즈니스용 Skype 지원되지 않습니다. 필요한 최소 [하드웨어에](https://products.office.com/office-system-requirements) 대한 시스템 요구 사항을 참조하세요.
  
### <a name="legacy-mac-clients"></a>레거시 Mac 클라이언트

비즈니스용 Skype 서버 2015는 Mac OS 10.5.8 또는 최신 서비스 팩 또는 릴리스(Intel 기반) 운영 체제를 실행하는 컴퓨터에서도 다음 레거시 클라이언트를 지원합니다(Mac OS 10.9 운영 체제는 현재 지원되지 않습니다). 지원되는 기능에 대한 자세한 내용은 에 대한 데스크톱 클라이언트 기능 [비교를 비즈니스용 Skype.](desktop-feature-comparison.md)
  
- Microsoft Lync for Mac 2011(Lync [for Mac 2011 배포 가이드](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))참조)
    
- Microsoft Communicator for Mac 2011(Communicator [for Mac 2011 배포 가이드](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))참조)
 
이러한 클라이언트는 2019년 8월에 비즈니스용 Skype 서버 않습니다.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac의 비즈니스용 Skype 인프라 요구 사항
<a name="Infrastructure"> </a>

Mac 비즈니스용 Skype 클라이언트는 모바일 클라이언트가 사용하는 UCMP(Unified Communications Management Platform)와 UCWA(Unified Communications Web API)를 모두 활용합니다.
  
지원되는 구성에서 액세스 에지 서버 및 역방향 프록시를 배포해야 하다는 점에서 클라이언트의 모바일 클라이언트와 동일한 요구 사항이 있습니다. 
  
### <a name="authentication"></a>인증

Mac 비즈니스용 Skype 클라이언트는 배포 및 사용 시 인증서 기반 인증, Microsoft 최신 인증 및 다단계 인증을 지원합니다.
  
> [!NOTE]
> 현재 제한 사항으로 인해 사용자의 Exchange 자격 증명은 해당 자격 증명과 비즈니스용 Skype 되어야 합니다. 
  
### <a name="certificates"></a>인증서

액세스 에지, 역방향 프록시 및 프런트 엔드 서버에서 사용 중인 인증서는 SHA-512 해시 알고리즘을 사용하지 말아야 합니다.
  
HTTP 인증서 해지 목록은 클라이언트가 정의하고 액세스할 수 있어야 합니다. 예를 들어 인증서 해지 목록으로 인증서의 LDAP 항목을 지원하지 않습니다.
  
### <a name="dns"></a>DNS

Mac 클라이언트에서 모바일 기능이 제대로 비즈니스용 Skype 모바일 기능을 제대로 배포해야 합니다. 일반적인 오류 시나리오는 내부 네트워크에서 다음 두 DNS 항목을 모두 확인할 수 있는 것입니다.
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
자세한 내용은 [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)및 [Microsoft Lync Server 2010 Mobility Guide를 참조하십시오.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>참고 항목
<a name="Infrastructure"> </a>

[서버의 DNS 비즈니스용 Skype 서버](../../plan-your-deployment/network-requirements/dns.md)

[질문과 대답](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[알려진 문제](https://go.microsoft.com/fwlink/p/?LinkId=798228)