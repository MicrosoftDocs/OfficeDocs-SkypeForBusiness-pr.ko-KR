---
title: Lync Server 2013 스트레스 및 성능 도구 FAQ
description: Lync Server 2013 스트레스 및 성능 도구 FAQ
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
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573544"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 스트레스 및 성능 도구 FAQ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>FAQ

Lync Server 2013 스트레스 및 성능 도구에 대 한 몇 가지 질문과 대답이 나와 있습니다.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>프로덕션 환경에서 LyncPerfTool.exe 실행할 수 있는지 여부

이 방법은 권장 되지 않습니다. 이 도구는 서버 성능, 보안 및 사용자 환경에 영향을 줍니다.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>처음으로 사용자를 로그온 합니다. 서버가 이러한 높은 부하에서 실행 되는 이유는 무엇 인가요?

사용자가 처음 로그온 할 때 추가 작업이 수행 됩니다. 따라서 Microsoft SQL Server 백 엔드 서버의 성능이 저하 됩니다. 모든 사용자에 대해 기록 되는 짧은 테스트를 실행 한 다음 결과를 측정 하기 전에 클라이언트를 다시 시작 하는 것이 좋습니다. 초당 12 개 이상의 동시 사용자 로그온 세션은 지원 되지 않지만 하드웨어 구성에 따라 다릅니다.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>클라이언트에 메모리가 부족 합니다. 제가 뭘 해야 하나요?

클라이언트에 메모리가 부족 한 경우 컴퓨터당 사용자 수를 줄여야 합니다.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>클라이언트는 항상 100%의 CPU에 있습니다. 제가 뭘 해야 하나요?

모든 사용자가 로그온 한 후에 클라이언트가 매우 높은 CPU로 실행 되는 경우 컴퓨터당 사용자 수를 줄여야 합니다. 높은 CPU 스파이크는 사용할 수 있지만 지속적인 경우에는 부하를 줄여야 합니다.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>서버에서 도구를 실행할 수 있습니까?

아니요. 이 시나리오는 지원 되지 않으며 이진 불일치로 인해 실패할 수 있습니다. 또한 서버에서 리소스 소비를 측정 하는 것 이므로 도구를 실행 하면 측정이 의미가 없게 됩니다.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>가상 서버나 Microsoft Hyper-v Server 2008/2012에서 LyncPerfTool.exe 실행할 수 있나요?

예.

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 무슨 의미 입니까?

MPOP는 여러 개의 현재 상태를 나타냅니다. 이는 사용자가 여러 컴퓨터에서 Lync 2013에 로그온 하는 시나리오를 시뮬레이션 하는 것을 의미 합니다. LyncPerfTool.exe에서 각 끝점은 기본 프로필을 사용 하며,이 프로필은 두 개의 현재 상태 사이에 분할 되지 않습니다.

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>LyncPerfTool.exe를 시작 했지만 아무 일도 발생 하지 않습니다. 어떻게 된 것일까요?

사용자가 연결 되어 있는지 여부를 확인 하려면 클라이언트의 총 활성 끝점 카운터를 확인 합니다. 사용자가 연결 되어 있지 않으면 Lync Server 2013 구성을 확인 합니다. 이 문제는 일반적으로 서버 이름, 사용자 접두사 또는 암호가 잘못 되었기 때문에 발생 합니다. 외부 클라이언트는 액세스 프록시를 TargetServer 값으로 지정 해야 합니다. 구성 파일의 포트를 확인 합니다.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>어떤 일이 진행 되 고 있는지 어떻게 알 수 있나요?

다양 한 LyncPerfTool 성능 카운터는 사용자가 연결 하 고 작업을 수행 하 고 있는지 여부를 나타냅니다. 그러나 쉽게 확인할 수 있는 방법은 Lync 2013을 사용 하 여 계정 중 하나에 로그온 하 고 원하는 작업을 수행 하는 것입니다.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Live Communications Server 2007 R2 용량 계획 도구 및/또는 Lync Server 2010가 설치 되어 있습니다. 정상 인가요?

아니요. 상호 운용성 문제가 있으므로이 제품의 이전 버전을 모두 제거 해야 합니다.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>스트레스 및 성능 도구에서 CAA 통화 정보 서버 토폴로지를 설정 합니까?

아니요. 이 도구는 사용자, 연락처 및 메일 목록만 만들고 사용자 부하를 시뮬레이션 합니다.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>도구에서 지 원하는 최대 사용자 수는 얼마나 됩니까?

이 도구를 사용 하 여 총 8만 명의 사용자를 만들고 전체 3만 사용자 테스트를 실행 했습니다. 기술적 제한은 사용 가능한 클라이언트 및 서버 하드웨어에 따라 값이 더 높다는 것을 허용 하지만 최대 12만 명의 사용자를 추천 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

