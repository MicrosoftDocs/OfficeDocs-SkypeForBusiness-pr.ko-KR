---
title: 'Lync Server 2013: 지원되는 Active Directory 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013에서 지원되는 Active Directory 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-10-02_

Lync Server 2013는 Microsoft Lync Server 2010 및 Microsoft Office Communications Server 2007 R2와 동일한 Active Directory 도메인 서비스 토폴로지를 지원 합니다. 다음과 같은 토폴로지가 지원 됩니다.

  - 단일 도메인이 있는 단일 포리스트

  - 단일 트리 및 여러 도메인이 있는 단일 포리스트

  - 여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트

  - 중앙 포리스트 토폴로지의 여러 포리스트

  - 리소스 포리스트 토폴로지의 여러 포리스트

  - Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 여러 포리스트

다음 그림은이 섹션의 일러스트레이션에 사용 된 아이콘을 나타냅니다.

**토폴로지 그림의 기호**

![토폴로지 그림의 기호](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "토폴로지 그림의 기호")

<div>

## <a name="single-forest-single-domain"></a>단일 포리스트, 단일 도메인

Lync Server에서 지원 되는 가장 간단한 Active Directory 토폴로지 인 단일 도메인 포리스트는 일반적인 토폴로지입니다.

다음 그림은 단일 도메인 Active Directory 토폴로지에서 Lync Server 배포를 보여 줍니다.

**단일 도메인 토폴로지**

![단일 도메인 토폴로지](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "단일 도메인 토폴로지")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>단일 포리스트, 여러 도메인

Lync Server에서 지원 되는 다른 Active Directory 토폴로지는 루트 도메인과 하나 이상의 자식 도메인으로 구성 된 단일 포리스트입니다. 이러한 유형의 Active Directory 토폴로지에서는 사용자가 만드는 도메인이 Lync Server를 배포 하는 도메인과 다를 수 있습니다. 그러나 프런트 엔드 풀을 배포 하는 경우에는 풀의 모든 프런트 엔드 서버를 단일 도메인 내에 배포 해야 합니다. Windows 유니버설 관리자 그룹에 대 한 Lync 서버 지원은 도메인 간 관리를 가능 하 게 합니다.

다음 그림은 여러 도메인이 있는 단일 포리스트에 배포 하는 방법을 보여 줍니다. 이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고 화살표는 Lync 서버 풀이 있는 도메인을 가리킵니다. 사용자 계정에는 다음이 포함 됩니다.

  - Lync Server 풀과 동일한 도메인 내의 사용자 계정

  - Lync Server 풀의 다른 도메인에 있는 사용자 계정

  - Lync Server 풀을 사용 하 여 도메인의 자식 도메인에 있는 사용자 계정

**도메인이 여러 개인 단일 포리스트**

![도메인이 여러 개인 단일 포리스트](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "도메인이 여러 개인 단일 포리스트")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>단일 포리스트, 여러 트리

다중 트리 포리스트 토폴로지는 독립 트리 구조와 별도의 Active Directory 네임 스페이스를 정의 하는 둘 이상의 도메인으로 구성 됩니다.

다음 그림은 여러 트리가 있는 단일 포리스트를 보여 줍니다. 이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고, 실선은 같은 도메인에 있는 Lync 서버 풀을 가리킵니다. 다른 트리에 있는 Lync 서버 풀을 가리키는 파선입니다. 사용자 계정에는 다음이 포함 됩니다.

  - Lync Server 풀과 동일한 도메인 내의 사용자 계정

  - 다른 도메인에 있는 사용자 계정 (그러나 같은 트리)은 Lync 서버 풀과 동일 합니다.

  - Lync Server 풀의 다른 트리에 있는 사용자 계정

**트리가 여러 개인 단일 포리스트**

![트리가 여러 개인 단일 포리스트](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "트리가 여러 개인 단일 포리스트")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>다중 포리스트, 중앙 포리스트

Lync Server는 중앙 포리스트 토폴로지에 구성 된 여러 포리스트를 지원 합니다. 중앙 포리스트 토폴로지는 중앙 포리스트의 연락처 개체를 사용 하 여 다른 포리스트의 사용자를 나타냅니다. 또한 중앙 포리스트는이 포리스트의 모든 사용자에 대 한 사용자 계정을 호스팅합니다. MIIS (Microsoft Id 통합 서버), Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1) 등의 디렉터리 동기화 제품에서 사용자 계정의 수명 주기를 관리 합니다. 조직: 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 중앙 포리스트의 해당 연락처를 동기화 합니다.

