---
title: 'Lync Server 2013: 프런트 엔드 서버에 IP 주소 유형 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3be24a05cf75adfc999205bb306010ba43fa1d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Lync Server 2013에 대 한 프런트 엔드 서버에 IP 주소 유형 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-07-28_

토폴로지 작성기를 사용 하 여 프런트 엔드 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형을 배포하려면

1.  **Enterprise Edition 프런트 엔드 풀** 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 선택합니다. 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집**을 클릭합니다.

2.  **속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 다음 그림과 같이 **IPv4 사용**과 **IPv6 사용**을 선택합니다.
    
    **프런트 엔드 서버 풀에 대한 속성 편집 대화 상자**
    
    ![프런트 엔드 서버 속성 편집 대화 상자](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "프런트 엔드 서버 속성 편집 대화 상자")
    
      - **구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.
        
        <div>
        

        > [!NOTE]  
        > 이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.

        
        </div>
    
      - **선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 **기본 IP 주소**의 값을 입력해야 합니다.
    
      - **기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.
    
      - **PSTN IP 주소**. Lync Server 2013에 대 한 PSTN IP 주소 구성을 지원 하기 위해 추가 NIC (네트워크 인터페이스 카드)를 설치 하는 것은 배치 된 중재 서버 역할에서 지원 되지 않습니다. Lync Server 2013에 대해 지원 되는 NIC 구성에 대 한 자세한 내용은 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

