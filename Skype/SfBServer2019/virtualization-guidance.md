---
title: '비즈니스용 Skype 서버 2019에 대 한 가상화 지원 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype 서버 2019에 대 한 가상화 지원에 대해 알아봅니다.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565957"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에 대 한 가상화 지원

비즈니스용 Skype 서버 2019은 가상화에서 지원 됩니다.

가상화가 지원 되는 동안 몇 가지 주요 사항에 유의 해야 합니다.

- 실제 CPU에 대 한 1:1 비율의 가상 CPU를 유지 관리 합니다.
- 작동 중에는 게스트 서버를 이동 하지 마세요.
- 라이브 시스템 및 가상 컴퓨터의 이식성 마이그레이션은 지원 되지 않습니다.
- 모든 호스트에서 하이퍼 스레드를 사용 하지 않도록 설정 합니다.
- 호스트 서버에 동적 메모리를 구성 하지 마십시오.
- 동적 디스크가 아닌 고정 또는 통과 디스크를 사용 합니다.
- 가상 게스트에 필요한 것 보다 더 이상 하이퍼바이저에 대 한 6-10% 오버 헤드를 허용 합니다.

## <a name="supported-hypervisors"></a>지원 되는 하이퍼바이저

SfB 서버 2019는 Windows Server 2016 및 Windows Server 2019에서 지원 됩니다.

타사 하이퍼바이저의 경우 관련 OS에 대 한 SVVP (서버 가상화 유효성 검사 프로그램) 테스트를 통과 한 하이퍼바이저가 필요 합니다.

- SVVP 목록에서 [Windows Server 2016 버전](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 을 참조 하십시오.
- SVVP 목록에서 [Windows Server 2019 버전](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 을 참조 하십시오.