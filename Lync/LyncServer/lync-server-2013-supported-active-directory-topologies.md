---
title: 'Lync Server 2013: 지원 되는 Active Directory 토폴로지'
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
ms.openlocfilehash: 46f9236bfbd110ee17811edec2e3e81fc4a0e0f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524165"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013의 지원 되는 Active Directory 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-10-02_

Lync Server 2013에서는 Microsoft Lync Server 2010 및 Microsoft Office Communications Server 2007 r 2와 동일한 Active Directory 도메인 서비스 토폴로지를 지원 합니다. 지원되는 토폴로지는 다음과 같습니다.

  - 도메인이 하나인 단일 포리스트

  - 트리가 하나이고 도메인이 여러 개인 단일 포리스트

  - 트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트

  - 중앙 포리스트 토폴로지의 다중 포리스트

  - 리소스 포리스트 토폴로지의 다중 포리스트

  - Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 다중 포리스트

다음 그림에서는 이 섹션의 그림에서 사용되는 아이콘을 보여 줍니다.

**토폴로지 그림의 기호**

![토폴로지 그림의 기호](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "토폴로지 그림의 기호")

<div>

## <a name="single-forest-single-domain"></a>단일 포리스트, 단일 도메인

Lync Server에서 지원 되는 가장 간단한 Active Directory 토폴로지 (단일 도메인 포리스트)는 일반적인 토폴로지입니다.

다음 그림에서는 단일 도메인 Active Directory 토폴로지의 Lync Server 배포를 보여 줍니다.

**단일 도메인 토폴로지**

![단일 도메인 토폴로지](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "단일 도메인 토폴로지")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>단일 포리스트, 여러 도메인

Lync Server에서 지원 되는 또 다른 Active Directory 토폴로지는 루트 도메인과 하나 이상의 자식 도메인으로 구성 되는 단일 포리스트입니다. 이러한 유형의 Active Directory 토폴로지에서 사용자를 만드는 도메인은 Lync Server를 배포 하는 도메인과 다를 수 있습니다. 그러나 프런트 엔드 풀을 배포하는 경우에는 단일 도메인 내에서 풀의 모든 프런트 엔드 서버를 배포해야 합니다. Windows 유니버설 관리자 그룹에 대 한 Lync Server 지원은 도메인 간 관리를 사용 하도록 설정 합니다.

다음 그림에서는 여러 도메인이 포함된 포리스트의 배포를 보여 줍니다. 이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고 화살표는 Lync Server 풀이 있는 도메인을 가리킵니다. 사용자 계정에는 다음이 포함됩니다.

  - Lync Server 풀과 같은 도메인 내의 사용자 계정

  - Lync Server 풀과 다른 도메인에 있는 사용자 계정

  - Lync Server 풀을 사용 하는 도메인의 하위 도메인에 있는 사용자 계정

**도메인이 여러 개인 단일 포리스트**

![도메인이 여러 개인 단일 포리스트](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "도메인이 여러 개인 단일 포리스트")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>단일 포리스트, 다중 트리

다중 트리 포리스트 토폴로지는 독립적인 트리 구조를 정의하는 두 개 이상의 도메인과 별도의 Active Directory 네임스페이스로 구성됩니다.

다음 그림에서는 트리가 여러 개인 단일 포리스트를 보여 줍니다. 이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고, 실선은 동일한 또는 다른 도메인에 있는 Lync Server 풀을 가리키며, 다른 트리에 있는 Lync Server 풀에 대 한 파선을 가리킵니다. 사용자 계정에는 다음이 포함됩니다.

  - Lync Server 풀과 같은 도메인 내의 사용자 계정

  - Lync Server 풀과는 다른 도메인과 같은 트리의 사용자 계정

  - Lync Server 풀과 다른 트리의 사용자 계정

**트리가 여러 개인 단일 포리스트**

![트리가 여러 개인 단일 포리스트](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "트리가 여러 개인 단일 포리스트")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>다중 포리스트, 중앙 포리스트

Lync Server에서는 중앙 포리스트 토폴로지에 구성 된 다중 포리스트를 지원 합니다. 중앙 포리스트 토폴로지는 중앙 포리스트의 대화 상대 개체를 사용 하 여 다른 포리스트의 사용자를 나타냅니다. 또한 중앙 포리스트는이 포리스트의 모든 사용자에 대 한 사용자 계정을 호스트 합니다. MIIS (Microsoft Identity Integration Server)와 같은 디렉터리 동기화 제품 Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Identity 수명 주기 관리자 (FP1)는 조직 내의 사용자 계정 수명 주기를 관리 2007 합니다. 새 사용자 계정을 포리스트 중 하나에서 만들거나 사용자 계정을 포리스트에서 삭제 하는 경우 디렉터리 동기화 제품이 중앙 포리스트의 해당 연락처와 동기화 합니다.

