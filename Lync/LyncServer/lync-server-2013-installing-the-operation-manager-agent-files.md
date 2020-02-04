---
title: 'Lync Server 2013: Operation Manager 에이전트 파일 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Lync Server 2013에서 Operation Manager 에이전트 파일을 설치 하는 중

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

컴퓨터에 Operations Manager 에이전트 파일을 설치 하려면 다음 단계를 완료 합니다.

1.  System Center 설정 미디어에서 **SetupOM**를 두 번 클릭 합니다.

2.  System Center Operation Manager 설치에서 **Operations Manager 에이전트 설치**를 클릭 합니다.

3.  System Center 설정 마법사의 **System Center Operations Manager 설치 마법사 시작** 페이지에서 **다음**을 클릭 합니다.

4.  **대상 폴더** 페이지에서 Operations Manager 에이전트 파일이 설치 될 폴더를 선택 하 고 **다음**을 클릭 합니다.

5.  **관리 그룹 구성** 페이지에서 **관리 그룹 정보 지정**을 선택 하 고 **다음**을 클릭 합니다.

6.  **관리 그룹 구성** 페이지의 **관리 그룹 이름** 상자에 operations manager 관리 그룹의 이름을 입력 하 고 **관리 서버** 상자에 operations manager 서버의 호스트 이름 (예: atl-scom-001)을 입력 합니다. Operations Manager에 사용 되는 포트 번호를 변경한 경우 관리 서버 포트 상자에 새 포트 번호를 입력 합니다. 그렇지 않으면 포트의 기본값 5723을 그대로 두고 **다음**을 클릭 합니다.

7.  **에이전트 작업 계정** 페이지에서 **로컬 시스템**을 선택 하 고 **다음**을 클릭 합니다.

8.  **Microsoft 업데이트** 페이지에서 **microsoft 업데이트 사용 안 함을**선택 하 고 **다음**을 클릭 합니다.

9.  **설치 준비** 페이지에서 **설치**를 클릭 합니다.

10. **System Center Operations Manager 설치 마법사 완료** 페이지에서 **마침을**클릭 합니다.

11. **끝내기**를 클릭 합니다.

System Center 2007 R2를 사용 하는 경우 **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **System Center operations manager 2007 R2**를 클릭 하 고 **Operations Manager Shell**을 클릭 하 여 에이전트가 만들어졌는지 확인할 수 있습니다. Operations Manager 셸에서 다음 Windows PowerShell 명령을 입력 한 다음 enter 키를 누릅니다.

    Get-Agent 

모든 Operations Manager 에이전트 목록이 화면에 표시 됩니다.

System Center 2012를 사용 하는 경우 작업 2012 Manager 셸에서이 명령을 실행 합니다.

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

