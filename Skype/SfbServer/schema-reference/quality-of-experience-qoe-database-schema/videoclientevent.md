---
title: VideoClientEvent 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다. 일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804996"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 테이블
 
각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다. 일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**FromCaller** <br/> |다소  <br/> |주요한  <br/> |0: 피호출자의 데이터  <br/> 1: 발신자의 데이터  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |세션 백분율 \ \ \ \에 대 한 \ \ \ n 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 사용할 수 있는 대역폭이 불충분 한 음성 환경에 적합 하지 않습니다.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |세션 백분율 ReceiveSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.  <br/> 지터 또는 패킷 손실 측면의 네트워크 품질은 심각 하며 수신 되는 오디오 품질에 영향을 줍니다.  <br/> |
   

