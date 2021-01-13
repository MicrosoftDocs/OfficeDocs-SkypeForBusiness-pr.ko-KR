---
title: VideoClientEvent 테이블
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 각 레코드에는 비디오 통화에서 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다. 일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821398"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 테이블
 
각 레코드에는 비디오 통화에서 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다. 일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 발신자 데이터  <br/> 1: 발신자 데이터  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |LowBandwidth 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다. 사용 가능한 음성 환경의 경우 사용 가능한 대역폭이 부족합니다.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |ReceiveSendQuality 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다.  <br/> 지터나 패킷 손실 측면에서 네트워크 품질은 심각하며 수신되는 오디오 품질에 영향을 미치게 됩니다.  <br/> |
   

