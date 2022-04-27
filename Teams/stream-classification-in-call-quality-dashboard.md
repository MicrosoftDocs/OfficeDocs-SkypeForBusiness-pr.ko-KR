---
title: CQD(통화 품질 대시보드)의 스트림 분류
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Microsoft Teams 및 비즈니스용 Skype Online용 CQD(통화 품질 대시보드)에서 스트림 품질을 분류하는 방법을 알아봅니다.
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059259"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)의 스트림 분류

Microsoft Teams 및 비즈니스용 Skype Online용 CQD(통화 품질 대시보드)를 사용하면 Microsoft Teams 및 비즈니스용 Skype 서비스를 사용하여 수행한 통화 품질에 대한 인사이트를 얻을 수 있습니다. 이 항목에서는 미디어 스트림의 품질 분류에 대한 자세한 정보를 제공합니다. CQD 및 설정 방법에 대한 자세한 내용은 [통화 품질 대시보드 설정을](turning-on-and-using-call-quality-dashboard.md) 참조하세요.

## <a name="classifier-definitions"></a>분류자 정의

CQD의 스트림 사용 가능한 주요 품질 메트릭의 값을 기반으로 _Good_, _Poor_ 또는 _Unclassified_ 로 분류됩니다. 스트림을 분류하는 데 사용되는 메트릭 및 조건은 다음 표에 표시됩니다. CQD의 "잘못된 원인" 차원을 사용하여 _분류_ 불량을 담당하는 메트릭을 파악할 수 있습니다. 이러한 차원에 대한 자세한 내용은 [통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값을 참조하세요](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>오디오 분류자

다음 조건 중 하나 이상이 충족되고 패킷 사용률이 500개 패킷에 > 경우 오디오 스트림이 _불량_ 으로 표시됩니다.

|메트릭|시나리오|조건|설명|
|:-----|:-----|:-----|:-----|
|왕복|모든|> 500|평균 왕복 네트워크 전파 시간(밀리초)입니다. [RFC3550](https://tools.ietf.org/html/rfc3550)에서 사용할 수 있는 세부 정보입니다.|
|패킷 손실률|모든|> 0.1|스트림의 평균 패킷 손실률입니다.|
|지터|모든|> 30|스트림의 평균 지터(밀리초)입니다.|
||||

### <a name="video-classifier-due-to-freeze"></a>동결로 인한 비디오 분류자

비디오 스트림은 최종 사용자가 Frozen Video를 경험했다고 추정하기 위해 생성된 분류자 점수의 값에 따라  _양_ 수 또는 _불량_ 으로 표시됩니다. 이 분류자는 Microsoft Teams 제품에만 사용할 수 있습니다.

|단계 #|메트릭|시나리오|조건 |조건이 True이면 분류 |조건이 False이면 분류 |메트릭을 사용할 수 없는 경우 분류 |설명 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|동결 분류자로 인한 비디오 불량 |서버 쌍이 클라이언트인가요? 서버|>0.246|_가난한_|_좋은_|_분류 되지 않은_|사용자 환경, 동결 기간 통계 및 전반적인 통화 환경의 조합에 따라 생성되는 0에서 1 사이의 점수 |
|2|동결 분류자로 인한 비디오 불량 |서버 쌍이 클라이언트인 경우: 클라이언트|>0.524|_가난한_|_좋은_|_분류 되지 않은_|사용자 환경, 동결 기간 통계 및 전반적인 통화 환경의 조합에 따라 생성되는 0에서 1 사이의 점수 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>비디오 분류자
비디오 스트림은 사용 가능한 첫 번째 메트릭의 값에 따라 다음 순서대로 _양_ 호 또는 _불량_ 으로 표시됩니다.

|단계 #|메트릭|조건 |조건이 True이면 분류 |조건이 False이면 분류 |메트릭을 사용할 수 없는 경우 분류 |설명 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|비디오 로컬 프레임 손실 백분율 평균|> 50% |_가난한_|_좋은_|2단계 진행|사용자에게 표시된 대로 손실된 비디오 프레임의 평균 백분율입니다. 평균에는 네트워크 손실에서 복구된 프레임이 포함됩니다.|
|2|비디오 프레임 속도 평균|< 7|_가난한_|_좋은_|3단계 진행|세션 기간 동안 계산된 비디오 스트림에 대해 수신된 초당 평균 프레임 수입니다.|
|3|비디오 포스트 FECPLR|> 0.15|_가난한_|_좋은_|_분류 되지 않은_|FEC가 적용된 후의 패킷 손실률은 모든 비디오 스트림 및 코덱에서 집계됩니다.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 분류자

VBSS 스트림은 다음 순서로 사용 가능한 첫 번째 메트릭의 값에 따라 _양_ 호 또는 _불량_ 으로 표시됩니다.

|단계 # |메트릭 |조건 |조건이 True이면 분류 |조건이 False이면 분류 |메트릭을 사용할 수 없는 경우 분류 |설명 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|비디오 로컬 프레임 손실 백분율 평균|코덱이 H264S가 아님</br>및</br>StreamDirection이 인바운드입니다.</br></br>FrameLoss가 50% > 경우|_가난한_|_좋은_|_분류 되지 않은_|사용자에게 표시된 대로 손실된 비디오 프레임의 평균 백분율입니다. 평균에는 네트워크 손실에서 복구된 프레임이 포함됩니다. FrameLoss는 인바운드 비 H264S 스트림을 분류하는 데만 사용됩니다.|
|2|비디오 프레임 속도 평균|< 1|_가난한_|_좋은_|_분류 되지 않은_|세션 기간 동안 계산된 비디오 스트림에 대해 수신된 초당 평균 프레임 수입니다. 모든 아웃바운드 스트림 및 H264S용 StreamDirection에 적용됩니다.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>애플리케이션 공유 분류자

다음 조건 중 하나 이상이 충족되면 애플리케이션 공유 스트림이 _불량_ 으로 표시됩니다.

| 메트릭     | 조건 | 설명 |
|:---        |:---       | :--- |
| 버릇없는 타일 백분율 합계 | > 36 | 원격 피어로 전송되는 대신 삭제되는 타일의 백분율입니다(예: MCU에서 뷰어로). 삭제(또는 버릇 없는) 타일은 클라이언트와 서버 간의 대역폭 제한으로 인해 발생할 수 있습니다. |
| AppSharing RDP 타일 처리 대기 시간 평균 | > 400 | 회의 서버의 RDP 스택에서 타일을 처리하는 평균 대기 시간(밀리초)입니다. |
| AppSharing 상대 OneWay 평균 | > 1.75 | 애플리케이션 공유 스트림의 경우 엔드포인트 간의 평균 상대 단방향 지연 시간(초)입니다. |
| | | |

## <a name="unclassified-streams"></a>분류되지 않은 스트림

CQD에서는 ICE(Interactive Connectivity Establishment) 연결이 실패하거나 스트림 분류를 계산하는 데 필요한 모든 메트릭이 보고되지 않은 경우 스트림이 _분류되지_ 않은 것으로 표시됩니다.

ICE 연결 오류를 확인하려면 "First Connectivity Ice" 및 "Second Connectivity Ice" 차원에서 "FAILED" 값을 검사합니다. 두 값 중 하나가 실패를 나타내는 경우 스트림은 _분류되지 않은_ 것으로 표시됩니다.

ICE 연결이 _분류되지 않은_ 스트림에 성공한 경우 키 스트림 메트릭이 보고되지 않았기 때문에 스트림이 _분류되지 않은_ 것으로 간주될 수 있습니다. 이러한 메트릭을 보고하지 않을 수 있는 몇 가지 이유가 있습니다.

- **QoE 보고서를 받지 못했습니다** . 분류에 사용되는 메트릭은 통화가 끝날 때 전송된 QoE 보고서에서 보고됩니다. 이 보고서가 생성되지 않았거나(예: 일부 타사 엔드포인트가 QoE를 보내지 않을 수 있기 때문에) 전송할 수 없는 경우(예: 네트워크 중단으로 인해) CQD는 스트림을 분류할 수 없습니다.

  > [!TIP]
  > "사용 가능한 QoE 레코드" 차원을 사용하여 스트림에 대해 QoE 보고서를 받았는지 여부를 확인할 수 있습니다. 두 엔드포인트에서 QoE 보고서를 받은 경우 이 차원의 값은 "True"입니다. 메트릭을 가장 정확하게 보고하려면 두 엔드포인트의 QoE 보고서가 필요합니다.

- **짧은 호출** - 짧은 호출에는 키 스트림 메트릭을 계산하기에 충분한 미디어 활동이 없을 수 있습니다. 이러한 메트릭이 없으면 CQD에서 스트림을 분류할 수 없습니다.

  > [!TIP]
  > "기간(초)", "기간(분)", "기간 5초 이하", "기간 60초 이상" 차원을 사용하여 스트림의 기간을 확인할 수 있습니다. 측정 "평균 호출 기간"을 사용하여 스트림 집합의 평균 기간을 계산할 수도 있습니다.

- **낮은 패킷 사용률** - "짧은 호출" 시나리오와 마찬가지로 키 스트림 메트릭을 계산하려면 충분한 패킷 사용률이 필요합니다. 이러한 메트릭이 없으면 CQD에서 스트림을 분류할 수 없습니다.
  - 일반적인 낮은 패킷 사용률 시나리오는 참석자가 모임에 참가하여 발표자의 말을 듣지 않을 때 발생합니다(대부분의 통화에 대해 마이크가 음소거됨). 여기서 클라이언트에 대한 오디오 스트림 인바운드는 패킷 사용률이 높지만 클라이언트의 오디오 스트림 아웃바운드에는 패킷 사용률이 거의 또는 전혀 없습니다. 스트림의 기간은 1시간 이상일 수 있지만 마이크가 음소거된 이후 클라이언트에서 서버로 스트림의 패킷 사용률이 낮고 _분류되지 않은_ 스트림 결과가 발생합니다.

  > [!TIP]
  > "패킷 사용률" 차원 및 "평균 패킷 사용률" 측정값을 사용하여 스트림의 패킷 활동을 확인할 수 있습니다.

## <a name="related-topics"></a>관련 항목
[Teams 대한 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Power BI 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
