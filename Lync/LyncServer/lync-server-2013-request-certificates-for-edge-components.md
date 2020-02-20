---
title: Lync Server 2013:에 지 구성 요소에 대 한 인증서 요청
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 473d526bbdf8f556f167c80cc3b654f336f78070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Lync Server 2013의에 지 구성 요소에 대 한 인증서 요청

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

외부 사용자 액세스를 지원하는 데 필요한 인증서에는 공용 CA(인증 기관)에서 발급한 인증서와 내부 엔터프라이즈 CA에서 발급한 인증서가 포함됩니다.

  - 에 지 서버 및 역방향 프록시에 대 한 외부 인터페이스에 필요한 인증서는 공용 CA에서 발급 해야 합니다.

  - 외부 인터페이스에 필요한 인증서는 공용 CA 또는 내부 엔터프라이즈 CA에서 발급한 인증서일 수 있습니다. 내부 Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 ca 또는 Windows 2012 Server 2008 R2 CA를 사용 하 여 공용 인증서를 사용 하는 비용에도 이러한 인증서를 만들어 저장 하는 것이 좋습니다.

<div>


> [!IMPORTANT]  
> 인증서 요청 처리 시간 (특히 공용 CAs에 대 한 요청)을 처리할 때에는에 지 서버 구성 요소에 대 한 배포를 시작할 때에도 사용할 수 있도록 해당 서버에 대 한 인증서를 빠르게 요청 해야 합니다. 에 지 서버에 대 한 인증서 요구 사항을 요약 한 내용은 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을</A>참조 하십시오.



</div>

내부 에지 인증서에 공용 CA를 사용하도록 선택할 수 있긴 하지만 인증서 비용을 최소화하는 대신 그러한 다른 인증서에 내부 엔터프라이즈 CA를 사용하는 것이 좋습니다. 에 지 서버에 대 한 인증서 요구 사항을 요약 한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오.

<div>


> [!NOTE]  
> 에 지 서버를 설치할 때 설치 프로그램에는 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013에 대 한 edge 인증서 설정</A> 섹션에 설명 된 대로 인증서 요청, 할당 및 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다. Edge 서버를 설치 하기 전에 인증서를 요청 하려는 경우 (예:에 지 서버 구성 요소의 실제 배포 중에 시간을 절약 하는 것과 같은) 내부 서버를 사용 하 여 인증서를 내보낼 수 있게 하 고 모든 작업을 포함 하는 경우 필요한 주체 대체 이름입니다. 이 설명서에서는 내부 서버를 사용하여 인증서를 요청하는 절차는 제공하지 않습니다.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>공용 CA에서 인증서 요청

에 지 서버 배포에는 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V 인증 서비스에 사용 되는에 지 서버의 외부 인터페이스에 대 한 단일 공용 인증서가 필요 합니다. A/V 인증 서비스가 풀의 모든에 지 서버에서 동일한 키를 사용 하 게 하려면이 인증서에는 내보낼 수 있는 개인 키가 있어야 합니다. Microsoft Internet Security and 가속도 (ISA) 서버 2006 또는 Microsoft Forefront Threat Management Gateway 2010와 함께 사용 되는 역방향 프록시에도 공용 인증서가 필요 합니다.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>내부 엔터프라이즈 CA에서 인증서 요청

내부 에지 인터페이스에 필요한 인증서는 공용 CA(인증 기관) 또는 내부 CA에서 발급한 인증서일 수 있습니다. 내부 엔터프라이즈 CA를 사용하면 인증서 비용을 최소화할 수 있습니다. 조직에 내부 CA가 배포되어 있는 경우에는 내부 에지용 인증서를 내부 CA에서 발급해야 합니다. 내부 인증서에 대해 내부 엔터프라이즈 CA를 사용하면 인증서 비용을 줄일 수 있습니다.

에 지 구성 요소에 대 한 인증서 요구 사항을 요약 한 내용은 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하십시오. 공용 CA를 사용 하 여 인증서를 가져오는 방법에 대 한 자세한 내용은 [Lync Server 2013에서에 지 구성 요소에 대 한 인증서 요청](lync-server-2013-request-certificates-for-edge-components.md)을 참조 하세요. 인증서 요청, 설치 및 할당에 대 한 자세한 내용은 [Set Up Edge certificate For Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

