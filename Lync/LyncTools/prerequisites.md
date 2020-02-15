---
title: 필수 구성 요소
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a856a44a82af84f4881e487c5f853deeede72e07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>필수 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-19_

Lync Server 2013 스트레스 및 성능 도구를 실행 하는 데 필요한 다양 한 하드웨어, 소프트웨어 및 시스템 구성 요구 사항이 있습니다.

<div>

## <a name="client-hardware-requirements"></a>클라이언트 하드웨어 요구 사항

Lync Server 2013 배포에서 Lync Server 2013 스트레스 및 성능 도구를 실행 하려면 부하를 시뮬레이션할 모든 4500 사용자에 대해 다음 최소 하드웨어 요구 사항을 충족 하는 전용 컴퓨터가 하나 이상 필요 합니다.

  - 기가 비트 네트워크 어댑터 1 개

  - 8gb ram

  - 듀얼 코어 중앙 처리 장치 2 개 (Cpu)

</div>

<div>

## <a name="client-software-requirements"></a>클라이언트 소프트웨어 요구 사항

Lync Server 2013 배포에서 Lync Server 2013 스트레스 및 성능 도구를 실행 하려면 지원 되는 운영 체제는 다음과 같습니다.

  - Windows Server 2012 운영 체제

  - Windows Server 2008 운영 체제 (64 비트 버전)

클라이언트 컴퓨터에서 다음 소프트웨어 요구 사항을 충족 해야 합니다.

  - [Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212) runtime이 설치 되어 있어야 합니다.

  - Windows Server 2008/Windows Server 2012에서 데스크톱 경험 기능을 사용 하도록 설정 해야 합니다.

  - [Microsoft Visual c + + 2012 재배포 가능 패키지](http://go.microsoft.com/fwlink/?linkid=143216) (x64)가 설치 되어 있어야 합니다.

  - 완전히 구성 된 Lync Server 2013 배포

<div>


> [!IMPORTANT]  
> Microsoft 통합 커뮤니케이션 관리 API (c) 4.0 라이브러리는 설치 패키지에 포함 되어 있기 때문에, 클라이언트 컴퓨터에는 설치 되지 않아야 합니다.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>구성 요구 사항

Lync Server 2013 스트레스 및 성능 도구를 실행 하는 컴퓨터는 다음 요구 사항에 따라 구성 해야 합니다.

1.  Domain 또는 Local Admins 그룹의 구성원으로 로그온 해야 합니다.

2.  Lync server 2013 스트레스 및 성능 도구 (LyncPerfTool)는 Lync Server 2013 구성 요소도 실행 되는 컴퓨터에서 실행할 수 없습니다.

3.  프런트 엔드 서버 또는 사용자 계정이 상주할 Standard Edition 서버에서 Lync Server 2013 사용자 만들기 도구 (UserProvisioningTool)를 실행 해야 합니다. 도구를 여러 번 실행 하는 경우 Microsoft 통합 통신을 사용 하도록 설정 된 각 사용자에 게 고유한 전화 번호가 있어야 합니다.

4.  페이지 파일 크기는 시스템에서 관리 되거나 시스템의 RAM 크기의 1.5 배 이상 이어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

