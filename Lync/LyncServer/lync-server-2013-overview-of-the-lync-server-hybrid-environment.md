---
title: 'Lync Server 2013: Lync Server 하이브리드 환경 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 443dcfc17849e34aa711f657726fed9c86fa566d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 하이브리드 환경 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-28_

Lync Server 2013 hybrid environment는 일부 사용자가 온-프레미스 Lync Server 2013에 위치 하 고 다른 사용자는 Lync Online에 홈으로 설정 되었지만, 사용자는 user@contoso.com와 같은 동일한 도메인을 공유 하는 배포를 참조 합니다.

<div>

## <a name="about-this-guide"></a>이 가이드 정보

이 가이드에서는 lync Online과의 상호 운용성을 위해 Lync Server 2013 환경을 구성한 다음 온-프레미스 배포에서 사용자를 이동 하 여 Lync Online을 사용 하는 데 필요한 작업에 대해 설명 합니다.

</div>

<div>

## <a name="prerequisites"></a>필수 구성 요소

하이브리드 배포를 구성 하기 위한 작업을 완료 하려면 다음 응용 프로그램 및 유틸리티를 설치 해야 합니다. 이러한 파일의 설치 관리자는 다음 목록에 포함 된 링크 뿐 아니라 배포를 위해 제공 되는 설정 미디어에도 포함 되어 있습니다.

  - [ADFS(Active Directory Federation Services) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft 디렉터리 동기화 도구 9.1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [AD FS를 사용 하 여 single sign-on 용 Windows PowerShell 설치](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services 로그인 도우미 (msoidcli-)는 office 365 관리 포털에서 연결 된 다운로드 페이지에서 얻을 수 있는 Office 365 데스크톱 설치 프로그램에 포함 되어 있습니다.

</div>

<div>

## <a name="administrator-credentials"></a>관리자 자격 증명

관리자 자격 증명을 입력 하 라는 메시지가 표시 되 면 Office 365 테 넌 트에 대 한 관리자 계정의 사용자 이름 및 암호를 사용 합니다. AD FS (Active Directory Federation Services) 2.0, 디렉터리 동기화, Single sign-on, 페더레이션 및 이동 사용자를 Lync Online으로 구성 하는 경우에도 이러한 자격 증명을 사용 합니다.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Lync Online PowerShell에 연결

이제 관리자는 Windows PowerShell을 사용 하 여 Lync Online 및 해당 Lync Online 사용자 계정을 관리할 수 있습니다. 이 작업을 수행 하려면 먼저 Microsoft 다운로드 센터 (https://go.microsoft.com/fwlink/?LinkId=294688)를 통해 Lync Online Connector 모듈을 다운로드 하 여 설치 해야 합니다. Lync online 커넥터 모듈을 다운로드, 설치 및 사용 하는 방법 및 Windows PowerShell을 사용 하 여 Lync Online을 관리 하는 방법에 대 한 자세한 내용은 [Windows powershell을 사용 하 여 Lync online 관리](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

