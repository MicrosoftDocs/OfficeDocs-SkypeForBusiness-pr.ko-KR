---
title: 비즈니스용 Skype 서버에서 파일 공유 고가용성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 비즈니스용 Skype 서버에서 DFS를 사용 하 여 파일 공유의 가용성을 확보 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 56a6e1008935bc0d38d65e2355826634709aed27
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196888"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 파일 공유 고가용성
 
비즈니스용 Skype 서버에서 DFS를 사용 하 여 파일 공유의 가용성을 확보 하는 방법에 대해 알아보세요.
  
비즈니스용 Skype 서버 배포에서 파일 공유를 위한 고가용성을 보장 하기 위해 DFS (분산 파일 시스템)를 사용할 수 있습니다. DFS는 같은 데이터 센터 내에서 한 파일 서버에서 다른 파일로 장애 조치를 지원 합니다. 대규모 배포의 경우 DFS를 사용 하는 전용 파일 서버를 사용 하는 것이 좋습니다. Windows Server 2012의 DFS에 대 한 자세한 내용은을 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)참조 하세요. Windows Server 2008의 DFS에 대 한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)을 참조 하세요.
  
네트워크 크기와 원하는 복원 력 크기에 따라 한 쌍의 서버를 사용 하 여 사이트의 모든 파일 공유를 호스팅하거나 프런트 엔드 당 하나의 쌍을 사용할 수 있습니다.
  
DFS는 게시 된 RTO (복구 시간 목표) 또는 RPO (복구 시점 목표) 약정 없이 최상의 파일 복제 메커니즘입니다. DFS 서버 간의 장애 조치를 빠르게 완료 해야 하지만 데이터 복제 지연으로 인해 장애 조치가 발생할 때 사용자가 진행 중인 작업을 계속할 수 없습니다.
  
DFS를 사용 하는 경우 파일 공유에 있는 데이터 저장소가 중요 한 경우 4 시간에 한 번, 예를 들어 사용자를 자주 백업 하는 것이 좋습니다. 한 파일 공유가 다운 되 고 복제가 최신 상태가 아닌 경우 백업을 사용 하 여 실패 한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 쌍을 이루는 다른 서버로 복원할 수 있습니다.
  

