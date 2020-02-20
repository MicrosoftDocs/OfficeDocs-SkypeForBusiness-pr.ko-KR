---
title: 'Lync Server 2013: Lync Server 관리 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ba9b1d9848fa51d798dd93b9cbc53daf69a6b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 관리 도구

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

이 항목에서는 Lync Server 2013의 관리 도구에 대해 설명 합니다.

관리 도구는 각 Lync Server 서버에 기본적으로 설치 됩니다. 또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다. 관리 도구를 설치 하는 절차는 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오. 관리 작업을 수행 하는 도구를 여는 절차는 [Open Lync Server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

Lync Server 관리 도구를 설치 하거나 사용 하기 전에 인프라, 운영 체제, 소프트웨어 및 관리자 권한 요구 사항을 검토 해야 합니다. 인프라 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 관리 도구 인프라 요구 사항을](lync-server-2013-administrative-tools-infrastructure-requirements.md)참조 하세요. Lync Server 관리 도구를 설치 하기 위한 운영 체제 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [lync server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md), lync server [2013의 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)및 [lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md)참조 하세요. 이 도구를 설치 및 사용 하기 위해 필요한 사용자 권한 및 사용 권한은 [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한에](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)설명 되어 있습니다.

관리 도구는 다음 항목으로 구성됩니다.

  - **Lync server 배포 마법사**   를 사용 하 여 lync server를 배포 하 고 모든 관리 도구를 설치 합니다.

  - **Lync Server 토폴로지 작성기**   를 사용 하 여 배포의 구성 요소를 정의 합니다.

  - **Lync Server 제어판**   은 웹 기반 인터페이스를 사용 하 여 배포를 지속적으로 관리 하는 데 사용 됩니다.

  - **Lync Server 관리 셸**   명령줄을 사용 하 여 배포를 지속적으로 관리 하는 데 사용 됩니다.

  - **Lync Server 로깅 도구**   를 사용 하 여 배포 문제를 해결할 수 있습니다.

  - **중앙 로깅 서비스**   는 한 컴퓨터, 풀, 사이트 또는 전역에서 로그 및 추적 파일을 수집 합니다. 공급자, 플래그 및 추적 수준이 포함 된 시나리오를 선택 하 고 정의 합니다. 로깅은 텍스트 기반 도구 또는 Snooper와 같은 도구를 사용 하 여 수집 및 집계 되 고 표시 됩니다.

기본적으로 토폴로지 작성기 및 Lync Server 제어판을 사용 하 여 배포를 관리할 수 있습니다.

<div>

## <a name="deployment-wizard"></a>배포 마법사

Lync Server를 아직 설치 하지 않은 컴퓨터에 설치 미디어에 포함 된 Lync Server 배포 마법사를 사용 하 여 모든 관리 도구를 설치 해야 합니다. 관리 도구 설치 프로세스 중에 Lync Server 배포 마법사는 다른 도구와 함께 로컬로 설치 되므로 나중에 추가 구성 요소에 대 한 파일을 설치 하거나, 필요 하지 않은 구성 요소에 대 한 파일을 제거할 수 있습니다. 컴퓨터.

Lync Server 설치 미디어에서 처음으로 Lync Server 배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 [Install Lync server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.

</div>

<div>

## <a name="topology-builder"></a>토폴로지 작성기

토폴로지 작성기를 사용 하 여 수행할 수 있는 배포 작업에 대 한 자세한 내용은 각 서버 역할에 대 한 배포 설명서를 참조 하십시오.

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 제어판

Lync Server 2013 제어판을 사용 하 여 Lync Server 2013를 관리 하 고 유지 관리 하는 데 필요한 대부분의 관리 작업을 수행할 수 있습니다. Lync Server 제어판은 조직의 사용자, 클라이언트 및 장치 외에도 Lync Server 실행 서버의 구성을 관리 하기 위한 GUI (그래픽 사용자 인터페이스)를 제공 합니다. Lync server 관리 셸이 lync server 제어판을 기본 메커니즘으로 사용 하 여 Lync Server 구성을 수행 합니다.

Lync Server 제어판은 모든 Lync Server 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다. 이번 릴리스에서는 에지 서버를 원격으로 관리합니다. Lync server를 중앙에서 관리 하려는 관리 콘솔과 같은 다른 컴퓨터에 Lync Server 제어판을 설치할 수도 있습니다. 자세한 내용은 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 제어판을 사용 하 여 설정을 구성 하려면 CsAdministrator 역할에 할당 된 계정을 사용 하 여 로그인 해야 합니다. Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync server 2013에서 역할 기반 액세스 제어 계획</A>을 참조 하십시오.</P>
> <LI>
> <P>Lync Server 제어판을 사용 하 여 설정을 구성 하려면 최소 화면 해상도 1024 x 768의 컴퓨터도 사용 해야 합니다.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Communications Server 관리 셸

Lync Server에서 Lync Server 관리 셸은 관리 및 관리에 대 한 새로운 방법을 제공 합니다. Lync Server 관리 셸은 Windows PowerShell 명령줄 인터페이스를 기반으로 작성 된 강력한 관리 인터페이스로, Lync Server와 관련 된 포괄적인 cmdlet 집합이 포함 되어 있습니다. Lync Server 관리 셸을 사용 하 여 다양 한 구성 및 자동화 컨트롤을 얻을 수 있습니다. 토폴로지 작성기 및 Lync Server 제어판 둘 다 Lync Server의 관리를 지원 하기 위해 이러한 cmdlet의 하위 집합을 구현 합니다. Lync Server 관리 셸에서는 모든 Lync Server 관리 작업에 대 한 cmdlet이 포함 되며,이 cmdlet을 개별적으로 사용 하 여 배포를 관리할 수 있습니다. 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서 또는 각 cmdlet에 대 한 명령줄 도움말을 참조 하십시오.

</div>

<div>

## <a name="logging-tool"></a>로깅 도구

Lync Server 로깅 도구를 이용 하면 제품을 실행 하는 동안 제품에서 로깅 및 추적 정보를 캡처하여 문제를 쉽게 해결할 수 있습니다. 이 도구를 사용 하 여 모든 Lync Server 서버 역할에서 디버그 세션을 실행할 수 있습니다. 로깅 도구에 대 한 자세한 내용은 TechNet 라이브러리에서 Lync Server 2010 로깅 도구 설명서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).

<div>


> [!IMPORTANT]  
> 중앙 로깅 서비스는 모든 상황에서 Lync Server 로깅 도구를 통해 모든 로깅 수집에 권장 됩니다. Lync Server 로깅 도구는 계속 작동 하지만, 중앙 로깅 서비스가 이미 실행 되 고 있는 경우에는 거의 대부분의 경우에는 비효율적으로 렌더링 됩니다. 중앙 로깅 서비스 또는 Lync Server 로깅 도구를 하나만 사용 해야 하며 동시에 수행 해서는 안 됩니다. 중앙 로깅 서비스에 대 한 자세한 내용과 단독으로 사용 해야 하는 이유는 <A href="lync-server-2013-using-the-centralized-logging-service.md">Lync Server 2013에서 중앙화 된 로깅 서비스 사용</A>을 참조 하세요.



</div>

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 관리 도구 인프라 요구 사항](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013의 관리 도구 소프트웨어 요구 사항](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Lync Server 2013의 토폴로지 게시 요구 사항](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 제어판 문제 해결](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Lync Server 2013에서 중앙 로깅 서비스 사용](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

