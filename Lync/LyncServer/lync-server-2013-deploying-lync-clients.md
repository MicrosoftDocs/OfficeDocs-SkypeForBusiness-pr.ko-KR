---
title: 'Lync Server 2013: Lync 클라이언트 배포'
description: 'Lync Server 2013: Lync 클라이언트 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09b501fc721ac880c5cf7da0293e3aa9c6443722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573434"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a>Lync Server 2013에서 Lync 클라이언트 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

Lync 2013에는 클라이언트 배포와 다른 방식이 도입 되었습니다. 이전 릴리스에서는 출발 했지만 Lync 2013에는 더 이상 자체 설치 관리자가 없습니다. 대신 Office 2013 설치 프로그램에 Lync가 포함 되어 있습니다. 사용자에 게 Lync 2013을 배포 하려면 Office 2013 설치 방법 및 사용자 지정 도구를 사용할 수 있습니다.

  - **Office 2013 Windows installer** 는 여러 MSI 파일로 구성 된 windows installer 기반 설치 패키지입니다. 언어 중립적인 핵심 MSI 패키지는 완벽한 제품 구성을 위해 하나 이상의 언어별 패키지로 조합됩니다. 설치 프로그램은 개별 패키지를 조합하고 사용자 컴퓨터에 Office를 설치하는 동안 그리고 설치 후에 사용자 지정 및 유지 관리 작업을 수행합니다. 이 섹션의 항목에서는 Office 2013 Windows Installer를 사용 하 고 사용자 지정 하 여 Lync 2013를 배포 하는 방법에 대해 설명 합니다.

  - **Office 2013 간편 실행** 은 Microsoft 365 관리 센터에서 office 설치 파일을 사용자에 게 스트리밍하는 설치 프로그램입니다. 관리자는 간편 실행을 위한 Office 배포 도구를 사용하여 설치를 사용자 지정할 수 있습니다. Office 2013 간편 실행은 주로 Microsoft 365 환경에서 사용 되므로이 설치 방법에 대해서는이 섹션에서 자세히 설명 하지 않습니다. 간편 실행 설치를 사용 하 고 사용자 지정 하는 방법에 대 한 자세한 내용은 Office 2013 Resource Kit 설명서를 참조 하십시오. 또한 관리자는 Office 2013 간편 실행 프로그램 및 언어 원본 파일을 온-프레미스 위치에 다운로드할 수 있으며,이는 네트워크에 대 한 요구를 최소화 하거나 사용자가 회사 보안 요구 사항으로 인해 인터넷에서 소프트웨어를 설치 하지 못하도록 하려는 경우에 유용 합니다.

이 섹션의 항목에서는 Office 2013 MSI 기반 설치 관리자를 사용 하 여 클라이언트를 배포 하는 방법에 대해 중점적으로 설명 합니다. 기본 참조는 인프라를 준비 하 고, 설치를 사용자 지정 하 고, Office 2013를 배포 하는 방법에 대해 자세히 설명 하는 Office 2013 Resource Kit 설명서 여야 합니다. 그러나 Office 설명서를이 섹션의 항목과 함께 사용 하 여 Lync 2013와 관련 된 배포 고려 사항을 확인 해야 합니다.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Outlook 메시징 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 Lync 2013 용 온라인 모임 추가 기능이 Lync 2013을 사용 하 여 자동으로 설치 됩니다.</P>
> <LI>
> <P>Office 2013 설치 프로그램은 이전 버전의 Lync 또는 Office Communicator를 제거 하지 않습니다. Lync 2013 클라이언트는 다른 Lync 또는 Office Communicator 클라이언트와 함께 나란히 설치 됩니다.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 클라이언트 설치 사용자 지정](lync-server-2013-customizing-client-installation.md)

  - [Lync Server 2013의 Lync 동작 및 사용자 인터페이스 사용자 지정](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Lync Server 2013에서 온라인 모임 추가 기능 사용자 지정](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Lync Server 2013에서 모임 참가 페이지 구성](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Lync Server 2013에서 지원 되는 클라이언트 버전 구성](lync-server-2013-configuring-supported-client-versions.md)

  - [Lync Server 2013에서 향상 된 현재 상태 개인 정보 보호 모드 구성](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

