---
title: 'Lync Server 2013: 토폴로지 테스트 문제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Lync Server 2013의 토폴로지 테스트 문제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

**CsTopology** cmdlet과 같이 모범 사례 분석기는 Lync Server 2013이 전역 수준에서 올바르게 작동 하는지 확인 하는 방법을 제공 합니다. 기본적으로 cmdlet과 같은 모범 사례 분석기는 전체 Lync Server 2013 인프라를 확인 하 고, 필요한 서비스가 실행 중인지 확인 하 고, 이러한 서비스 및 유니버설에 대해 적절 한 사용자 권한 및 사용 권한이 설정 되었는지 Lync Server 2013을 설치할 때 생성 되는 보안 그룹

Lync Server의 유효성을 전반적으로 확인 하는 것 외에도 **테스트-CsTopology** 는 특정 서비스의 유효성을 검사 합니다. Cmdlet을 사용 하 여 특정 서비스를 테스트 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 을 참조 하세요. 다음 정보를 사용 하 여 토폴로지의 문제를 해결할 수 있습니다.

<div>


> [!NOTE]  
> Edge 서버 구성 및 방화벽 설정 및 사용 권한을 비롯 한 관련 경계 네트워크 설정에 따라 모범 사례 분석기에서 Edge 서버에 액세스 하 고 검색 하지 못할 수 있습니다. 스캔에 Edge 서버를 포함 하는 경우 보고서에 Edge 서버에 액세스 하는 데 문제가 있는 것으로 표시 되는 경우 <STRONG>Edge 서버</STRONG> 확인란의 선택을 취소 하 고 스캔을 다시 실행 하 여 보고서에 문제가 표시 되지 않도록 합니다.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>토폴로지와 관련 한 문제 해결

토폴로지 테스트에서 토폴로지에 문제가 발견 되는 경우 이러한 문제는 토폴로지를 게시 하거나 사용할 수 있는 경우 발생 하는 문제로 인해 발생할 수 있습니다.

토폴로지를 변경 하면 변경 내용이 게시 되 고 사용 하도록 설정 된 경우에만 적용 됩니다. 토폴로지가 변경 되 게 하려면 토폴로지 작성기를 사용 해야 합니다. 변경한 후에는 토폴로지 작성기를 사용 하 여 해당 변경 내용을 게시 하 고 사용할 수 있습니다.

변경 내용을 게시할 때 새 사이트 또는 새 서버 역할 같은 새 정보가 중앙 관리 저장소에 기록 됩니다. 그러나 이러한 새로운 (또는 새로 수정 된) 개체는 토폴로지에 즉시 참여 하지 않습니다. 개체는 업데이트 된 토폴로지를 사용 하도록 설정한 경우에만 토폴로지에 참여 합니다. 토폴로지 작성기에서 게시 옵션을 선택 하는 경우이 두 단계가 모두 발생 합니다 (즉, 중앙 관리 저장소에 기록 됨), 새 토폴로지가 사용 하도록 설정 된 것입니다.

기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 **게시-CsTopology** Cmdlet 및 **Enable-CsTopology** cmdlet을 실행할 권한이 있습니다. 그러나 설정 권한이 위임 되지 않은 경우에는 도메인 관리자로 로그온 해야 **게시-CsTopology**를 실행할 수 있습니다. RTCUniversalServerAdmins cmdlet을 실제로 사용할 수 있는 권한을 부여 하려면 Lync Server services를 실행 **하는 컴퓨터** 를 포함 하는 모든 Active Directory 컨테이너에서 **부여-cssetuppermission** cmdlet을 실행 해야 합니다. **CsTopology** cmdlet을 사용할 권한을 RTCUniversalServerAdmins 제공 하려면 Lync Server services를 실행 하는 컴퓨터를 포함 하는 모든 Active Directory 도메인 서비스 컨테이너에 대해 **Set-cssetuppermission** cmdlet을 실행 해야 합니다. 토폴로지 작성기를 사용 하 여 토폴로지를 활성화 하 고 게시 하는 데이 사항이 적용 됩니다. **Set-CsSetupPermission**을 사용 하 여 사용 권한을 위임 하지 않은 경우 도메인 관리자만 토폴로지 작성기를 통해 토폴로지를 사용 하도록 설정 하 고 게시할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

