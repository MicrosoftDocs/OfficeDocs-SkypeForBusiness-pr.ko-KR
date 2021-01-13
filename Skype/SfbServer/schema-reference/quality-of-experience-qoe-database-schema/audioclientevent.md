---
title: AudioClientEvent 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 각 레코드에는 오디오 호출의 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다. 일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809688"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 테이블
 
각 레코드에는 오디오 호출의 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다. 일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 발신자 데이터  <br/> 1: 발신자 데이터  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |NetworkSendQuality 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다.  <br/> 지터나 패킷 손실 측면에서 네트워크 품질은 심각하며 전송되는 오디오 품질에 영향을 미치게 됩니다.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |ReceiveSendQuality 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다.  <br/> 지터나 패킷 손실 측면에서 네트워크 품질은 심각하며 수신되는 오디오 품질에 영향을 미치게 됩니다.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Delay 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 네트워크 대기 시간이 심각하며 대화형 통신을 방지하여 환경에 영향을 미치기  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |LowBandwidth 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 사용 가능한 음성 환경의 경우 사용 가능한 대역폭이 부족합니다.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |부족한 CPU 이벤트가 '불량' 상태로 발생된 세션의 비율입니다. 현재 사용 중인 모달 및 응용 프로그램으로 처리하기 위한 CPU 주기가 부족합니다. 이로 인해 오디오 채널이 왜곡됩니다.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceHalfDuplexAEC 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 에코를 방지하기 위해 시스템은 반이이면 입력합니다.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceRenderNotFunctioning 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 현재 세션에 사용 중인 렌더링 장치가 제대로 작동하지 않습니다. 이로 인해 단방형 오디오 문제가 발생할 수 있습니다.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceCaptureNotFunctioning 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 현재 세션에 사용 중인 캡처 장치가 제대로 작동하지 않습니다. 이로 인해 단방형 오디오 문제가 발생할 수 있습니다.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceGlitches 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 오디오 렌더링 시 심각한 문제로 인해 왜곡이 발생할 수 있습니다. 이러한 불량은 드라이버 문제, 지연된 프로시저 호출(DPC) 스와일드(drivers) 및 높은 CPU 사용량으로 인해 발생할 수 있습니다.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSNR 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 캡처 품질이 매우 불량하거나, 매우 시선이 좋거나 사용자가 마이크에서 너무 멀리 멀어지거나 말하고 있습니다. 이로 인해 왜곡이 발생할 수 있습니다.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceLowSpeechLevel 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 사용자의 음성 수준이 너무 낮고 시스템에서 이를 더 이상 늘일 수 없습니다. 이로 인해 왜곡이 발생하거나 단방형 오디오로 인식될 수 있습니다.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |DeviceClipping 이벤트가 '나쁜' 상태로 발생한 세션의 백분율입니다.  <br/> 주변 음성이 마이크를 잘라내면 클리핑으로 인한 왜곡이 극단에서 들리게 됩니다. 주변 마이크 클리핑은 피해야 합니다.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceEchoEvent 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 장치 또는 설정으로 인해 시스템이 보완할 수 없는 에코가 발생하고 있습니다.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |DeviceNearEndToEchoRatio 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 사용자의 음성이 캡처되는 에코에 비해 너무 낮아 사용자를 방해하는 것이 얼마나 쉬운지 제한하기 때문에 사용자 환경에 영향을 미치게 됩니다. 스피커 볼륨을 줄이고 마이크를 발신자에 가깝게 움직입니다.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||세션 중 DeviceMultipleEndpoints 이벤트가 '나쁜' 상태로 발생된 횟수입니다. 동일한 세션에서 여러 오디오 끝점이 검색되고 시스템이 렌더링 볼륨을 줄여 보완했습니다.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |세션 중 DeviceHowlingEvent 이벤트가 '나쁜' 상태로 발생된 횟수입니다. 오디오 피드백 루프가 검색되었습니다(오디오 경로를 공유하는 여러 끝점으로 인해 발생).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderZeroVolume 이벤트가 "불량" 상태인 세션의 비율입니다. 렌더링 장치가 볼륨 0으로 설정되어 있습니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||DeviceRenderMute 이벤트가 "불량" 상태인 세션의 비율입니다. 렌더링 장치가 음소거됩니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
   

