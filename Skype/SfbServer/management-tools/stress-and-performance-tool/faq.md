---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype 2015 스트레스 및 성능 도구 자주 묻는 질문 (FAQ), 지원 되는 도구 구성, 문제 해결 도구 문제, 스트레스 및 성능 도구를 실행할 때 표시 될 수 있는 상세한 behaviours에 대해 알아보기 .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816187"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답
 
비즈니스용 Skype 2015 스트레스 및 성능 도구 자주 묻는 질문 (FAQ), 지원 되는 도구 구성, 문제 해결 도구 문제, 스트레스 및 성능 도구를 실행할 때 표시 될 수 있는 상세한 behaviours에 대해 알아보기 .
  
 이 FAQ는 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대해 자주 묻는 질문 중 몇 가지를 다루며 문제 해결 및 도구 구성 선택에 도움이 될 수 있습니다.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>실제 환경에서 L Cperftool을 실행할 수 있나요?

이 방법은 권장 **되지** 않습니다. 이 도구는 프로덕션 서버 성능, 보안 및 최종 사용자 환경에 영향을 줍니다.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>사용자를 처음으로 로그인 합니다. 서버가 높은 부하를 실행 하는 이유는 무엇 인가요?

사용자가 처음 로그온 할 때 백그라운드에서 추가 작업이 수행 됩니다. 결과적으로 Microsoft SQL Server 백 엔드 서버의 성능이 떨어질 수 있습니다. 모든 사용자에 게 기록 하는 짧은 테스트를 실행 한 다음 도구를 사용 하 여 결과 측정을 시작 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다. 비즈니스용 Skype 서버는 초당 12 대의 동시 사용자 로그온 세션을 지원 하지 않지만, 서버에서 처리할 수 있는 실제 숫자는 하드웨어 구성에 따라 다르며 지원 되는 값 보다 낮을 수도 있습니다.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>내 클라이언트의 메모리가 부족 합니다! 제가 뭘 해야 하나요?

클라이언트의 메모리가 부족 한 경우 비즈니스용 Skype Server 프런트 엔드 풀에 로그온 한 사용자 수를 줄여야 합니다. 문제가 지속 되는 경우 프런트 엔드 풀을 확장 하도록 선택할 수도 있습니다.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>비즈니스용 Skype 서버에서이 도구를 실행할 수 있나요?

이 작업을 수행 하지 마세요. 이 시나리오는 이진 불일치로 인해 실패할 수 있고 서버에서 리소스 소모를 측정 하는 것이 목표 때문에 지원 되지 않습니다. 실제로이 도구를 실행 하면 서버 성능에 영향을 줄 수 있고 데이터와 측정법을 무효화할 수 있습니다.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>가상 서버나 Microsoft Hyper-v Server 2008/2012에서 L<c13> Cperftool을 실행할 수 있나요?

네 당신은 할 수 있어요.
  
## <a name="what-does-mpop-mean"></a>MPOP 무엇을 의미 하나요?

MPOP "여러 지점을 표시" 하는 간단한 방법입니다. MPOP는 사용자가 여러 컴퓨터 또는 장치에서 비즈니스용 Skype 2015 클라이언트에 로그온 하는 시나리오를 시뮬레이트하는 데 목적이 있습니다. 모든 끝점에서 기본 프로필을 사용 하는 L<c13> Cperftool. 즉, 프로필이 두 지점 사이에 분할 되지 않습니다.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>죄송 합니다. exe를 시작 했지만 아무런 변화가 없습니다. 무슨 일이죠?

사용자가 연결 되어 있는지 확인 하려면 서버의 총 활성 끝점 카운터를 확인 합니다. 사용자가 연결 되지 않은 경우 비즈니스용 Skype Server 2015 구성을 확인 합니다. 일반적으로 표시 되는 문제는 서버 이름, 사용자 접두사 또는 암호 중 하나가 올바르지 않기 때문에 발생 합니다. 외부 클라이언트에서 액세스 프록시와 TargetServer 값을 지정 해야 한다는 점에 유의 하세요. 구성 파일의 포트 번호를 확인 합니다.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>무엇을 측정 하 고 있는지 확인 하려면 어떻게 해야 하나요?

사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타내는 L의사 Cperftool 성능 카운터가 있지만 작업이 측정 되는 가장 쉬운 방법은 비즈니스용 Skype 2015 클라이언트를 사용 하 여 계정 중 하나에 로그온 하 여 수행 하는 것입니다. 작업을 수행 합니다. 측정을 확인 하기 위해 결과를 확인 합니다.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 용량 계획 도구 및/또는 Lync Server 2013 용량 계획 도구가 설치 되어 있습니다. 그 게 괜 찮 나요?

 이러한 도구에는 상호 운용성 문제가 있습니다! 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에서 유효한 데이터를 얻으려면 이전 버전의이 도구를 모두 제거 해야 합니다.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>스트레스 및 성능 도구가 CAA Call 정보 서버 토폴로지를 설정 하나요?

아니요, 도구가이 작업을 수행 하지 않습니다. 이 도구는 사용자 부하를 시뮬레이트하기 위해 사용자, 연락처 및 메일 목록만 만듭니다.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>도구가 지 원하는 최대 사용자 수는 무엇 인가요?

테스트를 통해 총 8만 명의 사용자를 만들고,이 도구를 실행 하는 전체 3만 사용자 테스트를 실행 했습니다. 기술적 제한 때문에 더 높은 값을 사용할 수 있지만 최대 12만 명의 사용자를 제안 합니다. 이러한 값은 사용자 환경의 서버와 하드웨어에 따라 달라 집니다.
  

