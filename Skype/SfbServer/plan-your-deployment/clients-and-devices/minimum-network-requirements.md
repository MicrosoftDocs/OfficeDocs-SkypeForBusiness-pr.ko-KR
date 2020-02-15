---
title: Skype 모임 앱 최소 네트워크 요구 사항
ms.author: v-lanac
author: lanachin
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
description: '요약: Office 365를 사용 하지 않고 조직에서 호스팅하는 모임에 액세스 해야 하는 조직에 대 한 정보입니다.'
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033192"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 모임 앱 최소 네트워크 요구 사항
 
**요약:**  Office 365를 사용 하지 않고 조직에서 호스팅하는 모임에 액세스 해야 하는 조직에 대 한 정보입니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.
  
사용자가 Skype 모임 앱을 사용 하 여 비즈니스용 Skype Online에서 호스트 되는 모임에 참가할 수 있도록 허용 하려면 Office 365을 사용 하지 않는 조직의 네트워크 관리자에 게 허용 목록 하거나, 아래에 설명 된 Fqdn, Ip 및 포트를 사용할 수 있어야 합니다.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 모임 앱 연결 요구 사항

여기에 나열 된 정보는 보다 깊이를 제공 하 고 항상 최신 상태로 유지 되는 [Office 365 url 및 IP 주소 범위의](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)하위 집합입니다.
                    
 
|앱 |대상 Fqdn  |IP 주소  |포트  |
|---|---------|---------|---------|
|**Skype 모임 앱** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*<span></span>officeapps.live.com <br/>\*<span></span>officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>* s-microsoft.com<br/>        |   이러한 IP 주소는 자주 업데이트 됩니다.  [OFFICE Ip 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) 는 물론 [비즈니스용 Skype IP 범위](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 를 참조 하세요.         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | 이러한 IP 주소는 자주 업데이트 됩니다.  [OFFICE Ip 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) 는 물론 [비즈니스용 Skype IP 범위](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 를 참조 하세요.      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[모임 클라이언트 계획 (웹 앱 및 모임 앱)](meetings-clients.md)

[비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 모임 앱에 대해 지원 되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
