---
title: 2015 스트레스 비즈니스용 Skype 서버 성능 도구에 대한 FAQ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 비즈니스용 Skype 2015 스트레스 및 성능 도구는 지원되는 도구 구성을 확인, 도구 문제 해결 및 스트레스 및 성능 도구를 실행하면 표시될 수 있는 행동을 명확히 하는 데 유용한 FAQ(질문과 대답)를 제공합니다.
ms.openlocfilehash: 401377560183b598311ed58b1a60291ba84f00b06fb8c4a6bd8b7ec792405084
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333170"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 스트레스 비즈니스용 Skype 서버 성능 도구에 대한 FAQ
 
비즈니스용 Skype 2015 스트레스 및 성능 도구는 지원되는 도구 구성을 확인, 도구 문제 해결 및 스트레스 및 성능 도구를 실행하면 표시될 수 있는 행동을 명확히 하는 데 유용한 FAQ(질문과 대답)를 제공합니다.
  
 이 FAQ에서는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 가장 자주 묻는 질문 중 일부를 설명하며 문제 해결 및 도구 구성 선택에 도움이 될 수 있습니다.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>프로덕션에서 LyncPerfTool.exe 수 있나요?

이 경우 **권장되지** 않습니다. 이 도구는 프로덕션 서버 성능, 보안 및 최종 사용자 환경에 영향을 미치게 됩니다.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>사용자를 처음으로 로그온합니다. 서버가 높은 부하를 실행하는 이유는 무엇입니까?

사용자가 처음 로그온할 때 백그라운드에서 추가 작업이 수행됩니다. 따라서 백 엔드 서버의 Microsoft SQL Server 성능이 저하될 수 있습니다. 도구로 결과를 측정하기 전에 모든 사용자에 대해 로그온하는 짧은 테스트를 실행한 다음 클라이언트를 다시 시작하는 것이 좋습니다. 비즈니스용 Skype 서버 초당 12개 이상의 동시 사용자 로그온 세션을 지원하지 않지만 서버에서 처리할 수 있는 실제 수는 하드웨어 구성에 따라 달라지며 지원되는 값보다 낮을 수 있습니다.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>클라이언트의 메모리가 부족합니다. 어떻게 해야 하나요?

클라이언트에 메모리가 부족한 경우 프런트 엔드 풀당 로그온한 비즈니스용 Skype 서버 수를 줄여야 합니다. 문제가 지속되는 경우 프런트 엔드 풀을 수리할 수 있습니다.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>서버 자체에서 이 비즈니스용 Skype 실행할 수 있나요?

이 작업을 하지 말아야합니다. 이 시나리오는 이진 불일치로 인해 실패할 수 있으며 서버의 리소스 소비를 측정하는 것이기 때문에 지원되지 않습니다. 실제로 이 도구를 실행하면 서버 성능에 영향을 미치고 데이터와 측정을 무효화할 수 있습니다.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>가상 서버 또는 LyncPerfTool.exe Server 2008/2012에서 Microsoft Hyper-V 실행할 수 있나요?

네 당신은 할 수 있어요.
  
## <a name="what-does-mpop-mean"></a>MPOP는 무엇을 의미하나요?

MPOP는 "여러 현재 상태 지점"을 말하기 위해 단축된 방식입니다. MPOP는 사용자가 여러 컴퓨터 또는 장치에서 비즈니스용 Skype 클라이언트에 로그온하는 시나리오를 시뮬레이트하기 위한 것입니다. 각 끝점은 LyncPerfTool.exe 프로필을 사용하게 됩니다. 즉, 프로필이 두 현재 상태 지점 간에 분할되지 않습니다.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>I started LyncPerfTool.exe but nothing is happening. 무슨 일이죠?

서버에서 총 활성 끝점 카운터를 확인하여 사용자가 연결하고 있는지 확인할 수 있습니다. 사용자가 연결되지 않는 경우 2015 비즈니스용 Skype 서버 확인해야 합니다. 일반적으로 서버 이름, 사용자 prefix 또는 암호 중 하나에 잘못된 문제가 있기 때문에 발생합니다. 외부 클라이언트는 액세스 프록시 및 TargetServer 값을 지정해야 합니다. 구성 파일의 포트 번호를 확인 합니다.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>어떤 것이 측정되고 있는지 어떻게 확신할 수 있나요?

사용자가 작업을 연결하고 수행하고 있는지 여부를 나타내는 LyncPerfTool 성능 카운터가 있지만, 작업을 측정하는 가장 쉬운 방법은 비즈니스용 Skype 2015 클라이언트를 사용하여 계정 중 하나에 로그온한 후 직접 해당 작업을 수행하는 것입니다. 결과를 확인하여 측정이 수행된 것이 확인됩니다.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 용량 계획 도구 및/또는 Lync Server 2013 용량 계획 도구가 설치되어 있습니다. 괜찮습니까?

 이러한 도구에는 상호 관리 문제가 있습니다. 2015 스트레스 및 성능 도구에서 유효한 데이터를 비즈니스용 Skype 서버 이전 버전의 도구를 모두 제거해야 합니다.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>스트레스 및 성능 도구에서 CAA 통화 정보 서버 토폴로지가 설정하나요?

아니요. 도구는 이 작업을 하지 않습니다. 이 도구는 사용자 부하를 시뮬레이트하기 위해 사용자, 연락처 및 메일 목록을 만들기만 합니다.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>도구에서 지원하는 최대 사용자 수는 어떻게 하나요?

테스트에서는 최대 80,000명까지 사용자를 만들며 총 30,000명에 달하는 테스트를 실행했습니다. 기술 제한으로 더 높은 값을 허용하기는 하지만 최대 120,000명까지 사용자를 추천합니다. 이러한 값은 환경의 서버 및 하드웨어에 따라 달라 집니다.
  

