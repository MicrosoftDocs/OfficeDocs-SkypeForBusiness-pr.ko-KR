---
title: 'Lync Server 2013: Lync Server 용 보안 프레임 워크'
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
ms.openlocfilehash: 9910b4c481ea474425cae51d7fac88a217d52e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013의 보안 프레임 워크

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-08_

이 섹션에서는 Microsoft Lync Server 2013의 보안 프레임 워크를 구성 하는 기본 요소에 대 한 개요를 제공 합니다. 이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 Lync Server 2013 배포의 보안에 대 한 의사 결정을 내리는 데 필수적입니다.

이러한 요소는 다음과 같습니다.

  - AD DS (Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공 합니다.

  - RBAC (역할 기반 액세스 제어)를 사용 하면 보안에 대 한 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.

  - PKI (공개 키 인프라)에서는 신뢰할 수 있는 Ca (인증 기관)에서 발급 한 인증서를 사용 하 여 서버를 인증 하 고 데이터 무결성을 보장 합니다.

  - TLS (전송 계층 보안), HTTPS를 통한 HTTPS (SSL) 및 MTLS (상호 TLS)를 사용 하도록 설정 합니다. 지점간 오디오, 비디오 및 응용 프로그램 공유 스트림은 Secure SRTP (실시간 전송 프로토콜)를 사용 하 여 암호화 됩니다.

  - 가능한 경우 사용자 인증용으로 업계 표준 프로토콜을 사용 합니다.

  - Windows PowerShell은 사용자가 스크립트를 쉽게 실행 하거나 모르는 사이에 기본적으로 사용 하도록 설정 되는 보안 기능을 제공 합니다.

이러한 기본 보안 요소가 함께 작동 하 여 Lync Server 2013의 보안 기반을 보장 하는 데 도움이 되는 신뢰할 수 있는 사용자, 서버, 연결 및 작업을 정의 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

이 섹션의 항목에서는 이러한 기본 요소가 각각 Lync Server 인프라의 보안을 향상 시키는 방식에 대해 설명 합니다.

  - [Lync Server 2013에 대 한 Active Directory 도메인 서비스](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013의 RBAC (역할 기반 액세스 제어)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 용 공개 키 인프라](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 용 TLS 및 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013에 대 한 암호화](lync-server-2013-encryption.md)

  - [Lync Server 2013에 대 한 사용자 및 클라이언트 인증](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 및 Lync Server 2013 관리 도구](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

