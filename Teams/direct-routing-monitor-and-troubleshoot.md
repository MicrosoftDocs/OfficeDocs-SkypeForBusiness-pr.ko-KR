---
title: 직접 라우팅 모니터링 및 문제 해결
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 세션 경계 컨트롤러, 직접 라우팅 구성 요소 및 Telecom 트렁크를 포함하여 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97bc8afb3645fca4e06b859b765dfbf1e3fe1859
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462322"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>직접 라우팅 모니터링 및 문제 해결

이 문서에서는 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 설명합니다. 

직접 라우팅을 사용하여 전화를 걸고 받는 능력에는 다음 구성 요소가 포함됩니다. 

- 세션 테두리 컨트롤러(SBC) 
- Microsoft Cloud의 직접 라우팅 구성 요소 
- Telecom 트렁크 

문제 해결에 문제가 있는 경우 SBC 공급업체 또는 Microsoft에서 지원 사례를 열 수 있습니다. 

Microsoft는 문제 해결 및 모니터링을 위한 더 많은 도구를 제공하기 위해 작업 중입니다. 업데이트를 위해 설명서를 주기적으로 확인하세요. 

## <a name="direct-routing-diagnostic-tool"></a>직접 라우팅 진단 도구

관리자인 경우 다음 진단 도구를 사용하여 사용자가 직접 라우팅에 대해 올바르게 구성된지 확인할 수 있습니다.

1. 아래에서 **테스트** 실행을 선택하여 진단 센터에 진단을 Microsoft 365 관리 선택합니다. 

   > [!div class="nextstepaction"]
   > [테스트 실행: 직접 라우팅](https://aka.ms/TeamsDirectRoutingDiag)

2. 진단 실행 창에서 사용자 이름 또는 전자 메일 필드에서  테스트할 사용자의 전자 메일을 입력한 다음 테스트 실행 **을 선택합니다.**

3. 테스트는 모든 테넌트, 사용자 또는 정책 구성을 해결하기 위해 가장 좋은 다음 단계를 반환하여 사용자가 직접 라우팅에 대해 올바르게 구성되었는지 Microsoft Teams.

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>SIP(세션 시작 프로토콜) 옵션 메시지를 사용하여 세션 테두리 컨트롤러의 가용성 모니터링

직접 라우팅은 세션 테두리 컨트롤러에서 전송한 SIP 옵션을 사용하여 SBC 상태 모니터링을 합니다. SIP 옵션 모니터링을 사용하도록 설정하는 데 테넌트 관리자에게 필요한 작업은 없습니다. 수집된 정보는 라우팅 결정을 내릴 때 고려됩니다. 

예를 들어 특정 사용자의 경우 호출을 라우팅하는 데 사용할 수 있는 SBC가 여러 개 있는 경우 직접 라우팅은 각 SBC에서 수신한 SIP 옵션 정보를 고려하여 라우팅을 결정합니다. 

다음 다이어그램은 구성의 예제를 보여줍니다. 

![SIP 옵션 구성 예제입니다.](media/sip-options-config-example.png)

사용자가 +1 425 번호로 전화를 걸면 직접 라우팅이 \<any seven digits> 경로를 평가합니다. 경로에는 두 개의 SBC가 있습니다. sbc1.contoso.com 및 sbc2.contoso.com. 두 SBC 모두 경로에 동일한 우선 순위가 있습니다. SBC를 선택하기 전에 라우팅 메커니즘은 SBC가 SIP 옵션을 마지막으로 보낸 시기를 기준으로 SBC의 상태도 평가합니다. 

호출을 보내는 순간의 통계가 SBC에서 1분마다 옵션을 전송하는 경우 SBC는 정상으로 간주됩니다.  

호출이 설정된 경우 다음 논리가 적용됩니다.

- SBC는 오전 11:00에 페어링됩니다.  
- SBC는 오전 11:01, 오전 11:02에 옵션을 전송합니다.  
- 11:15에서 사용자가 전화를 걸고 라우팅 메커니즘이 이 SBC를 선택합니다. 

직접 라우팅은 일반 간격 옵션을 세 번(일반 간격은 1분)으로 합니다. 지난 3분 동안 옵션이 전송된 경우 SBC가 정상으로 간주됩니다.

예제의 SBC가 오전 11시 12분에서 오전 11시 15분 사이에 옵션을 보낸 경우(통화가 시작된 시간) 정상으로 간주됩니다. 그렇지 않은 경우 SBC가 경로에서 강하됩니다. 

강하는 SBC가 먼저 시도되지 않습니다. 예를 들어 동일한 우선 순위를 sbc1.contoso.com sbc2.contoso.com 수 있습니다.  

이전에 sbc1.contoso.com 주기적으로 SIP 옵션을 보내지 않는 경우 강하됩니다. 다음으로 sbc2.contoso.com 를 호출합니다. sbc2.contoso.con이 호출을 배달할 수 없는 경우 실패가 sbc1.contoso.com 전에 다시 시도됩니다. 

한 경로에서 두 개 이상의 SBC가 정상 및 같음으로 간주되는 Fisher-Yates 셔플이 적용되어 SBC 간에 호출을 분산합니다.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>통화 품질 분석 대시보드 및 SBC 로그 모니터링 
 
특히 초기 페어링 중에 SBC 또는 직접 라우팅 서비스의 잘못 구성과 관련된 문제가 있을 수 있습니다. 

다음 도구를 사용하여 구성을 모니터링할 수 있습니다.  
 
- 통화 품질 대시보드 
- SBC 로그 

직접 라우팅 서비스에는 Call Analytics 또는 SBC 로그에 보고된 매우 설명적인 오류 코드가 있습니다. 

통화 품질 대시보드는 통화 품질 및 안정성에 대한 정보를 제공합니다. Call Analytics를 사용하여 문제 해결 방법에 [](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 대한 자세한 내용은 통화 품질 대시보드를 켜고 사용하는 방법을 참조하세요. Microsoft Teams 및 비즈니스용 Skype 통화 분석을 사용하여 통화 품질 문제를 [해결하세요.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

호출 오류가 발생하면 Call Analytics는 문제 해결에 도움이 되는 표준 SIP 코드를 제공합니다. 

![호출 오류에 대한 샘플 SIP 코드입니다.](media/failed-response-code.png)

그러나 호출 분석은 호출이 직접 라우팅의 내부 구성 요소에 도달하고 실패할 때만 도움이 될 수 있습니다. SBC 페어링에 문제가 있는 경우 또는 SIP "초대"가 거부된 문제(예: 트렁크 FQDN의 이름이 잘못 구성) 호출 분석에 도움이 되지 않습니다. 이 경우 SBC 로그를 참조합니다. 직접 라우팅은 문제에 대한 자세한 설명을 SBC에 전송합니다. 이러한 문제는 SBC 로그에서 읽을 수 있습니다.
