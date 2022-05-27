---
title: Skype 모임 앱 최소 네트워크 요구 사항
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: '요약: Microsoft 365 또는 Office 365 사용하지 않고 조직에서 호스트하는 모임에 액세스해야 하는 조직에 대한 정보입니다.'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674530"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 모임 앱 최소 네트워크 요구 사항

**요약:** Microsoft 365 또는 Office 365 사용하지 않고 조직에서 호스트하는 모임에 액세스해야 하는 조직에 대한 정보입니다. 이 문서는 Office 365 또는 Microsoft 365 최종 사용자를 위한 것이 아닙니다.

Microsoft 365 또는 Office 365 사용하지 않는 조직의 Skype 모임 앱 사용자는 비즈니스용 Skype Online에서 호스트되는 모임에 참석해야 할 수 있습니다. 이러한 모임에 참석하려면 네트워크 관리자가 방화벽을 통해 다음 FQDN, IP 주소 및 포트를 허용해야 합니다.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 모임 앱 연결에 대한 요구 사항

여기에 나열된 정보는 [Office 365 URL 및 IP 주소 범위에](/microsoft-365/enterprise/urls-and-ip-address-ranges) 있는 정보의 하위 집합입니다. 해당 항목은 훨씬 더 심층적이고 항상 최신입니다.

|앱|대상 FQDN|IP 주소|포트|
|---|---------|---------|---------|
|**Skype 모임 앱**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|이러한 IP 주소는 자주 업데이트됩니다. [비즈니스용 Skype 및 Microsoft Teams IP 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 및 [Office IP 범위를 참조하세요.](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|이러한 IP 주소는 자주 업데이트됩니다. [비즈니스용 Skype 및 Microsoft Teams IP 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 및 [Office IP 범위를 참조하세요.](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[모임 클라이언트 계획(웹앱 및 모임 앱)](meetings-clients.md)

[비즈니스용 Skype 서버 웹 다운로드 가능 클라이언트 배포](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 모임 앱에 지원되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
