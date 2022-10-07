---
title: 새로운 직접 라우팅 기능
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 이 문서에서는 직접 라우팅의 새로운 사항에 대해 설명합니다. 업데이트를 자주 확인합니다.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6d2496ef355df7a935dbf45321a8b8fd63b8e8de
ms.sourcegitcommit: fc1787ad74a8c454f750a294def188b532cbadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67854434"
---
# <a name="whats-new-for-direct-routing"></a>직접 라우팅의 새로운 기능

이 문서에서는 직접 라우팅의 새로운 사항에 대해 설명합니다. 업데이트를 자주 확인합니다.

## <a name="trunk-demoting-logic-based-on-sip-options"></a>SIP 옵션에 따라 트렁크 수준 내리기 논리

트렁크 상태에 대한 SIP 옵션을 기반으로 하는 새로운 기능이 도입되었습니다. 게이트웨이 구성에서 사용하도록 설정된 경우(Set-CsOnlinePSTNGateway cmdlet 및 SendSipOptions 매개 변수 참조) 아웃바운드 호출에 대한 라우팅 논리는 SIP 옵션을 주기적으로 보내지 않는 트렁크를 강등합니다(예상 기간은 분당 SBC에서 보낸 하나의 SIP 옵션). 이러한 강등된 트렁크는 아웃바운드 통화에 사용할 수 있는 트렁크 목록의 끝에 배치되며 마지막 트렁크로 시도됩니다. 따라서 호출 설정 시간이 감소할 수 있습니다.
Microsoft 지역(NOAM, EMEA, APAC, OCEA) SIP 프록시에 5분 이내에 하나 이상의 SIP 옵션을 보내지 않는 해당 기능에 대해 사용하도록 설정된 모든 트렁크는 강등된 것으로 간주됩니다. 트렁크가 Microsoft 지역 SIP 프록시의 하위 집합에만 SIP 옵션을 보내는 경우 이러한 경로가 먼저 시도되고 나머지는 강등됩니다.


## <a name="sip-support"></a>SIP 지원

2022년 6월 1일에 Microsoft는 직접 라우팅 구성에서 sip-all.pstnhub.microsoft.com 및 sip-all.pstnhub.gov.teams.microsoft.us FQDN에 대한 지원을 제거합니다.

6월 1일 이전에 수행된 작업이 없는 경우 사용자는 직접 라우팅을 통해 전화를 걸거나 받을 수 없습니다.

서비스 영향을 방지하려면 다음을 수행합니다.

- 분류 또는 ACL 규칙에 권장되는 서브넷(52.112.0.0/14 및 52.120.0.0/14)을 사용합니다.
- 직접 라우팅에 대한 세션 테두리 컨트롤을 구성할 때 sip-all FQDN 사용을 중단합니다.

자세한 내용은 [직접 라우팅 계획을 참조하세요](direct-routing-plan.md).

## <a name="tls-certificates"></a>TLS 인증서

Microsoft 365는 다른 CA(루트 인증 기관) 집합을 사용하도록 Teams 및 기타 서비스를 업데이트하고 있습니다.

자세한 내용과 영향을 받는 서비스의 전체 목록은 [Microsoft Teams를 포함한 Microsoft 365 서비스에 대한 TLS 인증서 변경 내용을 참조하세요](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>인증 기관

2022년 2월 1일부터 직접 라우팅 SIP 인터페이스는 Microsoft 신뢰할 수 있는 루트 인증서 프로그램의 일부인 CA(인증 기관)에서 서명한 인증서만 신뢰합니다. 서비스 영향을 방지하려면 다음 단계를 수행합니다.

- SBC 인증서가 Microsoft 신뢰할 수 있는 루트 인증서 프로그램의 일부인 CA에 의해 서명되었는지 확인합니다.
- 인증서의 EKU(확장 키 사용) 확장에 "서버 인증"이 포함되어 있는지 확인합니다.

Microsoft 신뢰할 수 있는 루트 인증서 프로그램에 대한 자세한 내용은 [프로그램 요구 사항 - Microsoft 신뢰할 수 있는 루트 프로그램을](/security/trusted-root/program-requirements) 참조하세요.

신뢰할 수 있는 CA 목록은 [Microsoft 포함 CA 인증서 목록을 참조하세요](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>머리글 바꾸기

2022년 4월부터 직접 라우팅은 Replaces 헤더가 정의된 SIP 요청을 거부합니다. Microsoft에서 Replaces 헤더를 SBC(Session Border Controller)로 보내는 흐름에는 변경 내용이 없습니다.

SBC 구성을 확인하고 SIP 요청에서 Replaces 헤더를 사용하지 않는지 확인합니다.

## <a name="tls10-and-11"></a>TLS1.0 및 1.1

Microsoft는 고객에게 동급 최고의 암호화를 제공하기 위해 TLS(전송 계층 보안) 버전 1.0 및 1.1을 더 이상 사용하지 않을 계획입니다. 2022년 4월 3일에 Microsoft는 직접 라우팅 SIP 인터페이스에 TLS1.2를 강제로 사용합니다.

서비스에 영향을 주지 않으려면 SCC가 TLS1.2를 지원하도록 구성되어 있고 다음 암호 그룹 중 하나를 사용하여 연결할 수 있는지 확인합니다.

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 예: ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 예: ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 예: ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 예: ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>관련 주제

- [직접 라우팅 - SIP 프로토콜](direct-routing-protocols-sip.md)
