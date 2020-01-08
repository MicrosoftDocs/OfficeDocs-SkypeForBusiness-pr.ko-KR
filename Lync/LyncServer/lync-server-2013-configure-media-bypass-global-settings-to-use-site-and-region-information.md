---
title: 미디어 구성 사이트 및 지역 정보 사용을 위한 전역 설정 무시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>미디어 구성 Lync Server 2013에서 사이트 및 지역 정보를 사용 하 여 전역 설정을 무시 합니다.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

<div>


> [!NOTE]
> 이 항목에서는 인터넷 전화 통신 서비스의 중재 서버에서 피어 (PSTN (공개 통신 네트워크) 게이트웨이, IP PBX 또는 세션 경계 컨트롤러 (SBC)로의 트렁크 연결에 대 한 미디어 바이패스를 이미 구성 했다고 가정 합니다. 미디어를 사용 하 여 중재 서버를 우회 하려는 특정 사이트 또는 서비스에 대 한 공급자 (ITSP)<BR>또한이 항목에서는 lync <A href="lync-server-2013-create-or-modify-a-network-region.md">server 2013에서 네트워크 영역 만들기 또는 수정</A>, lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013에서 네트워크 사이트</A>만들기 또는 수정, lync server <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">2013에서 서브넷을 네트워크 사이트에 연결</A>하는 단계에 따라 수행 된 네트워크 지역, 네트워크 사이트 및 서브넷 구성과 일치 하는 방식으로 모든 중앙 사이트 및 분기 사이트를 토폴로지 작성기에 정의 했다고 가정 합니다. 일치 하지 않으면 미디어 바이패스에 실패 합니다.



</div>

피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 전역 설정을 구성 해야 합니다. 이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우 다음 상황 중 하나 또는 모두에 따라 구성에 영향을 가정 합니다.

  - 사용자가 트렁크 연결에서 미디어 바이패스를 구성한 피어와 Lync 서버 끝점 간에는 적절 하 게 연결할 수 *없습니다* .

  - 대역폭 관리에 대 한 호출 허용 제어 (CAC)를 사용 합니다.
    
    <div>
    

    > [!NOTE]
    > 통화 허용 제어 및 미디어 바이패스에 대 한 고려 사항에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013에서 미디어 바이패스 및 조정 서버의</A> "PSTN 연결에 대 한 통화 허용 제어" 섹션을 참조 하세요.

    
    </div>

네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 건너뛰기 고급 Enterprise Voice 기능을 모두 사용 하도록 설정 되어 있는 경우 공유 됩니다. 따라서 통화 허용 제어를 이미 구성한 경우에는 다음 절차를 사용 하 여 미디어 바이패스에 대 한 사이트 및 지역 정보를 편집할 필요는 없습니다. 통화 허용 제어에 대해 아직 네트워크 지역과 사이트를 구성 하지 않은 경우 미디어 우회 설정을 변경 하려면이 절차의 단계를 따릅니다.

또는 우회 결정에 사이트 및 지역 정보를 사용 하려는 경우에는 다음 단계를 수행 하지만,이 경우에는 통화 허용 제어를 사용 하지 않습니다. 이러한 경우에는 [Lync Server 2013의 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md)에 설명 된 대로 네트워크 사이트 간 정책을 통해 대역폭 제한 링크를 표시 해야 합니다. 이 경우에는 통화 허용 제어를 사용할 수 없기 때문에 실제 대역폭 제약 조건이 중요 하지 않습니다. 대신 이러한 링크를 사용 하 여 대역폭 한도가 없는 서브넷을 지정 하 고 미디어 바이패스를 활용할 수 있습니다. 이는 또한 통화 허용 제어와 미디어 바이패스를 모두 사용 하는 경우에도 마찬가지입니다.

또한 bypass이 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트 간에 일관성을 유지 해야 하며, 네트워크 지역과 네트워크 사이트를 구성할 때 정의 되어 있습니다. 예를 들어, PSTN 게이트웨이만 배포 된 상태로 토폴로지 작성기에 정의한 지점 사이트를 사용 하는 경우에는 지점 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 할 수 있는 엔터프라이즈 음성 정책으로 해당 지점 사이트를 구성 해야 합니다. 지사 사이트의 게이트웨이입니다.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>미디어 바이패스에 대 한 사이트 및 지역 정보를 구성 하려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  표에서 **전역** 구성을 두 번 클릭 합니다.

4.  **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.

5.  **사이트 및 지역 구성 사용을**클릭 합니다.

6.  필요한 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 합니다.
    
    <div>
    

    > [!NOTE]
    > 대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만이 확인란을 선택 하 고, 대역폭이 있는 동일한 지역에 연결 된 일부 지점 사이트도 사항이. 매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결 된 서브넷만 지정 하는 구성이 간소화 됩니다. 통화 허용 제어를 사용 하는 경우이 확인란을 선택 하지 않는 것이 좋습니다.

    
    </div>

7.  **커밋**을 클릭합니다.

다음으로, [Lync Server 2013에서 미디어를 사용 하 여 서브넷을 연결](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)하는 것과 같이 네트워크 사이트에 서브넷을 추가 합니다. 네트워크 사이트와 서브넷을 연결 하는 실제 절차는 [Lync Server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 되어 있습니다. 모든 서브넷을 네트워크 사이트에 연결한 후에는 미디어 바이패스 배포가 완료 됩니다.

<div>


> [!IMPORTANT]
> 아직 네트워크 지역과 네트워크 사이트를 만들지 않은 경우에는 먼저 해당 지역을 만들어야 미디어 건너뛰기 배포를 진행할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013에서 네트워크 영역 만들기 또는 수정을</A> 참조 하 고 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013에서 네트워크 사이트를 만들거나 수정</A>합니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[네트워크 사이트와 서브넷을 연결 하 여 Lync Server 2013에서 미디어 무시](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

