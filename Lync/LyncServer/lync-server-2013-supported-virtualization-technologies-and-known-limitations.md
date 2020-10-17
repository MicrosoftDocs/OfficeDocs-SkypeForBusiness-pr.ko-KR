---
title: 'Lync Server 2013: 지원 되는 가상화 기술 및 알려진 제한 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d2d884566c21933e00dd3897f5fe394b4a2624
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523935"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013의 지원 되는 가상화 기술 및 알려진 제한 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-02-06_

Lync VDI 플러그 인을 사용 하면 지원 되는 가상화 기술에 대 한 오디오 및 비디오 통화를 할 수 있습니다. 이는 [Microsoft lync 2010 백서에서 클라이언트 가상화](https://go.microsoft.com/fwlink/?linkid=330447) 의 Microsoft lync Server 2010에 대해 설명 된 기능을 확장 합니다. 표준 전화 규정 준수에는 E911에 대 한 지원도 포함 되어 있습니다. 다음 섹션에서는 Lync VDI 플러그 인 및 알려진 기능 제한에 의해 지원 되는 가상화 기술에 대해 설명 합니다.

<div>

## <a name="support-for-virtualization-technologies"></a>가상화 기술 지원

Lync VDI 플러그 인은 개인 가상 데스크톱 시나리오에서는 전체 데스크톱 원격을 지원 하지만 원격 데스크톱 세션 시나리오에는 해당 되지 않습니다. 이러한 시나리오는 다음과 같이 설명할 수 있습니다.

  - **지원: 개인 설정 된 가상 데스크톱 또는 VDI (가상 데스크톱 인프라)**     이 시나리오에서는 각 사용자가 맞춤형 가상 데스크톱에 로그온 하 고 세션 간에 지속 되는 파일을 데스크톱에 저장할 수 있습니다. Microsoft 원격 데스크톱 서비스, VMware 수평 보기 및 Citrix XenDesktop은 Lync에서 사용 하도록 테스트 된 구현입니다. Microsoft에서 테스트 한 공급 업체별 VDI 환경 및 클라이언트 하드웨어에 대 한 자세한 내용은 [Microsoft Lync의 인프라 자격](https://go.microsoft.com/fwlink/?linkid=313435)을 참조 하십시오.

  - **지원 되지 않음: 원격 데스크톱 세션**     이 시나리오에서 각 사용자는 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온 합니다. 예제 구현에는 Microsoft RDSH (원격 데스크톱 세션) 및 citrix 수신기와 함께 사용 되는 Citrix XenApp 포함 됩니다.

Lync VDI 플러그 인은 전체 응용 프로그램을 로컬로 설치 하지 않고도 응용 프로그램을 사용할 수 있도록 하는 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원 하지 않습니다. 예제 구현에는 Citrix XenApp 및 Microsoft Application Virtualization (App-v)이 포함 됩니다. 응용 프로그램 스트리밍, 응용 프로그램 원격 및 혼합 가상화 모드 (예: 전체 데스크톱 원격에서의 응용 프로그램 원격)는 지원 되지 않습니다.

확장성을 허용 하기 위해 Lync VDI 플러그 인은 DVCs (동적 가상 채널) 라는 플랫폼 독립적 Api를 사용 하도록 설계 되었습니다. Lync에서 명시적으로 지원 하지 않는 시나리오는 VDI solution provider의 지원 문을 참조 하십시오.

</div>

<div>

## <a name="known-feature-limitations"></a>알려진 기능 제한 사항

VDI 환경에서 Lync 2013을 사용 하는 경우의 알려진 제한은 다음과 같습니다.

  - 통화 위임 및 응답 그룹 에이전트 익명화 기능에 대 한 지원은 제한적입니다.

  - 다음 기능은 지원 되지 않습니다.
    
      - 통합 오디오 장치 및 비디오 장치 조정 페이지
    
      - 다중 보기 비디오
    
      - 대화 기록
    
      - RDS (원격 데스크톱 서비스)
    
      - 익명으로 모임 참가 (즉, 조직과 페더레이션 되지 않는 조직에서 호스팅하는 Lync 모임 참가)
    
      - Lync Phone Edition 장치와 함께 Lync VDI 플러그 인 사용
    
      - 네트워크 중단이 발생 하는 경우의 통화 연속성
    
      - 사용자 지정 된 벨 소리 및 보류 된 음악 기능

  - Lync VDI 플러그 인은 Microsoft 365 또는 Office 365 환경에서 지원 되지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