중앙 포리스트에는 다음과 같은 이점이 있습니다.

  - Lync Server를 실행 하는 서버는 단일 포리스트 내에서 중앙 집중식으로 관리 됩니다.

  - 사용자가 모든 포리스트에 있는 다른 사용자를 검색하고 이들과 통신할 수 있습니다.

  - 사용자가 모든 포리스트에 있는 다른 사용자의 현재 상태를 볼 수 있습니다.

  - 디렉터리 동기화 제품은 사용자 계정을 만들거나 제거할 때 중앙 포리스트에서 연락처 개체의 추가 및 삭제를 자동화합니다.

다음 그림에서는 중앙 포리스트 토폴로지를 보여 줍니다. 이 그림에서는 중앙 포리스트에 있는 Lync Server를 호스트 하는 도메인과 별도의 포리스트에 있는 각 사용자 전용 도메인 간에 양방향 트러스트 관계가 형성 됩니다. 개별 사용자 포리스트의 스키마는 확장할 필요가 없습니다.

**중앙 포리스트 토폴로지**

![중앙 포리스트 토폴로지](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "중앙 포리스트 토폴로지")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>다중 포리스트, 리소스 포리스트

리소스 포리스트 토폴로지에서는 한 포리스트는 Microsoft Exchange Server 및 Lync Server와 같은 서버 응용 프로그램을 실행 하는 전용입니다. 리소스 포리스트는 서버 응용 프로그램 및 활성 사용자 개체의 동기화된 표시를 호스팅하지만, 로그온할 수 있는 사용자 계정은 포함하지 않습니다. 리소스 포리스트는 사용자 개체가 있는 다른 포리스트에 대해 공유 서비스 환경 역할을 합니다. 사용자 포리스트는 리소스 포리스트와 포리스트 수준 트러스트 관계가 있습니다. 이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트의 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다. Microsoft Exchange가 이미 리소스 포리스트에 배포 되어 있는 경우 사용 하지 않도록 설정 된 사용자 계정이 이미 있을 수 있습니다. MIIS, Microsoft Forefront Identity Manager(FIM) 2010, 또는 Microsoft Identity Lifecycle Manager(ILM) 2007 FP1(Feature Pack 1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리합니다. 사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 포리스트에서 사용자 계정을 삭제하면 디렉터리 동기화 제품은 리소스 포리스트에서 해당 사용자 표시를 동기화합니다.

이 토폴로지는 다중 포리스트를 관리하는 조직에서 서비스를 위한 공유 인프라를 제공하거나 Active Directory 개체 관리를 다른 관리와 구분하는 데 사용할 수 있습니다. 보안상의 이유로 Active Directory 관리를 분리해야 하는 회사에서 이 토폴로지를 선택하는 경우가 많습니다.

이 토폴로지는 Active Directory 스키마를 단일 포리스트(리소스 포리스트)로만 확장해도 되는 이점을 제공합니다.

다음 다이어그램에서는 리소스 포리스트 토폴로지를 보여 줍니다.

**리소스 포리스트 토폴로지**

![Active Directory 리소스 포리스트 토폴로지](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 리소스 포리스트 토폴로지")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 다중 포리스트

이 토폴로지에서는 하나 이상의 포리스트가 온-프레미스에 있으며 Active Directory 사용자 계정 호스팅 전용입니다. 리소스 포리스트는 오프-프레미스에 있으며 타사 호스팅 공급자에 의해 유지 관리 됩니다. 리소스 포리스트에는 Lync Server 배포 및 온-프레미스 사용자 계정 포리스트에서 사용자 계정의 동기화 된 복제만 포함 됩니다. 로그온을 사용 하는 사용자 계정은 포함 하지 않습니다. Exchange는 온-프레미스 사용자 계정 포리스트 (Exchange Online과 함께 통합) 또는 온-프레미스 사용자 계정에 대 한 전자 메일 서비스가 Exchange Online에서 단독으로 제공 합니다.

리소스 포리스트는 사용자 개체가 상주 하는 온-프레미스 Active Directory 포리스트에 대 한 공유 서비스 환경으로 작동 합니다. 사용자 계정 포리스트에는 리소스 포리스트와 단방향 포리스트 수준 트러스트 관계가 있습니다. 이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트의 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다. MIIS, Microsoft Forefront Identity Manager(FIM) 2010, 또는 Microsoft Identity Lifecycle Manager(ILM) 2007 FP1(Feature Pack 1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리합니다. 사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 포리스트에서 사용자 계정을 삭제하면 디렉터리 동기화 제품은 리소스 포리스트에서 해당 사용자 표시를 동기화합니다. 다중 포리스트 배포를 구성 하는 방법에 대 한 자세한 내용은 [다중 포리스트 아키텍처에서 Lync 배포 (Exchange 하이브리드를 사용 하는 파트너 호스트 Lync)](https://go.microsoft.com/fwlink/p/?linkid=513216)를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

