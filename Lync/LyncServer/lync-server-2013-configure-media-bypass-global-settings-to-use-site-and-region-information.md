---
title: 사이트 및 지역 정보를 사용 하도록 미디어 바이패스 전역 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>사이트 및 지역 정보를 사용 하도록 Lync Server 2013에서 미디어 바이패스 전역 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

<div>


> [!NOTE]
> 이 항목에서는 중재 서버 미디어 바이패스를 설정하려는 특정 사이트 또는 서비스에 대해 중재 서버에서 피어(ITSP(인터넷 전화 통신 서비스 공급자)의 공중 전화망(PSTN) 게이트웨이, IP-PBX 또는 SBC(Session Border Controller))로의 트렁크 연결에 대한 미디어 바이패스를 이미 구성한 것으로 가정합니다.<BR>또한이 항목에서는 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013에서 네트워크 사이트 만들기 또는 수정</A>의 단계에 따라 수행한 네트워크 지역, 네트워크 사이트 및 서브넷 구성과 일치 하는 방식으로 토폴로지 작성기에서 모든 중앙 사이트 및 분기 사이트를 정의 하 고 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013에서 network site를 만들거나 수정한</A>후 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">서브넷을 네트워크 2013 사이트에 연결</A>하는 방법에 대해 설명 합니다. 구성이 일치하지 않으면 미디어 바이패스에 실패합니다.



</div>

피어와 연결된 개별 트렁크 연결에 대한 미디어 바이패스를 설정하는 것 외에 전역 설정도 구성해야 합니다. 이 항목의 단계를 사용하여 미디어 바이패스에 대한 전역 설정을 구성하는 경우 다음 상황 중 하나 또는 둘 다가 구성에 영향을 주는 것으로 가정합니다.

  - 트렁크 연결에서 미디어 바이패스를 구성한 피어와 Lync Server 끝점 간의 연결이 양호 *하지* 않습니다.

  - 대역폭 관리에 대한 CAC(통화 허용 제어)가 설정된 경우
    
    <div>
    

    > [!NOTE]
    > 통화 허용 제어 및 미디어 바이패스에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-media-bypass-and-mediation-server.md">미디어 바이패스 및 중재 서버 2013</A> 의 "PSTN 연결에 대 한 통화 허용 제어" 섹션을 참조 하십시오.

    
    </div>

네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 바이패스 고급 Enterprise Voice 기능 간에 공유됩니다(둘 다 설정된 경우). 따라서 통화 허용 제어를 이미 구성한 경우 다음 절차에 따라 특별히 미디어 바이패스에 대해 사이트 및 지역 정보를 편집할 필요가 없습니다. 통화 허용 제어에 대한 네트워크 지역 및 사이트를 아직 구성하지 않은 상태에서 미디어 바이패스 설정을 변경하려는 경우에 이 절차의 단계를 따르십시오.

또는 미디어 바이패스에 대한 결정을 내릴 때 사이트 및 지역 정보를 사용하되, 통화 허용 제어를 설정하지 않으려는 경우에 이러한 단계를 따르십시오. 이러한 경우에는 [Lync Server 2013의 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md)에 설명 된 것 처럼 대역폭 제한 링크는 여전히 네트워크 사이트 간 정책을 통해 표시 되어야 합니다. 통화 허용 제어가 설정되지 않았으므로 이 경우 실제 대역폭 제한은 중요하지 않습니다. 대신, 이러한 링크는 서브넷을 분할하여 대역폭 제한이 없는 링크를 지정하는 데 사용되므로 미디어 바이패스를 적용할 수 있습니다. 이는 통화 허용 제어와 미디어 바이패스가 둘 다 설정된 경우에도 마찬가지입니다.

또한 바이패스가 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의 된 대로 일관성을 유지 해야 합니다. 예를 들어 PSTN 게이트웨이만 배포 된 것으로 토폴로지 작성기에 정의한 분기 사이트가 있는 경우에는 분기 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 사용할 수 있도록 하는 엔터프라이즈 음성 정책을 사용 하 여 해당 분기 사이트를 구성 해야 합니다. 분기 사이트의 게이트웨이입니다.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>미디어 바이패스에 대한 사이트 및 지역 정보를 구성하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  테이블에서 **전역** 구성을 두 번 클릭합니다.

4.  **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.

5.  **사이트 및 지역 구성 사용**을 클릭합니다.

6.  필요한 경우 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택합니다.
    
    <div>
    

    > [!NOTE]
    > 이 확인란은 대역폭 제한이 없는 하나 이상의 큰 사이트(예: 대규모 중앙 사이트)를 같은 지역과 연결했지만 대역폭이 제한된 일부 분기 사이트도 이 지역과 연결한 경우에만 선택합니다. 매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면 모든 사이트와 연결된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결된 서브넷만 지정하면 되므로 구성이 간소화됩니다. 통화 허용 제어가 설정된 경우에는 이 확인란을 선택하지 않는 것이 좋습니다.

    
    </div>

7.  **커밋**을 클릭합니다.

다음으로, [Lync Server 2013의 미디어 바이패스에 대 한 네트워크 사이트와 서브넷을 연결](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)하는 방법에 설명 된 대로 네트워크 사이트에 서브넷을 추가 합니다. 네트워크 사이트에 서브넷을 연결 하는 실제 절차는 [Lync Server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 되어 있습니다. 모든 서브넷을 네트워크 사이트에 연결 하 고 나면 미디어 바이패스 배포가 완료 된 것입니다.

<div>


> [!IMPORTANT]
> 네트워크 지역 및 네트워크 사이트를 아직 만들지 않은 경우 미디어 바이패스 배포를 진행하려면 먼저 네트워크 지역과 네트워크 사이트를 만들어야 합니다. 자세한 내용은 Lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013에서 네트워크 지역 만들기 또는 수정</A> 및 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스를 위해 네트워크 사이트에 서브넷 연결](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

