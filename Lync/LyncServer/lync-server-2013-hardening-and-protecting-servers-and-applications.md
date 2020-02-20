---
title: 'Lync Server 2013: 서버 및 응용 프로그램 강화 및 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50bd8d3fb538a7450d2129691ec523dbcb6dd208
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Lync Server 2013에 대 한 서버 및 응용 프로그램 강화 및 보호

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-12-05_

특정 구성 요소에 대 한 모범 사례에 따라 운영 체제 및 응용 프로그램을 강화 하 고 보호 해야 합니다. 이 섹션에서는 응용 프로그램 서버를 강화 하 고 그룹 정책을 사용 하 여 보안 잠금을을 구현 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> Microsoft Lync Server 2013 배포에 사용 되는 데이터베이스를 강화 하 고 보호할 수도 있습니다. 자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013의 데이터베이스 보안 강화 및 보호</A>를 참조 하십시오.



</div>

<div>

## <a name="securing-application-servers"></a>응용 프로그램 서버 보안

응용 프로그램 서버의 경우 운영 체제와 응용 프로그램을 강화 해야 합니다. 예를 들어 Microsoft Internet Security and 가속화 (ISA) 서버 2006을 실행 하기 위한 Windows Server 2008 컴퓨터는 운영 체제와 응용 프로그램 측면에서 강화 해야 합니다. 서버에서 실행 되 고 제공 하는 서비스 수를 최소화 하는 것은 주요 목표입니다.

</div>

<div>

## <a name="securing-virtual-servers"></a>가상 서버 보안

가상 서버 스냅숏에는 서버의 데이터 디스크 복사본이 포함 되며 메모리 내 데이터의 덤프도 포함 되며, 둘 다 공격이 발생할 수 있는 중요 한 암호화 데이터를 포함할 수 있습니다. 가상화를 사용 하 여 구현 되는 프로덕션 서버의 경우 모든 서버 스냅숏을 사용 하지 않도록 설정 하거나 매우 통제 된 방식으로 관리 해야 합니다. Hyper-v 가상 서버를 보호 하는 방법에 대 한 자세한 내용은: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)의 Hyper-v 보안 가이드를 참조 하세요.

</div>

<div>

## <a name="group-policy"></a>그룹 정책

Windows Server 2008 및 Windows Server 2008 R2에서 그룹 정책은 디렉터리 기반 데스크톱 구성 관리를 제공 합니다. 그룹 정책을 사용 하 여 다음에 대 한 GPO (그룹 정책 개체) 내에서 컴퓨터 및 사용자 설정을 정의 하 여 보안 잠금을를 구현할 수 있습니다.

  - 레지스트리 기반 정책

  - 보안

  - 소프트웨어 설치

  - 스크립트

  - 폴더 리디렉션

  - 원격 설치 서비스

관리자가 이러한 설정을 구성 하는 데 사용할 수 있는 사용자 인터페이스를 제공 하기 위해 관리 템플릿은 운영 체제 릴리스, 서비스 팩 릴리스 및 일부 응용 프로그램 (Lync Server 2013 포함)과 함께 제공 됩니다.

Communicator .adm 파일은 Lync Server 2013와 함께 제공 되는 관리 템플릿으로,% windir%\\inf\\ 디렉터리에 설치 되어 있으며, 그룹 정책 설정에 대 한 인터페이스를 제공 합니다. Communicator의 각 설정은 응용 프로그램 동작에 영향을 주는 레지스트리 설정에 해당 합니다.

이 설정은 Active Directory 사용자 및 컴퓨터 콘솔과 GPMC (그룹 정책 관리 콘솔)에서 제공 되는 Gpedit.msc에서 액세스할 수 있습니다.

</div>

<div>

## <a name="group-policy-security-settings"></a>그룹 정책 보안 설정

그룹 정책 Gpedit.msc에서 액세스할 때 컴퓨터 구성/Windows 설정/보안 설정 아래에 GPO에 대 한 보안 설정이 들어 있습니다. 보안 템플릿을 가져와서 GPO에 대 한 보안 설정을 구성할 수 있습니다. 의 Windows Server 2008 보안 가이드 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 및 windows Server 2008 R2 보안 준수 관리 도구 키트에는 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) 사용자의 요구를 충족 하기 위해 수정할 수 있는 다양 한 샘플 서식 파일이 포함 되어 있습니다.

</div>

<div>

## <a name="best-practices"></a>모범 사례

  - 모든 서버 운영 체제 및 응용 프로그램을 강화 합니다.

  - 서버 스냅숏을 보호 하 고 모든 가상 서버의 보안을 향상 시킵니다.

  - 그룹 정책을 사용 하 여 보안 잠금을을 구현 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

