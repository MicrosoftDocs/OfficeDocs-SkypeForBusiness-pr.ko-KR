---
title: 'Lync Server 2013: 에지 서버에 IP 주소 유형 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a094a39fd74ab30ee1dd3a5a3da4e777bcf7e338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>Lync Server 2013의 에지 서버에 IP 주소 유형 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-14_

토폴로지 작성기를 사용 하 여 Edge 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Edge 서버에 IP 주소 유형을 배포 하려면

1.  토폴로지 작성기의 **Edge 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다. 또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.

2.  **속성 편집** 창에서 지원 하려는 IP 주소 구성을 선택 합니다. 다음 그림은 내부 인터페이스 및 외부 인터페이스에 대 한 이중 스택 구성을 보여 줍니다.
    
    **듀얼 스택형 Edge 서버 내부 인터페이스**
    
    ![Lync server 일반 속성 페이지](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "lync server 일반 속성 페이지")
    
    **듀얼 스택형 Edge 서버 외부 인터페이스**
    
    ![Lync server 다음 홉/외부 구성 페이지](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "lync server 다음 홉/외부 구성 페이지")

3.  선택한 각 주소 유형에 대해 적절 한 내부 및 외부 주소를 제공 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