중앙 포리스트의 장점은 다음과 같습니다.

  - Lync Server를 실행 하는 서버는 단일 포리스트 내에서 중앙 집중화 됩니다.

  - 사용자는 모든 포리스트에서 다른 사용자를 검색 하 고 통신할 수 있습니다.

  - 사용자는 모든 포리스트에서 다른 사용자의 현재 상태를 볼 수 있습니다.

  - 디렉터리 동기화 제품은 사용자 계정이 만들어지거나 제거 될 때 중앙 포리스트에서 연락처 개체의 추가 및 삭제를 자동화 합니다.

다음 그림은 중앙 포리스트 토폴로지를 보여 줍니다. 이 그림에는 중앙 포리스트의 Lync Server를 호스트 하는 도메인과 별도 포리스트의 각 사용자 전용 도메인 사이에 양방향 트러스트 관계가 있습니다. 별도의 사용자 포리스트에 있는 스키마는 확장할 필요가 없습니다.

**중앙 포리스트 토폴로지**

![중앙 포리스트 토폴로지](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "중앙 포리스트 토폴로지")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>다중 포리스트, 리소스 포리스트

리소스 포리스트 토폴로지에서 하나의 포리스트는 Microsoft Exchange Server 및 Lync Server와 같은 서버 응용 프로그램을 실행 하는 것을 전담 합니다. 리소스 포리스트는 활성 사용자 개체의 서버 응용 프로그램 및 동기화 된 표시를 호스팅하고 있지만 로그온이 지원 되는 사용자 계정은 포함 하지 않습니다. 리소스 포리스트는 사용자 개체가 상주 하는 다른 포리스트의 공유 서비스 환경 역할을 합니다. 사용자 포리스트에는 리소스 포리스트와 포리스트 수준의 신뢰 관계가 있습니다. 이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트에 있는 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다. Microsoft Exchange가 이미 리소스 포리스트에 배포 되어 있는 경우 사용 하지 않도록 설정 된 사용자 계정이 이미 있을 수 있습니다. MIIS, Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리 합니다. 사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 리소스 포리스트의 해당 사용자 표현을 동기화 합니다.

이 토폴로지를 사용 하 여 여러 포리스트를 관리 하는 조직의 서비스에 대 한 공유 인프라를 제공 하거나 다른 관리에서 Active Directory 개체의 관리를 분리할 수 있습니다. 보안상의 이유로 Active Directory 관리를 격리 해야 하는 기업은이 토폴로지를 선택 하는 경우가 많습니다.

이 토폴로지는 Active Directory 스키마를 단일 포리스트 (즉, 리소스 포리스트)로 확장할 필요가 없도록 제한 하는 이점을 제공 합니다.

다음 다이어그램은 리소스 포리스트 토폴로지를 보여줍니다.

**리소스 포리스트 토폴로지**

![Active Directory 리소스 포리스트 토폴로지](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 리소스 포리스트 토폴로지")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 여러 포리스트

이 토폴로지에서는 하나 이상의 포리스트가 온-프레미스에 있으며 Active Directory 사용자 계정 호스팅 전용입니다. 리소스 포리스트는 오프 라인으로 배치 되며 타사 호스팅 공급자에 의해 유지 관리 됩니다. 리소스 포리스트에는 온-프레미스 사용자 계정 포리스트의 사용자 계정에 대 한 동기화 된 복제 및 Lync Server 배포만 포함 됩니다. 로그온 할 수 있는 사용자 계정이 포함 되어 있지 않습니다. Exchange는 Exchange Online (하이브리드)과 함께 통합 된 온-프레미스 사용자 계정 포리스트에서 배포 되거나 온-프레미스 사용자 계정에 대 한 전자 메일 서비스가 Exchange Online에서 독점적으로 제공 됩니다.

리소스 포리스트는 사용자 개체가 상주 하는 온-프레미스 Active Directory 포리스트의 공유 서비스 환경 역할을 합니다. 사용자 계정 포리스트는 리소스 포리스트와 단방향 포리스트 수준의 트러스트 관계입니다. 이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트에 있는 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다. MIIS, Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리 합니다. 사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 리소스 포리스트의 해당 사용자 표현을 동기화 합니다. 다중 포리스트 배포를 구성 하는 방법에 대 한 자세한 내용은 [다중 포리스트 아키텍처에서 Lync 배포 (Exchange 하이브리드을 사용 하는 파트너 호스트 Lync)](http://go.microsoft.com/fwlink/p/?linkid=513216)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

