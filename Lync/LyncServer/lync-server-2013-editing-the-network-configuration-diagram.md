---
title: 'Lync Server 2013: 네트워크 구성 다이어그램 편집'
description: 'Lync Server 2013: 네트워크 구성 다이어그램을 편집 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570594"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 구성 다이어그램 편집

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

디자이너가 Lync Server 2013에서 수행 하는 대부분의 작업은 계획 도구에서 IP 주소에 대 한 항목과 네트워크 다이어그램의 항목에 대 한 Fqdn (정규화 된 도메인 이름)을 정의 하는 것으로 구성 됩니다. 이 페이지에서 입력 한 정보는 계획 도구에 포함 된 보고서 및 기타 정보로 전달 됩니다.

![계획 도구 네트워크 다이어그램](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "계획 도구 네트워크 다이어그램")

계획 도구는 IP 주소 및 Fqdn에 대 한 기본 텍스트가 포함 된 네트워크 다이어그램을 만듭니다.

네트워크 다이어그램과 입력 값을 편집하려면

1.  작업을 시작할 네트워크 섹션을 선택합니다. 예를 들어 **access1.contoso.com**텍스트를 두 번 클릭 합니다. 열리는 대화 상자에서 서버 access1.contoso.com의 실제 FQDN과 실제 IP 주소를 입력 하 고 131.107.155.3를 대체 합니다.

2.  **확인**을 클릭하여 변경 내용을 저장합니다.

3.  하드웨어 부하 분산 장치의 가상 IP 주소를 제공하거나 풀의 서버에 대한 DNS(Domain Name System) 부하 분산용 서버 항목을 제공하여 IP 주소 및 FQDN을 계속 편집합니다.

계획 도구의 유용한 기능은 디자이너가 풀의 각 서버를 별도로 편집할 필요 없이 IP 주소 범위 및 서버 호스트 이름을 점진적으로 할당할 수 있다는 것입니다. 예:

1.  풀링된 프런트 엔드 서버를 두 번 클릭합니다. 대화 상자가 열리면 **IP 및 FQDN을 이 클러스터에 있는 모든 동일한 서버의 시작 지점으로 사용하시겠습니까?** 를 선택합니다.

2.  예를 들어 첫 번째 서버의 시작 값은 fe0101.contoso.com이 고 IP 주소는 192.168.21.122입니다.

3.  **프런트 엔드 서버 FQDN**에 **fe0.contoso.com** 을 입력 하 고 **프런트 엔드 서버 IP 주소**에 **192.168.21.131** 를 입력 한 다음 **확인**을 클릭 합니다.

4.  자동 증분 기능은 풀에 있는 모든 서버를 fe01를 통해 f e으로 업데이트 하 고, 192.168.21.131에서 136 까지의 모든 IP 주소를 사용 합니다.

모든 편집을 완료 한 후에는 다음 단계를 완료 하 여 토폴로지를 저장 합니다.

계획 도구 디자인을 저장 하려면 **파일**을 클릭 하 고 **토폴로지 저장** 또는 **토폴로지를 다른 이름으로 저장**을 클릭 합니다. **다른 이름으로 계획 도구 저장** 대화 상자가 나타나면 **파일 이름**에 파일 이름을 입력한 다음 **저장**을 클릭합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 디자인 편집](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

