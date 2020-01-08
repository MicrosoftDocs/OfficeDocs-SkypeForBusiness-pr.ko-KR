---
title: 'Lync Server 2013: 에지 구성 요소에 대한 인증서 요청'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Lync Server 2013에서 에지 구성 요소에 대한 인증서 요청

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

외부 사용자 액세스를 지 원하는 데 필요한 인증서에는 공용 CA (인증 기관)에서 발급 한 인증서와 내부 엔터프라이즈 CA에서 발급 한 인증서가 포함 됩니다.

  - Edge 서버의 외부 인터페이스와 역방향 프록시에 필요한 인증서는 공용 CA에서 발급 해야 합니다.

  - 내부 인터페이스에 필요한 인증서는 공용 CA 또는 내부 엔터프라이즈 CA 중 하나에서 발급할 수 있습니다. 공용 인증서를 사용 하 여 비용을 절약 하기 위해 이러한 인증서를 만드는 데 사용할 수 있는 내부 Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows server 2012 CA 또는 Windows Server 2012 R2 CA를 사용 하는 것이 좋습니다.

<div>


> [!IMPORTANT]  
> 인증서 요청 (특히 공용 Ca에 대 한 요청)을 처리 하는 데 시간이 걸릴 수 있으므로 edge 서버 구성 요소 배포를 시작할 때 사용할 수 있도록 먼저 Edge 서버에 대 한 인증서를 요청 해야 합니다. Edge 서버의 인증서 요구 사항에 대 한 요약 정보는 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을</A>참조 하세요.



</div>

내부에 지 인증서에 대해 공용 CA를 사용할 수 있지만, 인증서 비용을 최소화 하는 대신 다른 인증서에 대해 내부 엔터프라이즈 CA를 사용 하는 것이 좋습니다. Edge 서버의 인증서 요구 사항에 대 한 요약 정보는 [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요.

<div>


> [!NOTE]  
> Edge 서버를 설치할 때 설치 프로그램에는 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013의 Edge 인증서 설정</A> 섹션에 설명 된 대로 인증서 요청, 할당 및 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다. Edge 서버를 설치 하기 전에 인증서를 요청 하는 경우 (예: Edge 서버 구성 요소의 실제 배포 중에 시간을 절약 하는 경우), 인증서를 내보낼 수 있고 모든 작업을 포함 하는 경우 내부 서버를 사용 하는 것이 좋습니다. 필수 주제 대체 이름입니다. 이 설명서에서는 내부 서버를 사용 하 여 인증서를 요청 하는 절차는 제공 하지 않습니다.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>공용 CA에 인증서 요청

Edge 서버 배포에는 Edge 서버의 외부 인터페이스에 대 한 단일 공용 인증서가 필요 하며, 여기에는 Access Edge 서비스, 웹 회의 Edge 서비스, 그리고/V 인증 서비스에 사용 됩니다. A/V 인증 서비스에서 풀의 모든 Edge 서버에 동일한 키를 사용 하도록 하려면이 인증서에는 내보낼 수 있는 개인 키가 있어야 합니다. Microsoft Internet Security 및 가속 (ISA) 서버 2006 또는 Microsoft Forefront Threat Management Gateway 2010에 사용 되는 역방향 프록시에도 공용 인증서가 필요 합니다.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>내부 엔터프라이즈 CA에서 인증서 요청

내부에 지 인터페이스에 필요한 인증서는 공용 ca (인증 기관) 또는 내부 CA에 의해 발급 될 수 있습니다. 내부 엔터프라이즈 CA를 사용 하 여 인증서 비용을 최소화할 수 있습니다. 조직에 내부 CA가 배포 되어 있는 경우 내부에 지에 대 한 인증서가 내부 CA에 의해 발급 되어야 합니다. 내부 인증서에 내부 엔터프라이즈 CA를 사용 하 여 인증서 비용을 줄일 수 있습니다.

Edge 구성 요소의 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스를 위한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요. 공용 CA를 사용 하 여 인증서를 가져오는 방법에 대 한 자세한 내용은 [Lync Server 2013의 edge 구성 요소에 대 한 인증서 요청](lync-server-2013-request-certificates-for-edge-components.md)을 참조 하세요. 인증서 요청, 설치 및 할당에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Edge 인증서 설정을](lync-server-2013-set-up-edge-certificates.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

