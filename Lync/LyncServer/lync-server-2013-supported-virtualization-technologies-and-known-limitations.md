---
title: 'Lync Server 2013: 지원되는 가상화 기술 및 알려진 제한 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013의 지원되는 가상화 기술 및 알려진 제한 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-02-06_

Lync VDI 플러그 인을 사용 하면 지원 되는 가상화 기술에 대 한 오디오 및 비디오 통화를 할 수 있습니다. 이렇게 하면 [microsoft lync 2010 백서에서 클라이언트 가상화](https://go.microsoft.com/fwlink/?linkid=330447) 의 Microsoft lync Server 2010에 대해 개괄적으로 설명 하는 기능이 확장 됩니다. 표준 전화 규정을 준수 하는 경우 E911에 대 한 지원도 포함 됩니다. 다음 섹션에서는 Lync VDI 플러그 인 및 알려진 기능 제한에서 지원 되는 가상화 기술에 대해 설명 합니다.

<div>

## <a name="support-for-virtualization-technologies"></a>가상화 기술 지원

Lync VDI 플러그 인은 개인용 가상 데스크톱 시나리오에서 전체 데스크톱 remoting을 지원 하지만, 원격 데스크톱 세션 시나리오에는 해당 하지 않습니다. 이러한 시나리오는 아래와 같이 설명할 수 있습니다.

  - **지원 됨: 개인 설정 된 가상 데스크톱 또는 VDI (가상 데스크톱 인프라).**    이 시나리오에서는 각 사용자가 사용자 지정 가능한 가상 데스크톱에 로그온 하 고 모든 세션에서 유지 되는 데스크톱에 파일을 저장할 수 있습니다. Microsoft 원격 데스크톱 서비스, VMware 구간 보기 및 Citrix XenDesktop는 Lync에서 사용 하도록 테스트 된 구현입니다. Microsoft에서 테스트 한 공급 업체별 VDI 환경과 클라이언트 하드웨어에 대 한 자세한 내용은 [Microsoft Lync의 인프라 적격](https://go.microsoft.com/fwlink/?linkid=313435)을 참조 하세요.

  - **지원 되지 않음: 원격 데스크톱 세션**    이 시나리오에서는 각 사용자가 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온 합니다. 예제 구현에는 RDSH(Microsoft 원격 데스크톱 세션) 및 Citrix Receiver와 결합된 Citrix XenApp이 있습니다.

Lync VDI 플러그 인은 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원 하지 않으며, 응용 프로그램을 사용 하 여 전체 응용 프로그램을 로컬로 설치할 필요 없이 사용할 수 있습니다. 예제 구현에는 Citrix XenApp 및 Microsoft Application Virtualization (App-v)이 포함 됩니다. 응용 프로그램 스트리밍, 응용 프로그램 원격, 혼합 가상화 모드 (예: 전체 데스크톱 remoting의 응용 프로그램 원격)는 지원 되지 않습니다.

확장성을 허용 하려면 Lync VDI 플러그 인이 DVCs (동적 가상 채널) 라는 플랫폼 독립적인 Api를 사용 하도록 디자인 되었습니다. Lync에서 명시적으로 지원 하지 않는 시나리오는 VDI 솔루션 공급자의 지원 문을 참조 하세요.

</div>

<div>

## <a name="known-feature-limitations"></a>알려진 기능 제한

다음은 VDI 환경에서 Lync 2013을 사용할 때 발생 하는 제한 사항입니다.

  - 통화 위임 및 응답 그룹 에이전트 익명화 기능에 대해 제한적인 지원이 제공 됩니다.

  - 다음 기능은 지원되지 않습니다.
    
      - 통합 오디오 장치 및 비디오 장치 조정 페이지
    
      - 다중 보기 비디오
    
      - 대화 기록
    
      - RDS (원격 데스크톱 서비스).
    
      - 익명으로 모임 참가 (즉, 조직과 페더레이션 되지 않는 조직에서 호스트 하는 Lync 모임 참가).
    
      - Lync VDI 플러그 인을 Lync Phone Edition 장치와 함께 사용 합니다.
    
      - 네트워크 중단 시 통화 지속
    
      - 사용자 지정된 벨 소리 및 대기 음악 기능

  - Lync VDI 플러그 인은 Office 365 환경에서 지원 되지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

