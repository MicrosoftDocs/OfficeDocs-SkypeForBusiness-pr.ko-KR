---
title: Skype 모임 앱 최소 네트워크 요구 사항
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
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
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '요약: Microsoft 365 또는 Office 365 사용하지 않는 조직에서 호스팅하는 모임에 액세스해야 하는 조직에 대한 정보입니다.'
ms.openlocfilehash: b79c49b1b63041e84cc74887f6693e8601ae2465f90665ff757d9d890cb330cc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283200"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 모임 앱 최소 네트워크 요구 사항
 
**요약:**  조직에서 사이트 또는 Microsoft 365 Office 365 조직에서 호스팅하는 모임에 액세스해야 하는 조직에 대한 정보입니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아니며,
  
사용자가 Skype 모임 앱을 사용하여 비즈니스용 Skype Online에서 호스팅되는 모임에 참석할 수 있도록 허용하기 위해 Microsoft 365 또는 Office 365 사용하지 않는 조직의 네트워크 관리자는 아래 언급된 FQDNS, IP 및 포트를 허용하거나 사용할 수 있도록 해야 합니다.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>모임 Skype 연결에 대한 요구 사항

여기에 나열된 정보는 URL 및 IP 주소 [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)하위 집합으로, 보다 깊이를 제공하며 항상 최신 정보를 제공합니다.
                    
 
|앱 |대상 FQDNs  |IP 주소  |포트  |
|---|---------|---------|---------|
|**Skype 모임 앱** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*<span></span>.officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   이러한 IP 주소는 자주 업데이트됩니다.  IP [비즈니스용 Skype IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 범위 및 IP Office [참조](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | 이러한 IP 주소는 자주 업데이트됩니다.  IP [비즈니스용 Skype IP](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 범위 및 IP Office [참조](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[모임 클라이언트 계획(Web App 및 모임 앱)](meetings-clients.md)

[웹에서 다운로드 가능한 웹 클라이언트 비즈니스용 Skype 서버](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[모임 앱에 Skype 지원되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
