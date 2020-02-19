---
title: 'Lync Server 2013: SIP 트렁크에 대 한 통화 허용 제어'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7140d77b819f62f0eb2078cc161511653fef1461
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크에 대 한 통화 허용 제어

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

SIP 트렁크에 CAC(통화 허용 제어)를 배포하려면 ITSP(인터넷 전화 통신 서비스 공급자)를 나타내는 네트워크 사이트를 만듭니다. SIP 트렁크에 대역폭 정책 값을 적용하려면 엔터프라이즈의 네트워크 사이트와 ITSP를 나타내기 위해 만든 네트워크 사이트 간의 사이트 간 정책을 만듭니다.

다음 그림에서는 SIP 트렁크에 대한 예제 CAC 배포를 보여 줍니다.

**SIP 트렁크에 대한 CAC 구성**

![통화 허용 제어 SIP 트렁크 다이어그램](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "통화 허용 제어 SIP 트렁크 다이어그램")

SIP 트렁크에 CAC를 구성하려면 CAC 배포 중에 다음 작업을 수행해야 합니다.

1.  ITSP를 나타내는 네트워크 사이트를 만듭니다. 네트워크 사이트를 적절한 네트워크 지역에 연결하고 이 네트워크 사이트에 오디오 및 비디오 대역폭으로 0을 할당합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 CAC에 대 한 네트워크 사이트 구성을](lync-server-2013-configure-network-sites-for-cac.md) 참조 하십시오.
    
    <div>
    

    > [!NOTE]  
    > ITSP에 대해서는 이 네트워크 사이트 구성이 작동하지 않습니다. 대역폭 정책 값은 2단계에서 실제로 적용됩니다.

    
    </div>

2.  1단계에서 만든 사이트에 대한 관련 매개 변수 값을 사용하여 SIP 트렁크에 대한 사이트 간 링크를 만듭니다. 예를 들어 엔터프라이즈의 네트워크 사이트 이름을 NetworkSiteID1 매개 변수 값으로 사용하고 ITSP 네트워크 사이트를 NetworkSiteID2 매개 변수 값으로 사용합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md) 를 참조 하십시오. 또한 Remove-csnetworkintersitepolicy cmdlet에 대 한 Lync Server 관리 셸 설명서도 참조 하십시오.

3.  ITSP로부터 SCB(세션 경계 컨트롤러) 미디어 종료 지점의 IP 주소를 얻습니다. 해당 IP 주소(서브넷 마스크 32 포함)를 ITSP를 나타내는 네트워크 사이트에 추가합니다. 자세한 내용은 [Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)을 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

