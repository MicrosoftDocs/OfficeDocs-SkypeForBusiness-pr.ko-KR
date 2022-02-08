---
title: '2019년 가상화 비즈니스용 Skype 서버 지원 '
ms.reviewer: corbinm
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: '요약: 2019년 2019에 대한 가상화 지원에 대해 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 87263c4204cddbcd5e64cfeb6709b88bb94c2a60
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392260"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>2019년 가상화 비즈니스용 Skype 서버 지원

비즈니스용 Skype 서버 2019는 가상화에서 지원됩니다.

가상화가 지원되는 동안 몇 가지 주요 사항도 기억해야 합니다.

- 가상 CPU와 실제 CPU의 1:1 비율을 유지 관리합니다.
- 게스트 서버가 작동되는 동안에는 이동하지 않습니다.
- 라이브 시스템 마이그레이션 및 가상 컴퓨터의 이식성은 지원되지 않습니다.
- 모든 호스트에서 하이퍼스레딩을 사용하지 않도록 설정
- 호스트 서버에서 동적 메모리를 구성하지 않습니다.
- 동적 디스크 대신 고정 또는 통과 디스크를 사용 합니다.
- 가상 게스트에 필요한 것 이상으로 하이퍼바이저에 6-10% 오버헤드를 허용합니다.

## <a name="supported-hypervisors"></a>지원되는 하이퍼바이터

SfB Server 2019는 Windows Server 2016 Server 2019에서 Windows 지원됩니다.

타사 하이퍼바이어의 경우 관련 OS에 대한 SVVP(서버 가상화 유효성 검사 프로그램) 테스트를 통과한 하이퍼바이서가 필요합니다.

- SVVP [Windows Server 2016 버전](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 목록을 참조하세요.
- SVVP [Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 버전을 참조하세요.

## <a name="stress-and-performance-tool"></a>스트레스 및 성능 도구

비즈니스용 Skype 서버 2019 스트레스 및 성능 도구에는 2019년의 용량 계획을 간소화하는 비즈니스용 Skype 서버 포함되어 있습니다. 2019 비즈니스용 Skype 서버 및 성능 도구를 통해 다음을 할 수 있습니다.

- 2019년 하드웨어 계획 비즈니스용 Skype 서버 간소화
- 성능 조정을 위한 더 많은 지식과 모범 사례를 제공합니다.
- 의도한 2019년 배포의 비즈니스용 Skype 서버 측정
 
여기에서 도구를 다운로드할 수 [있습니다](https://www.microsoft.com/download/details.aspx?id=101447).
