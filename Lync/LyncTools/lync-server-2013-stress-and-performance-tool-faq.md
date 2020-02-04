---
title: Lync Server 2013 스트레스 및 성능 도구 FAQ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9138a23ee1fa45f3da827832b568852952b0ae4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 스트레스 및 성능 도구 FAQ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>자주 묻는 질문

Lync Server 2013 스트레스 및 성능 도구에 대 한 몇 가지 질문과 대답이 다음과 같이 나타납니다.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>실제 환경에서 L Cperftool을 실행할 수 있나요?

이 방법은 권장 되지 않습니다. 이 도구는 서버 성능, 보안 및 사용자 환경에 영향을 줍니다.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>처음으로 사용자를 로그인 합니다. 이러한 로드가 높을 때 서버가 실행 되는 이유는 무엇 인가요?

사용자가 처음 로그온 할 때 발생 하는 추가 작업이 있습니다. 결과적으로 Microsoft SQL Server 백 엔드 서버의 성능이 저하 됩니다. 모든 사용자에 게 기록 하는 짧은 테스트를 실행 한 다음 결과를 측정 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다. 초당 최대 12 개의 동시 사용자 로그온 세션을 지원 하지는 않지만 하드웨어 구성에 따라 다릅니다.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>클라이언트의 메모리가 부족 합니다. 제가 뭘 해야 하나요?

클라이언트의 메모리가 부족 한 경우 컴퓨터 당 사용자 수를 줄여야 합니다.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>클라이언트가 항상 100%의 CPU에 있습니다. 제가 뭘 해야 하나요?

모든 사용자가 로그온 한 후에 클라이언트가 매우 높은 CPU로 실행 되는 경우 컴퓨터 당 사용자 수를 줄여야 합니다. 높은 CPU 스파이크는 허용 되지만, 유지 되는 경우 부하를 줄여야 합니다.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>서버 자체에서 도구를 실행할 수 있나요?

아니요. 이 시나리오는 지원 되지 않으며 이진 불일치로 인해 실패할 수 있습니다. 또한 서버에서 리소스 소모를 측정 하는 것이 점에서 도구를 실행 하는 것 이기 때문에 측정값을 의미 없는 값으로 렌더링할 수 있습니다.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>가상 서버나 Microsoft Hyper-v Server 2008/2012에서 L<c13> Cperftool을 실행할 수 있나요?

예.

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 무엇을 의미 하나요?

MPOP는 여러 개의 현재 상태를 나타냅니다. 이는 사용자가 여러 컴퓨터에서 Lync 2013에 로그온 하는 시나리오를 시뮬레이트하는 것을 의미 합니다. L<c13> Cperftool .exe에서는 각 끝점이 기본 프로필을 사용 합니다 (즉, 프로필이 두 지점 사이에 분할 되지 않음).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>죄송 합니다. exe를 시작 했지만 아무런 변화가 없습니다. 무슨 일이죠?

사용자가 연결 되어 있는지 확인 하려면 클라이언트의 총 활성 끝점 카운터를 확인 합니다. 사용자가 연결 되지 않은 경우에는 Lync Server 2013 구성을 확인 합니다. 일반적으로이 문제는 서버 이름, 사용자 접두사 또는 암호가 올바르지 않기 때문에 발생 합니다. 외부 클라이언트에서 액세스 프록시를 TargetServer 값으로 지정 해야 한다는 점에 유의 하세요. 구성 파일의 포트를 확인 합니다.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>무슨 일이 발생 하 고 있는지 어떻게 알 수 있습니까?

다양 한 L<c13> Cperftool 성능 카운터는 사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타냅니다. 그러나 쉽게 확인할 수 있는 방법은 Lync 2013를 사용 하 여 계정 중 하나에 로그온 하 고 원하는 작업을 수행 하는 것입니다.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Live Communications Server 2007 R2 용량 계획 도구 및/또는 Lync Server 2010이 설치 되어 있습니다. 이 게 정상 인가요?

아니요. 상호 운용성 문제가 있으므로이 제품의 모든 이전 버전을 제거 해야 합니다.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>스트레스 및 성능 도구가 CAA Call 정보 서버 토폴로지를 설정 하나요?

아니요. 이 도구는 사용자, 연락처 및 메일 그룹을 만들고 사용자 부하를 시뮬레이트합니다.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>도구가 지 원하는 최대 사용자 수는 무엇 인가요?

이 도구를 사용 하 여 총 8만 명의 사용자를 만들고 3만 테스트를 실행 했습니다. 사용 가능한 클라이언트 및 서버 하드웨어에 따라 기술적 제한으로 더 높은 값이 허용 되지만, 최대 12만 명의 사용자를 추천 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

