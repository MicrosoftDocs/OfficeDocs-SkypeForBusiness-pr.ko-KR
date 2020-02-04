---
title: 'Lync Server 2013: Lync Server의 보안 프레임 워크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013의 보안 프레임 워크

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-08_

이 섹션에서는 Microsoft Lync Server 2013의 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다. 이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 Lync Server 2013 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.

이러한 요소는 다음과 같습니다.

  - AD DS (Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공 합니다.

  - RBAC (역할 기반 액세스 제어)를 사용 하 여 보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.

  - PKI (공개 키 인프라)는 신뢰할 수 있는 Ca (인증 기관)에서 발급 한 인증서를 사용 하 여 서버를 인증 하 고 데이터 무결성을 보장 합니다.

  - TLS (전송 계층 보안), https over SSL (HTTPS) 및 상호 TLS (MTLS)로 끝점 인증 및 IM 암호화를 사용 하도록 설정 합니다. 지점간 오디오, 비디오 및 응용 프로그램 공유 스트림은 보안 실시간 전송 프로토콜 (SRTP)을 사용 하 여 암호화 됩니다.

  - 가능 하면 사용자 인증을 위한 업계 표준 프로토콜입니다.

  - Windows PowerShell은 사용자가 스크립트를 쉽게 실행할 수 없도록 기본적으로 활성화 된 보안 기능을 제공 합니다.

이러한 기본 보안 요소는 Lync Server 2013의 보안 기반을 보장 하는 데 도움이 되는 신뢰할 수 있는 사용자, 서버, 연결, 작업을 정의 하기 위해 함께 작동 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션의 항목에서는 이러한 기본 요소의 작동 방식으로 Lync Server 인프라의 보안을 강화 하는 방법을 설명 합니다.

  - [Lync Server 2013의 Active Directory 도메인 서비스](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013에 대 한 RBAC (역할 기반 액세스 제어)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013의 공개 키 인프라](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 용 TLS 및 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 암호화](lync-server-2013-encryption.md)

  - [Lync Server 2013에 대 한 사용자 및 클라이언트 인증](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 및 Lync Server 2013 관리 도구](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

