---
title: 샘플 QoE 데이터베이스 쿼리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: 이 섹션에는 체감 품질 (환경 품질) 데이터베이스에 대 한 샘플 쿼리가 포함 되어 있습니다.
ms.openlocfilehash: 42000bfe28acde629165009bbb7b6c33d15f8cdb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196530"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="d6cba-103">샘플 QoE 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="d6cba-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="d6cba-104">이 섹션에는 체감 품질 (환경 품질) 데이터베이스에 대 한 샘플 쿼리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6cba-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="d6cba-105">다음 예제를 사용 하 여 모든 오디오 스트림에 대 한 지터 및 패킷 손실 평균을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6cba-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="d6cba-106">다음 예제를 사용 하 여 모임 콘솔을 사용 하는 총 회의 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6cba-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="d6cba-107">다음 예제를 사용 하 여 캡처 장치 당 ConversstionalMOS, SendingMOS 및 ListendingMOS를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6cba-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```
