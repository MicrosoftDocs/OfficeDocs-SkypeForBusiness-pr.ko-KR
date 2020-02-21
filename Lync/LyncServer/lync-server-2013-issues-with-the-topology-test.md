---
title: 'Lync Server 2013: 토폴로지 테스트 관련 문제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 테스트 관련 문제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

**Enable-cstopology** cmdlet과 마찬가지로 모범 사례 분석기를 통해 Lync Server 2013이 전역 수준에서 올바르게 작동 하는지 확인할 수 있습니다. 기본적으로 cmdlet과 같은 모범 사례 분석기에서는 전체 Lync Server 2013 인프라를 확인 하 고, 필요한 서비스가 실행 되 고 있는지 확인 하 고, 이러한 서비스 및 유니버설에 대해 적절 한 사용자 권한 및 사용 권한을 설정 해야 합니다. Lync Server 2013를 설치할 때 만들어지는 보안 그룹입니다.

Lync Server 전체적으로 유효성을 확인 하는 것 외에도 **enable-cstopology** 에서는 특정 서비스의 유효성을 검사 합니다. Cmdlet을 사용 하 여 특정 서비스를 테스트 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [enable-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 를 참조 하십시오. 토폴로지 문제를 해결하는 데 도움이 필요하면 다음 정보를 참조하십시오.

<div>


> [!NOTE]  
> 방화벽 설정과 권한을 포함하여 에지 서버 및 관련 경계 네트워크 설정의 구성에 따라 모범 사례 분석기가 에지 서버를 액세스하고 검색하지 못할 수 있습니다. 검색에 에지 서버를 포함하고 보고서에 에지 서버 액세스 문제가 표시되면 <STRONG>에지 서버</STRONG> 확인란의 선택을 취소하고 검색을 다시 실행해서 문제가 보고서에 표시되지 않도록 합니다.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>토폴로지 문제 해결

토폴로지 테스트로 토폴로지 문제가 발견된 경우 이러한 문제는 토폴로지를 게시하거나 사용하도록 설정할 때 발생한 문제로 인한 것일 수 있습니다.

토폴로지를 변경할 때는 토폴로지를 게시하고 사용하도록 설정한 경우에만 변경 내용이 적용됩니다. 토폴로지를 변경 하려면 토폴로지 작성기를 사용 해야 합니다. 변경한 후에는 토폴로지 작성기를 사용 하 여 이러한 변경 내용을 게시 하 고 사용 하도록 설정할 수 있습니다.

변경 내용을 게시 하면 새 사이트 또는 새 서버 역할 등의 새 정보가 중앙 관리 저장소에 기록 됩니다. 그러나 이러한 새 개체 또는 새로 수정한 개체가 토폴로지에 즉시 조인되는 것은 아닙니다. 개체는 사용자가 업데이트한 토폴로지를 사용하도록 설정할 때만 토폴로지에 참가합니다. 토폴로지 작성기에서 게시 옵션을 선택 하면 변경 내용이 게시 되 고 (중앙 관리 저장소에 기록 됨) 새 토폴로지가 사용 되도록 설정 됩니다.

기본적으로 RTCUniversalServerAdmins 그룹의 구성원에게는 **Publish-CsTopology** cmdlet 및 **Enable-CsTopology** cmdlet을 실행할 수 있는 권한이 부여됩니다. 하지만 설정 권한이 위임되지 않은 경우 **Publish-CsTopology**를 실행하려면 도메인 관리자로 로그온해야 합니다. **Enable-cstopology** cmdlet을 실제로 사용 하는 권한을 RTCUniversalServerAdmins에 게 제공 하려면 Lync Server 서비스를 실행 하는 컴퓨터를 포함 하는 모든 Active Directory 컨테이너에서 **-cssetuppermission** cmdlet을 실행 해야 합니다. RTCUniversalServerAdmins에서 **enable-cstopology** cmdlet을 사용할 수 있는 권한을 부여 하려면 Lync Server services를 실행 하는 컴퓨터를 포함 하는 모든 Active Directory 도메인 서비스 컨테이너에 대해 **Set-cssetuppermission** cmdlet을 실행 해야 합니다. 이는 토폴로지 작성기를 사용 하 여 토폴로지를 활성화 하 고 게시 하는 데 적용 됩니다. **Set-CsSetupPermission**을 사용 하 여 사용 권한을 위임 하지 않은 경우 도메인 관리자만 토폴로지 작성기를 통해 토폴로지를 사용 하도록 설정 하 고 게시할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

