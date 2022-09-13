---
title: 직접 라우팅 모니터링
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
description: 세션 테두리 컨트롤러, 직접 라우팅 구성 요소 및 Telecom 트렁크를 포함하여 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657248"
---
# <a name="monitor-direct-routing"></a>직접 라우팅 모니터링

이 문서에서는 직접 라우팅 구성을 모니터링하고 문제를 해결하는 방법을 설명합니다. 

직접 라우팅을 사용하여 전화를 걸고 수신하는 기능에는 다음 구성 요소가 포함됩니다. 

- 세션 테두리 컨트롤러(SCC) 
- Microsoft 클라우드의 직접 라우팅 구성 요소 
- 통신 트렁크 

문제 해결에 어려움이 있는 경우 SBC 공급업체 또는 Microsoft에서 지원 사례를 열 수 있습니다. 

Microsoft는 문제 해결 및 모니터링을 위한 더 많은 도구를 제공하기 위해 노력하고 있습니다. 정기적으로 설명서에서 업데이트를 확인합니다. 

## <a name="troubleshoot-direct-routing"></a>직접 라우팅 문제 해결

직접 라우팅 문제를 해결하려면 직접 라우팅 [관련 문제 진단을 참조하세요](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>SIP(세션 시작 프로토콜) 옵션 메시지를 사용하여 세션 테두리 컨트롤러의 가용성 모니터링

직접 라우팅은 세션 테두리 컨트롤러에서 보낸 SIP 옵션을 사용하여 SBC 상태를 모니터링합니다. SIP 옵션 모니터링을 사용하도록 설정하려면 테넌트 관리자가 수행해야 하는 작업이 없습니다. 수집된 정보는 라우팅 결정을 내릴 때 고려됩니다. 

예를 들어 특정 사용자의 경우 통화를 라우팅하는 데 사용할 수 있는 여러 SBC가 있는 경우 직접 라우팅은 라우팅을 결정하기 위해 각 SBC에서 받은 SIP 옵션 정보를 고려합니다. 

다음 다이어그램은 구성의 예를 보여줍니다. 

![SIP 옵션 구성 예제입니다.](media/sip-options-config-example.png)

사용자가 숫자 +1 425 \<any seven digits>를 호출하면 직접 라우팅이 경로를 평가합니다. 경로에는 sbc1.contoso.com 및 sbc2.contoso.com 두 개의 SCC가 있습니다. 두 SCC 모두 경로에서 동일한 우선 순위를 갖습니다. SBC를 선택하기 전에 라우팅 메커니즘은 SBC가 SIP 옵션을 마지막으로 보낸 시기에 따라 SBC의 상태를 평가합니다. 

SBC가 호출을 보내는 순간 통계에서 SBC가 매분마다 옵션을 보내는 것으로 표시되는 경우 SBC는 정상으로 간주됩니다.  

호출이 수행되면 다음 논리가 적용됩니다.

- SBC는 오전 11:00에 페어링되었습니다.  
- SBC는 오전 11:01, 오전 11:02 등에 옵션을 보냅니다.  
- 11:15에 사용자가 전화를 걸고 라우팅 메커니즘이 이 SBC를 선택합니다. 

직접 라우팅은 일반 간격 옵션을 세 번 사용합니다(일반 간격은 1분). 지난 3분 동안 옵션이 전송된 경우 SBC는 정상으로 간주됩니다.

예제의 SBC가 오전 11시 12분에서 오전 11시 15분(통화한 시간) 사이에 옵션을 보낸 경우 정상으로 간주됩니다. 그렇지 않으면 SBC가 경로에서 강등됩니다. 

강등은 SBC가 먼저 시도되지 않음을 의미합니다. 예를 들어 sbc1.contoso.com 우선 순위가 같은 sbc2.contoso.com 있습니다.  

sbc1.contoso.com 앞에서 설명한 대로 정기적으로 SIP 옵션을 보내지 않으면 강등됩니다. 다음으로, sbc2.contoso.com 호출을 시도합니다. sbc2.contoso.con이 호출을 전달할 수 없는 경우 오류가 생성되기 전에 sbc1.contoso.com(강등)가 다시 시도됩니다. 

한 경로에 있는 두 개 이상의 SCC가 정상 및 같음으로 간주되는 경우 Fisher-Yates 순서 섞기를 적용하여 SCC 간에 호출을 분산합니다.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>통화 품질 분석 대시보드 및 SBC 로그 모니터링 
 
경우에 따라 특히 초기 페어링 중에 SCC 또는 직접 라우팅 서비스의 잘못된 구성과 관련된 문제가 있을 수 있습니다. 

다음 도구를 사용하여 구성을 모니터링할 수 있습니다.  
 
- 통화 품질 대시보드 
- SBC 로그 

직접 라우팅 서비스에는 Call Analytics 또는 SBC 로그에 보고된 설명 오류 코드가 있습니다.

통화 품질 대시보드는 통화 품질 및 안정성에 대한 정보를 제공합니다. 통화 분석을 사용하여 문제를 해결하는 방법에 대한 자세한 내용은 [Microsoft Teams 및 비즈니스용 Skype Online용 통화 품질 대시보드 켜기 및 사용을](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 참조하고 [통화 분석을 사용하여 통화 품질 저하 문제를 해결](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)하세요. 

호출 실패의 경우 Call Analytics는 문제 해결에 도움이 되는 표준 SIP 코드를 제공합니다. 

![호출 실패에 대한 샘플 SIP 코드입니다.](media/failed-response-code.png)

그러나 호출 분석은 호출이 직접 라우팅의 내부 구성 요소에 도달하고 실패하는 경우에만 도움이 될 수 있습니다. SBC 페어링에 문제가 있거나 SIP "초대"가 거부된 문제(예: 트렁크 FQDN의 이름이 잘못 구성됨)의 경우 Call Analytics가 도움이 되지 않습니다. 이 경우 SBC 로그를 참조하세요. 직접 라우팅은 SCC에 문제에 대한 자세한 설명을 보냅니다. 이러한 문제는 SBC 로그에서 읽을 수 있습니다.
