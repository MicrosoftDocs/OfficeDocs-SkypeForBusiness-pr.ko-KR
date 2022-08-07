---
title: CQD PSTN 직접 라우팅 보고서 사용
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Microsoft Teams CQD(통화 품질 대시보드) PSTN 직접 라우팅 보고서를 사용하여 Microsoft Teams에서 PSTN 통화를 모니터링하고 문제를 해결합니다.
ms.openlocfilehash: 7b7205658358cfa3aa90824718c03731fa33a534
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270713"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>CQD PSTN 직접 라우팅 보고서 사용

Microsoft Teams CQD(통화 품질 대시보드) PSTN 직접 라우팅 보고서는 [CQD용 다운로드 가능한 Power BI 쿼리 템플릿](https://www.microsoft.com/download/details.aspx?id=102291)에서 사용할 수 있습니다. 


CQD PSTN 직접 라우팅 보고서(CQD PSTN 직접 라우팅 Report.pbit)를 사용하면 PSTN 서비스의 사용 패턴과 품질을 이해할 수 있습니다. 이 보고서를 사용하여 서비스 사용량, SBC(세션 테두리 컨트롤러), 전화 통신 서비스, 네트워크 매개 변수 및 네트워크 효율성 비율 세부 정보에 대한 정보를 모니터링합니다. 이 정보는 통화 중단 이유를 포함하여 문제를 식별하는 데 도움이 될 수 있습니다. 예를 들어 볼륨이 떨어질 때 또는 영향을 받는 호출 수 및 이유를 확인할 수 있습니다.


CQD PSTN 직접 라우팅 보고서에는 다음 네 개의 섹션이 있습니다.

  - [PSTN 개요](#pstn-overview)

  - [서비스 세부 정보](#service-details)

  - [네트워크 효율성 비율](#network-effectiveness-ratio)

  - [네트워크 매개 변수](#network-parameters)

## <a name="highlights"></a>하이라이트

1. 통화 유형, SBC, 호출자 및 호출 수신자 국가별 분석

   CQD PSTN 직접 라우팅 보고서는 지난 7일, 30일 또는 180일(6개월)동안 테넌트의 모든 SCC에 대한 안정성 및 사용량 메트릭을 집계합니다. 통화 유형, SBC, 발신자 및 호출 수신자 국가별로 데이터를 분석할 수 있습니다. 특정 SBC 또는 국가에 관심이 있는 경우 선택한 시간 범위에 대한 추세의 변화를 식별할 수 있습니다.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 직접 라우팅 보고서에서 사용할 수 있는 필터의 스크린샷.":::
   
2. 추세 추적

    추세 분석은 서비스 사용량 및 안정성을 이해하려고 할 때 필수적입니다. 시간별 추세는 실시간 인시던트 식별에 도움이 되는 일일 성능을 자세히 살펴봅니다. 일상적인 추세를 통해 장기적인 관점에서 서비스 상태를 확인할 수 있습니다. 적절한 데이터 세분성을 사용하여 두 모드 간에 전환할 수 있어야 합니다. CQD PSTN 직접 라우팅 보고서는 각 수준에서 성능을 분석할 수 있도록 6개월 추세 개요, 7일 및 30일 일일 추세 및 시간별 추세를 제공합니다.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 직접 라우팅 보고서의 추세 그래프 스크린샷":::

3. SBC 또는 사용자 수준으로 드릴스루

   SBC 또는 사용자 수준에서 사용량 또는 안정성 배포를 신속하게 이해할 수 있도록 CQD의 여러 데이터 범주에 대한 드릴스루 기능을 구축해 왔습니다. 드릴스루를 사용하면 문제를 신속하게 파악하고 실제 사용자 영향을 이해할 수 있습니다. CQD PSTN 직접 라우팅 보고서는 서비스 세부 정보 및 네트워크 효율성 비율 메트릭에 대한 드릴스루 기능을 제공합니다. SBC 또는 사용자 수준 세부 정보로 드릴스루하려는 데이터 지점을 클릭합니다.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="데이터 요소의 드릴스루 기능을 보여 주는 스크린샷":::


## <a name="pstn-overview"></a>PSTN 개요

CQD PSTN 직접 라우팅 보고서는 지난 180일 동안 서비스의 전반적인 상태와 관련된 다음 정보를 제공합니다.
![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report1.png)

예를 들어 SBC를 통해 진행되는 모든 인바운드 통화에 대한 전반적인 사용량 및 상태에 관심이 있는 경우 내부 국가로서 미국과 abc.bca.adatum.biz.

| **전화 걸기** | **설명**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 맨 위에 있는 필터를 사용하여 ByotIn을 호출 유형, abc.bca.contoso.com 세션 보더 컨트롤러로, 미국을 내부 국가로 드릴다운하고 선택할 수 있습니다. |
| 2            | 지난 180일 동안의 사용 추세입니다. 서비스 세부 정보 페이지에서 사용량 세부 정보 보고서를 찾을 수 있습니다.                                                                     |
| 3            | 지난 180일 동안의 Post Dial Delay, Latency, Jitter 및 Packet Loss 추세입니다. 네트워크 매개 변수 페이지에서 세부 보고서를 찾을 수 있습니다.                           |
| 4            | 지난 180일 동안의 동시 통화 및 일별 활성 사용자 추세입니다. 이 차트는 서비스의 최대 볼륨을 이해하는 데 도움이 될 수 있습니다.                            |
| 5            | 상위 통화 종료 이유는 지난 180일 동안 서비스 품질에 영향을 미쳤습니다. NER(네트워크 유효 비율) 페이지에서 서비스 상태 세부 정보를 찾을 수 있습니다.                    |

## <a name="service-details"></a>서비스 세부 정보

이 페이지에서는 일일 서비스 사용량 추세와 지리적으로 사용자 피드백 분석을 제공합니다.

  - **총 시도 호출 –** 성공 및 실패 호출을 포함하여 해당 시간 범위의 총 시도 호출

  - **총 연결된 호출 -** 해당 시간 범위의 총 연결된 호출 수

  - **총 시간(분) –** 해당 시간 범위의 총 분 사용량

  - **DAU(일일 활성 사용자) –** 해당 날짜에 하나 이상의 연결된 통화를 한 일일 활성 사용자 수

  - **동시 호출 –** 1분 내 최대 동시 활성 호출 수

  - **사용자 피드백 –** "내 통화 평가" 점수는 사용자로부터 제공됩니다. 3-5는 좋은 호출로 간주됩니다. 1-2는 잘못된 호출로 간주됩니다.

![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report2.png)

예를 들면 다음과 같습니다.

1.  2020년 2월 14일의 평균 통화 기간이 0으로 떨어지면 먼저 호출 볼륨이 정상으로 보이는지 확인하고 총 연결 호출과 총 시도 호출 간에 큰 불일치가 있는지 확인할 수 있습니다. 그런 다음, 네트워크 효율성 비율 페이지로 이동하여 통화 실패 이유에 투자합니다.

2.  사용자 피드백 맵에 빨간색 반점이 증가하는 경우 네트워크 효율성 비율 페이지 및 네트워크 매개 변수로 이동하여 변칙이 있는지 확인하고 MS Service Desk를 사용하여 티켓을 올릴 수 있습니다.

## <a name="network-effectiveness-ratio"></a>네트워크 효율성 비율

이는 전체 상태 대시보드에 표시되는 것과 동일한 메트릭입니다. 시간별 네트워크 효율성 비율 및 통화 종료 이유 차트에서 두 통화 방향(인바운드/아웃바운드)에 대해 영향을 받는 호출 세부 정보가 포함된 시간별 NER 번호를 확인할 수 있습니다.

  - **NER** - 수신자에게 전달된 통화 수와 보낸 통화 수를 측정하여 통화를 배달하는 네트워크의 기능(%)입니다.

  - **SIP 응답 코드** - 3자리 정수 응답 코드는 호출 상태를 표시합니다.

  - **Microsoft 응답 코드**-Microsoft 구성 요소에서 보낸 응답 코드입니다.

  - **설명** – SIP 응답 코드 및 Microsoft 응답 코드에 해당하는 이유 단계입니다.

  - **영향을 받는 호출 수** – 선택한 시간 범위 동안 영향을 받은 총 통화 수입니다.

> ![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report3.png)
> 
예를 들면 다음과 같습니다.

![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report4.png)

Daily NER가 2020/02/05에 급락한 경우 날짜를 클릭하면 다른 차트가 해당 특정 날짜로 확대됩니다.

![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report5.png)

매시간 NER 양호한 백분율 추세 21:00 경에 딥이 발생하는 것을 확인할 수 있습니다. 그런 다음 다시 클릭하여 21시간으로 확대하고 효과 있는 통화 세부 정보를 확인하여 해당 시간에 실패한 통화 수와 통화 종료 이유가 무엇인지 확인합니다. 문제가 SBC와 관련이 없는 경우 SBC 문제 또는 Service Desk에 보고하는 자체 문제부터 시작할 수 있습니다.

## <a name="network-parameters"></a>네트워크 매개 변수

모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 테두리 컨트롤러로 측정됩니다. 권장 값에 대한 자세한 내용은 [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md) 및 Customer Edge에서 Microsoft Edge로의 권장 값을 참조하세요.

  - **지터** – RTCP(RTP 제어 프로토콜)를 사용하여 두 엔드포인트 간에 계산되는 네트워크 전파 지연 시간 변동의 밀리초 측정값입니다.

  - **패킷 손실** – 도착하지 못한 패킷의 측정값입니다. 두 엔드포인트 간에 계산됩니다.

  - **대기 시간** -(왕복 시간이라고도 함)은 신호를 보내는 데 걸리는 시간과 해당 신호를 수신하는 데 걸리는 시간입니다. 이 시간 지연은 신호의 두 지점 간의 전파 시간으로 구성됩니다.

> ![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report6.png)

예를 들면 다음과 같습니다.

특정 날짜(예: 2020년 2월 14일의 대기 시간)에 대한 4개 차트(대기 시간, 지터, 패키지 손실률, 사후 다이얼 지연)가 급증하면 날짜 지점을 클릭합니다. 아래쪽의 시간별 추세 차트는 시간별 숫자를 표시하도록 새로 고쳐집니다. MS Service Desk를 사용하여 SCC를 확인하거나 티켓을 올릴 수 있습니다.

![스크린샷: PSTN CQD 보고서.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>관련 항목

[Power BI를 사용하여 Microsoft Teams용 CQD 데이터 분석](CQD-PSTN-report.md)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
