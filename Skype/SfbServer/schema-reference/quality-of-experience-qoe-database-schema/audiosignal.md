---
title: AudioSignal 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 각 레코드는 하나의 끝점에 대한 오디오 신호 메트릭을 표시합니다. 일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 발신자용, 다른 하나는 발신자용입니다.
ms.openlocfilehash: 1e4f7bf92448d4f2efefe3bfad4e1ca556ad44b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761786"
---
# <a name="audiosignal-table"></a>AudioSignal 테이블
 
각 레코드는 하나의 끝점에 대한 오디오 신호 메트릭을 표시합니다. 일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 발신자용, 다른 하나는 발신자용입니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 발신자 데이터  <br/> 1: 발신자 데이터  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타내며, 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |SendSignalLevel을 참조합니다.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |포스트 아날로그 게인 컨트롤 오디오 노이즈 수준을 나타내며, 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |SendNoiseLevel을 참조합니다.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |스피커 렌더링에 대한 5분당 평균 글리치입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |마이크 캡처에 대한 5분당 평균 글리치입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |CPU 클럭을 상대로 마이크 디바이스 클럭 드리프트 속도입니다.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |CPU 클럭을 상대로 스피커 디바이스 클럭 드리프트 속도입니다.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |CPU 클럭을 상대로 스피커 디바이스 클럭 드리프트 속도입니다.  <br/> 통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |통화의 최근 20초 동안의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 음성 스위치 항목의 원인:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 원인은 이러한 개별 원인의 조합일 수 있습니다. ENTER_VS_FORCEORCONVERGENCE 목적으로 regkey에서만 사용할 수 있습니다.  <br/> 이 열의 데이터 형식은 Microsoft Lync Server 2013에서 변경했습니다.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |에코 이벤트의 원인:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 원인은 이러한 개별 원인의 조합일 수 있습니다.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |마이크 캡처 스트림에서 에코가 감지된 시간의 백분율입니다. 일반적으로 헤드셋이나 핸드셋의 경우 값이 낮고 스피커 전화나 독립 실행형 스피커의 경우 값이 높게 설정됩니다. 보드의 음향 에코 취소를 지원하는 장치의 경우 값이 높을수록 에코 누출을 나타냅니다. 다른 장치의 경우 이 메트릭을 사용하여 장치 품질을 평가하면 안 됩니다.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||전송된 스트림에서 에코가 감지되는 시간의 백분율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |게이트웨이에서 중재 서버에 수신된 신호 수준 이는 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 양질의 경우 허용되는 범위는 [-30 ~ -18] dBoV입니다.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |게이트웨이에서 중재 서버에 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |중재 서버 쪽의 AGC(자동 게인 컨트롤)  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |호출의 처음 30초까지 수신된 신호의 RMS(루트 평균 정사각형)입니다.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||채널 1에서 수신된 신호 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||채널 2에서 수신된 신호 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||채널 1에서 수신된 노이즈 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||채널 2에서 수신된 노이즈 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||채널 1에서 전송된 신호 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||채널 2에서 전송된 신호 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||채널 1에서 전송된 노이즈 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||채널 2에서 전송된 노이즈 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||재생을 위해 스피커로 전송되는 신호의 dBFS 수준입니다. 수신된 신호에 대한 게인 조정에 대한 계정입니다. <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||재생을 위해 스피커로 전송되는 신호의 노이즈 콘텐츠 dBFS 수준 <br/> |

