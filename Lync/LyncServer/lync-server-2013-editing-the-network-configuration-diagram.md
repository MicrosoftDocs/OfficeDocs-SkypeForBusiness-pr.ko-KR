---
title: 'Lync Server 2013: 네트워크 구성 다이어그램 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 구성 다이어그램 편집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 2013에서 디자이너가 수행 하는 대부분의 작업은 네트워크 다이어그램의 항목에 대 한 IP 주소 및 Fqdn (정규화 된 도메인 이름)의 항목을 정의 하는 것으로 구성 됩니다. 이 페이지에 입력 되는 정보는 계획 도구에 포함 된 보고서 및 기타 정보로 전달 됩니다.

![계획 도구 네트워크 다이어그램](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "계획 도구 네트워크 다이어그램")

계획 도구는 IP 주소와 Fqdn에 대 한 기본 텍스트가 포함 된 네트워크 다이어그램을 만듭니다.

네트워크 다이어그램 및 입력 값을 편집 하려면 다음을 수행 합니다.

1.  작업을 시작할 네트워크의 섹션을 선택 합니다. 예를 들어, **access1.contoso.com**텍스트를 두 번 클릭 합니다. 열리는 대화 상자에서 서버 access1.contoso.com의 실제 FQDN과 실제 IP 주소를 입력 하 고 131.107.155.3를 바꿉니다.

2.  **확인** 을 클릭 하 여 항목을 저장 합니다.

3.  IP 주소 및 Fqdn을 계속 편집 하 여 하드웨어 부하 분산 장치에 대 한 가상 IP 주소를 제공 하거나 풀에 있는 서버의 DNS (Domain Name System) 부하 분산에 대 한 서버 항목을 표시 합니다.

계획 도구의 유용한 기능은 디자이너에서 풀의 개별 서버를 편집 하는 대신 IP 주소와 서버 호스트 이름 범위를 점차적으로 할당할 수 있다는 것입니다. 예를 들면 다음과 같습니다.

1.  풀링된 프런트 엔드 서버를 두 번 클릭 합니다. 대화 상자가 열리면 **이 클러스터의 모든 해당 서버에 대해 ip 및 FQDN을 시작 점으로 사용**하 시겠습니까?를 선택 합니다.

2.  예를 들어 첫 번째 서버의 시작 값은 fe0101.contoso.com이 고 192.168.21.122의 IP 주소입니다.

3.  **프런트 엔드 서버 FQDN**에 **fe0.contoso.com** 를 입력 하 고 **프런트 엔드 서버 IP 주소**에 **192.168.21.131** 를 입력 한 다음 **확인**을 클릭 합니다.

4.  자동 증가 기능은 풀의 모든 서버를 fe01로 업데이트 하 고 192.168.21.131에서 136 까지의 모든 IP 주소를 구성 합니다.

모든 편집을 완료 한 후 다음 단계를 완료 하 여 토폴로지를 저장 합니다.

계획 도구 디자인을 저장 하려면 **파일**을 클릭 한 다음 **토폴로지 저장** 또는 **다른 이름으로 토폴로지 저장**을 클릭 합니다. **계획 도구 저장** 대화 상자가 표시 되는 경우 파일 **이름**에 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 디자인 편집](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

