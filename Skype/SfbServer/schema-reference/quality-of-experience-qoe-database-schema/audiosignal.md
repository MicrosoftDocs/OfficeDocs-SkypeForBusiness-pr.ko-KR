---
title: AudioSignal 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 각 레코드는 한 끝점에 대 한 오디오 신호 메트릭을 나타냅니다. 일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 호출자를 위한 것이 고 하나는 피호출자 용입니다.
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196582"
---
# <a name="audiosignal-table"></a>AudioSignal 테이블
 
각 레코드는 한 끝점에 대 한 오디오 신호 메트릭을 나타냅니다. 일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 호출자를 위한 것이 고 하나는 피호출자 용입니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**FromCaller** <br/> |다소  <br/> |주요한  <br/> |0: 피호출자의 데이터  <br/> 1: 발신자의 데이터  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |SendSignalLevel을 참조 하세요.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |아날로그 후 게인 제어 오디오 노이즈 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |SendNoiseLevel을 참조 하세요.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |반향 반환 손실 보정 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |마이크 캡처에 대 한 5 분 당 평균 결함. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |10 진수 (9, 2)  <br/> | <br/> |CPU 클록을 기준으로 한 마이크 장치 시계 드리프트 속도입니다.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |10 진수 (9, 2)  <br/> | <br/> |CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |10 진수 (9, 2)  <br/> | <br/> |CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.  <br/> 평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |10 진수 (9, 2)  <br/> | <br/> |평균 스피커는 호출의 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 음성 전환 항목의 원인:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 원인은 이러한 개별적인 원인을 조합 했을 수 있습니다. ENTER_VS_FORCEORCONVERGENCE는 테스트 용도의 regkey 에서만 사용 하도록 설정할 수 있습니다.  <br/> Microsoft Lync Server 2013에서이 열의 데이터 형식이 변경 되었습니다.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |에코 이벤트의 원인:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 원인은 이러한 개별적인 원인을 조합 했을 수 있습니다.  <br/> |
|**EchoPercentMicIn** <br/> |10 진수 (5, 2)  <br/> | <br/> |마이크 캡처 스트림에 화면 표시가 감지 된 시간의 백분율입니다. 일반적으로 헤드셋 이나 송수화기의 경우 값은 낮고 스피커 전화 또는 독립 실행형 스피커는 더 높습니다. 화상 음향 반향 제거를 지 원하는 디바이스의 경우 높은 값은 에코 누수를 나타냅니다. 다른 디바이스의 경우이 메트릭은 장치 품질을 평가 하는 데 사용해 서는 안 됩니다.  <br/> |
|**EchoPercentSend** <br/> |10 진수 (5, 2)  <br/> ||전송 된 스트림에서 반향을 감지 하는 시간 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |중재 서버 쪽의 AGC (자동 게인 컨트롤)  <br/> |
|**InitialSignalLevelRMS** <br/> |o  <br/> | <br/> |호출의 처음 30 초까지 들어오는 신호에 대 한 루트 평균 사각형 (RMS)입니다.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||채널 1에서 받은 신호 수준  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||채널 2에서 받은 신호 수준  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||채널 1에서 받은 소음 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||채널 2에서 받은 소음 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||채널 1에서 전송 되는 신호 수준  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||채널 2에서 전송 되는 신호 수준  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||채널 1에서 전송 되는 소음 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||채널 2에서 전송 된 소음 수준입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||재생을 위해 스피커에 전송 되는 신호 중 dBFS의 수준입니다. 받은 신호에 대 한 게인 조정을 위한 계정 <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||재생을 위해 스피커에 전송 된 신호에 있는 노이즈 콘텐츠의 dBFS 수준 <br/> |

