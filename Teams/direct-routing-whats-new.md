---
title: 새로운 직접 라우팅의 일
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 이 문서에서는 직접 라우팅의 새로운 것을 설명합니다. 업데이트를 자주 확인합니다.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584332"
---
# <a name="whats-new-for-direct-routing"></a>직접 라우팅의 새로운 것

이 문서에서는 직접 라우팅의 새로운 것을 설명합니다. 업데이트를 자주 확인합니다.

## <a name="sip-support"></a>SIP 지원

2022년 6월 1일 Microsoft는 직접 라우팅 구성에서 sip-all.pstnhub.microsoft.com sip-all.pstnhub.gov.teams.microsoft.us FQDNs에 대한 지원을 제거합니다.

6월 1일 전에 작업이 수행되지 않는 경우 사용자는 직접 라우팅을 통해 전화를 걸거나 받을 수 없습니다.

서비스 영향 방지:

- 분류 또는 ACL 규칙에 대해 권장되는 서브넷(52.112.0.0/14 및 52.120.0.0/14)을 사용 합니다.
- 직접 라우팅에 대한 세션 테두리 컨트롤을 구성할 때 sip-all FQDN 사용을 중단합니다.

자세한 내용은 직접 라우팅 [계획을 참조하세요](direct-routing-plan.md).

## <a name="tls-certificates"></a>TLS 인증서

Microsoft 365 다른 TEAMS 인증서 기관(CAS)을 사용하기 위해 다른 서비스 및 기타 서비스를 업데이트하고 있습니다.

자세한 내용 및 영향을 받는 서비스의 전체 목록은 [TLS](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676) 인증서 변경 내용을 Microsoft 365 서비스를 포함하여 Microsoft Teams.

## <a name="certificate-authorities"></a>인증서 기관

2022년 2월 1일부터 직접 라우팅 SIP 인터페이스는 Microsoft 신뢰할 수 있는 루트 인증서 프로그램의 일부인 CAS(인증서 기관)에서 서명한 인증서만 신뢰합니다. 서비스 영향을 방지하기 위해 다음 단계를 수행합니다.

- Microsoft 신뢰할 수 있는 루트 인증서 프로그램의 일부인 CA에서 SBC 인증서를 서명해야 합니다.
- 인증서의 EKU(확장 키 사용) 확장에 "서버 인증"이 포함되어 있는지 확인해야 합니다.

Microsoft 신뢰할 수 있는 루트 인증서 프로그램에 대한 자세한 내용은 프로그램 [요구 사항 - Microsoft 신뢰할 수 있는 루트 프로그램을 참조하세요](/security/trusted-root/program-requirements).

신뢰할 수 있는 CA 목록은 [Microsoft 포함 CA 인증서 목록을 참조하세요](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>헤더 바꾸기

2022년 4월부터 직접 라우팅은 대체 헤더가 정의된 SIP 요청을 거부합니다. Microsoft가 SBC(세션 테두리 컨트롤러)에 바꾸기 헤더를 보내는 흐름에는 변경 내용이 없습니다.

SBC 구성을 확인하고 SIP 요청에서 바꾸기 헤더를 사용하지 않는지 확인합니다.

## <a name="tls10-and-11"></a>TLS1.0 및 1.1

고객에게 최상의 암호화를 제공하기 위해 Microsoft는 TLS(전송 계층 보안) 버전 1.0 및 1.1을 사용되지 않습니다. 2022년 4월 3일부터 Microsoft는 직접 라우팅 SIP 인터페이스에 TLS1.2 사용을 강제로 합니다.

서비스 영향을 방지하기 위해 TLS1.2를 지원하도록 SBC를 구성하고 다음 암호 제품군 중 하나를 사용하여 연결할 수 있는지 확인합니다.

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 예: ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 예: ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 예: ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 예: ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>관련 항목

- [직접 라우팅 - SIP 프로토콜](direct-routing-protocols-sip.md)
