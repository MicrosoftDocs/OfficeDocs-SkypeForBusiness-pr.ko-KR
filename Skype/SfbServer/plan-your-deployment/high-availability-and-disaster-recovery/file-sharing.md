---
title: 파일 공유 고가용성 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: DFS를 사용하여 비즈니스용 Skype 서버 공유의 고가용성을 보장하는 방법을 알아보는 방법을 배워야 합니다.
ms.openlocfilehash: 6abdf9656ddca5148c9b04c6dbe11cdc5da7e840
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603817"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>파일 공유 고가용성 비즈니스용 Skype 서버
 
DFS를 사용하여 비즈니스용 Skype 서버 공유의 고가용성을 보장하는 방법을 알아보는 방법을 배워야 합니다.
  
배포에서 파일 공유에 대한 고가용성을 비즈니스용 Skype 서버 DFS(분산 파일 시스템)를 사용할 수 있습니다. DFS는 한 파일 서버에서 동일한 데이터 센터 내에 있는 다른 파일 서버로의 장애 조치(failover)를 지원합니다. 대규모 배포의 경우 DFS를 사용하여 한 쌍으로 구성한 전용 파일 서버를 사용하는 것이 좋습니다. DFS에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) Windows Server 2012. Windows Server 2008의 DFS에 대한 자세한 내용은 을 [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) 참조하세요.
  
네트워크 규모와 원하는 복원력 수준에 따라 한 쌍의 서버로 사이트의 모든 파일 공유를 호스팅할 수도 있고 프런트 엔드 풀당 한 쌍의 서버를 사용할 수도 있습니다.
  
DFS는 공표된 RTO(복구 시간 목표) 또는 RPO(복구 시점 목표)가 없는 "최상의 노력" 파일 복제 메커니즘입니다. DFS 서버 간의 장애 조치(failover)는 빠르게 완료해야 하지만 데이터 복제 지연으로 인해 장애 조치(failover)가 발생할 때 사용자가 진행되는 작업을 계속할 수 없습니다.
  
DFS를 사용하는 경우 파일 공유의 데이터 저장소가 중요한 경우 파일 공유를 4~8시간마다 자주 백업해야 합니다. 한 파일 공유가 다운되고 복제가 최신 상태가 아닌 경우 백업을 사용하여 장애가 발생한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 한 쌍으로 구성된 다른 서버로 복원할 수 있습니다.
