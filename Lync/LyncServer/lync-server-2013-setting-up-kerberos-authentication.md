---
title: 'Lync Server 2013: Kerberos 인증 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8ae852be13ee1ca7780ed89bf710e64fe5a2902
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 인증 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Lync Server 2013에서는 웹 서비스에 대 한 NTLM 및 Kerberos 인증을 지원 합니다. Office Communications Server 2007 및 Office Communications Server 2007 R2는 사용자 계정으로 기본 RTCComponentService 및 RTCService를 사용 하 여 웹 서비스 응용 프로그램 풀을 실행 하 고, SPN (서비스 사용자 이름)을 할당할 수 있도록 합니다. 계정 및 인증 사용자 역할을 합니다. Lync Server는 NetworkService를 사용 하 여 웹 서비스를 실행 하 고 NetworkService에서 Spn을 할당할 수 없습니다.

Spn을 보유 하는 Active Directory 개체가 없는 경우의 문제를 해결 하려면 Lync Server 제어판에서이 용도로 컴퓨터 계정 개체를 사용할 수 있습니다. 컴퓨터 계정 개체는 SPN을 보유할 수 있으며, 이전 버전에서 사용자 계정 사용 시 문제가 되었던 암호 만료가 적용하지 않습니다.

Windows PowerShell cmdlet을 사용 하 여 Kerberos 인증을 제공 하도록 컴퓨터 개체를 구성 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Kerberos 인증을 사용 하기 위한 필수 구성 요소](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Lync Server 2013에서 Kerberos 인증 계정 만들기](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Lync Server 2013에서 사이트에 Kerberos 인증 계정 할당](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Lync Server 2013에서 Kerberos 인증 계정 암호 설정](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Lync Server 2013에서 다른 사이트에 Kerberos 인증 추가](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Lync Server 2013에서 사이트에서 Kerberos 인증 제거](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Lync Server 2013에서 Kerberos 인증 상태 및 할당 테스트 및 보고](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

