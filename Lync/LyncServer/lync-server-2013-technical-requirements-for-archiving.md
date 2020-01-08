---
title: 'Lync Server 2013: 보관에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013의 보관에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

Lync Server 2013 기술 요구 사항에는 다음이 포함 됩니다.

  - 인프라 요구 사항.

  - 보관을 위해 설치 해야 하는 필수 구성 요소 소프트웨어입니다.

  - 보관을 위한 데이터 저장소 요구 사항.

  - 보관 배포에 대 한 확장 요구 사항 및 고려 사항

  - 보관 데이터베이스에 대 한 성능 요구 사항 및 고려 사항

<div>


> [!NOTE]  
> 이 Lync Server 2013 릴리스에서는 크기 조정 및 성능 정보를 사용할 수 없습니다.



</div>

<div>

## <a name="infrastructure-requirements"></a>인프라 요구 사항

Lync Server 2013 아카이빙 인프라 요구 사항은 Lync Server 2013를 배포 하는 경우와 동일 합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 인프라 요구 사항 확인](lync-server-2013-determining-your-infrastructure-requirements.md) 을 참조 하세요.

</div>

<div>

## <a name="archiving-prerequisites"></a>필수 구성 요소 보관

Lync Server 2013는 다음과 같은 이유로 보관을 위한 필수 구성 요소를 간소화 합니다.

  - 보관 서버는 더 이상 서버 역할이 아닙니다. 대신 통합 데이터 수집 에이전트는 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 보관을 위해 데이터를 캡처하기 위해 실행 되므로 보관을 위해 별도의 시스템 플랫폼을 설정 하지 않습니다.

  - 보관은 Lync Server 2013 파일 저장소를 사용 하 여 모임 콘텐츠 파일을 임시로 저장 하므로 보관을 위해 별도의 파일 저장소를 설정 하지 않아도 됩니다.

  - Lync Server 2013에서는 메시지 대기열이 필요 하지 않습니다.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>보관을 위한 데이터 저장소 요구 사항

또한 저장소 보관을 위한 인프라를 설정 해야 합니다. 여기에는 다음 중 하나 또는 모두 포함 됩니다.

  - **Microsoft Exchange 저장소**. PowerPoint 프레젠테이션과 같은 모임 콘텐츠 파일은 첨부 파일로 보관 됩니다. Lync 보관 데이터가 Exchange 준수 데이터와 함께 저장 되도록 Microsoft Exchange 통합을 사용 하려는 경우 exchange 배포에 Exchange 2013를 사용 하 고 최대 저장소 크기가 모임 콘텐츠 파일의 저장소를 지원 하는지 확인 해야 합니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하는 경우 Lync 보관 데이터는 exchange 2013 서버에 속한 사용자 에게만 Exchange 2013 준수 데이터와 함께 저장 됩니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하 고 사용 하기 전에 Exchange 2013를 배포 해야 합니다. Exchange 2013 저장소를 사용 하도록 선택한 경우 Exchange 2013 서버에서 홈이 아닌 Lync 사용자가 없는 경우 보관을 위해 별도의 SQL Server 데이터베이스를 배포할 필요가 없습니다.

  - **보관을 위한 SQL Server 데이터베이스 저장소**. Exchange 2013 서버에 속하지 않는 사용자를 지원 하거나 Microsoft Exchange 통합 옵션을 사용 하지 않으려는 경우 SQL Server 데이터베이스를 사용 하 여 보관 저장소를 배포 해야 합니다. Lync Server 2013는 다음과 같은 64 비트 버전의 SQL Server를 지원 합니다.
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 및 Microsoft SQL Server 2012 Express는 보관에 지원 되지 않습니다. 32 비트 버전의 SQL Server는 지원 되지 않습니다. SQL Server 요구 사항에 대 한 자세한 내용은 계획 문서 또는 지원 가능성 설명서의 <A href="lync-server-2013-database-software-support.md">Lync Server 2013에서 데이터베이스 소프트웨어 지원을</A> 참조 하세요.

    
    </div>
    
    보관을 배포 하 고 사용 하기 전에 SQL Server 플랫폼을 설정 해야 합니다. 토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 관리자 권한과 사용 권한이 있는 경우, 토폴로지를 게시할 때 LcsLog (보관 데이터베이스)를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다. SQL Server에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)Sql server TechCenter을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

