---
title: A/V MCU 풀 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 배치된 A/V 회의 서비스가 없는 중앙 사이트의 모든 Enterprise Edition 프런트 엔드 서버에서는 동일한 독립 실행형 A/V 회의 풀을 사용할 수 있습니다. 각 A/V 회의 풀에 대해 풀의 FQDN(정규화된 도메인 이름) 및 해당 풀에 단일 A/V 회의 서버만 있는지 아니면 다중 부하 분산 A/V 회의 서버가 있는지를 지정해야 합니다.
ms.openlocfilehash: 114d67f6643fe2629cf3a6c1a72daa70eb2db65f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626870"
---
# <a name="add-av-mcu-pool"></a>A/V MCU 풀 추가
 
배치된 A/V 회의 서비스가 없는 중앙 사이트의 모든 Enterprise Edition 프런트 엔드 서버에서는 동일한 독립 실행형 A/V 회의 풀을 사용할 수 있습니다. 각 A/V 회의 풀에 대해 풀의 FQDN(정규화된 도메인 이름) 및 해당 풀에 단일 A/V 회의 서버만 있는지 아니면 다중 부하 분산 A/V 회의 서버가 있는지를 지정해야 합니다.
  
> [!IMPORTANT]
> 단일 서버 풀을 다중 서버 풀로 전환할 수는 없습니다. 나중에 조직에 다중 서버 풀이 필요하다고 판단하는 경우 단일 서버 풀을 삭제한 다음 다중 서버 풀을 추가해야 합니다. 
  
> [!TIP]
> 나중에 A/V 회의 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다. 풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 더 추가할 준비가 된 경우 토폴로지 작성기에서 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 A/V 회의 풀 구성원을 설정해야 합니다. A/V 회의 서버 풀은 풀을 만들기 위해 부하 분산 장치가 필요하지 않다는 점에서 고유합니다. A/V 회의 풀은 내부적으로 부하 분산을 수행하며 추가 하드웨어가 필요하지 않습니다. 
  

