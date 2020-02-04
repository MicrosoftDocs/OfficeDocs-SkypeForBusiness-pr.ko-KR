---
title: 'Lync Server 2013: Windows PowerShell 및 Lync Server 관리 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell 및 Lync Server 2013 관리 도구

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-07-20_

Microsoft Lync Server 2013에서 관리 도구는 Windows PowerShell을 사용 하 여 구현 됩니다. Windows PowerShell에는 명령줄 환경, 제품별 명령, 전체 스크립트 언어가 포함 됩니다. Windows PowerShell을 사용 하 여 구현 되는 Lync Server 2013 도구에는 다음이 포함 됩니다.

  - **토폴로지 작성기**. 토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 하 고, 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다. 개별 서버에 Lync Server 2013을 설치 하는 경우 서버는 설치 프로세스의 일부로 게시 된 토폴로지를 읽고, 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다. 설치 후에는 모든 서버에 구성 정보가 자동으로 복제 됩니다. 토폴로지 작성기를 사용 하는 경우에만 구성 요소를 배포에 추가할 수 있습니다.

  - **Lync Server 관리 셸**. 배포의 전체 명령줄 관리를 위해 Lync Server Management Shell을 사용할 수 있습니다.

  - **Lync 서버 컨트롤 패널** Microsoft Lync Server 2013 제어판 사용자 인터페이스를 사용 하 여 배포에서 가장 일반적인 작업을 관리할 수 있습니다.

이러한 도구는 550 제품별 cmdlet을 포함 하 여 배포 관리를 위해 Windows PowerShell cmdlet을 사용 합니다. Lync Server 2013에 포함 된 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한입니다. 인증서 및 PIN (개인 식별 번호) 인증에 대 한 cmdlet을 비롯 한 다양 한 cmdlet을 인증 관리에 사용할 수 있습니다. 또한 많은 cmdlet을 사용 하 여 Lync Server 2013의 관리 제어를 위임할 수 있는 새 RBAC (역할 기반 액세스 제어) 기능을 사용할 수 있습니다. Lync Server cmdlet에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.

Windows PowerShell 용 스크립트 보안 기능은 Microsoft VBScript (Visual Basic Scripting Edition)를 포함 하 여 이전 기술의 일부 스크립팅 관련 보안 문제를 방지 하기 위해 특별히 설계 되었습니다. Windows PowerShell 보안 기능은 사용자가 스크립트를 쉽게 실행할 수 없는 환경을 만들기 위한 것입니다. 기본적으로 Windows PowerShell 보안 기능을 사용할 수 있습니다. 이러한 기능의 상태를 스크립트 요구와 다양 한 보안 목표에 맞게 수정할 수 있습니다. 이는 셸이 사용자가 스크립트를 실행할 수 없다는 것을 말합니다. 대신 셸은 기본적으로 사용자가 수행 하는 작업을 인식 하지 않고 스크립트를 실행할 수 있도록 어렵게 만듭니다. 자세한 내용은 Windows PowerShell 스크립트 보안을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

</div>

<span> </span>

</div>

</div>

</div>

