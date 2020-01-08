---
title: 'Lync Server 2013: 서버 및 응용 프로그램 강화 및 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Lync Server 2013에 대한 서버 및 응용 프로그램 강화 및 보호

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-12-05_

특정 구성 요소에 대 한 모범 사례에 따라 운영 체제 및 응용 프로그램을 강화 하 고 보호 해야 합니다. 이 섹션에서는 응용 프로그램 서버를 강화 하는 방법과 그룹 정책을 사용 하 여 보안 lockdowns를 구현 하는 방법을 설명 합니다.

<div>


> [!NOTE]  
> Microsoft Lync Server 2013 배포에 사용 되는 데이터베이스를 강화 하 고 보호할 수도 있습니다. 자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013의 데이터베이스 강화 및 보호</A>를 참조 하세요.



</div>

<div>

## <a name="securing-application-servers"></a>응용 프로그램 서버 보안

응용 프로그램 서버의 경우 운영 체제와 응용 프로그램을 강화 해야 합니다. 예를 들어 Microsoft Internet Security 및 가속 (ISA) 서버 2006을 실행 하는 것을 전담 하는 Windows Server 2008 컴퓨터는 운영 체제와 응용 프로그램 관점에서 강화 되어야 합니다. 서버에서 실행 중이거나 제공 하는 서비스 수를 최소화 하는 것은 주요 목표입니다.

</div>

<div>

## <a name="securing-virtual-servers"></a>가상 서버 보안

가상 서버 스냅숏에는 서버 데이터 디스크의 복사본이 포함 되며 메모리 내 데이터의 덤프가 포함 되며,이 둘 모두 공격이 발생할 수 있는 민감한 암호화 데이터를 포함할 수 있습니다. 가상화를 사용 하 여 구현 된 프로덕션 서버의 경우 거의 제어 되는 방식으로 모든 서버 스냅숏을 사용 하지 않도록 설정 하거나 관리 해야 합니다. Hyper-v 가상 서버를 보호 하는 방법에 대 한 자세한 내용은 다음 [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)Hyper-v 보안 가이드를 참조 하세요.

</div>

<div>

## <a name="group-policy"></a>그룹 정책

Windows Server 2008 및 Windows Server 2008 R2에서 그룹 정책은 디렉터리 기반 데스크톱 구성 관리를 제공 합니다. 그룹 정책을 사용 하 여 다음에 대 한 GPO (그룹 정책 개체) 내에 컴퓨터 및 사용자 설정을 정의 하 여 보안 lockdowns를 구현할 수 있습니다.

  - 레지스트리 기반 정책

  - 보안

  - 소프트웨어 설치

  - 문자

  - 폴더 리디렉션

  - 원격 설치 서비스

관리자가 이러한 설정을 구성할 수 있는 사용자 인터페이스를 제공 하기 위해 관리 템플릿은 운영 체제 릴리스, 서비스 팩 릴리스 및 Lync Server 2013을 비롯 한 일부 응용 프로그램과 함께 제공 됩니다.

Communicator .adm 파일은 Lync Server 2013와 함께 제공 되는 관리 템플릿으로,% windir%\\inf\\ 디렉터리에 설치 되어 있으며, 그룹 정책 설정에 대 한 인터페이스를 제공 합니다. Communicator의 각 설정은 응용 프로그램 동작에 영향을 주는 레지스트리의 설정에 해당 합니다.

Active Directory 사용자 및 컴퓨터 콘솔과 GPMC (그룹 정책 관리 콘솔)에서 사용할 수 있는 GPedit에서 설정을 액세스할 수 있습니다.

</div>

<div>

## <a name="group-policy-security-settings"></a>그룹 정책 보안 설정

그룹 정책에는 GPedit에서 액세스할 때 컴퓨터 구성/Windows 설정/보안 설정 아래에 있는 GPO에 대 한 보안 설정이 포함 되어 있습니다. 보안 템플릿을 가져와 GPO에 대 한 보안 설정을 구성할 수 있습니다. 의 Windows Server 2008 보안 가이드 [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) 및 windows Server 2008 R2 보안 준수 관리 도구 키트에는 [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) 요구 사항에 맞게 수정할 수 있는 다양 한 샘플 템플릿이 포함 되어 있습니다.

</div>

<div>

## <a name="best-practices"></a>모범 사례

  - 모든 서버 운영 체제 및 응용 프로그램을 강화 합니다.

  - 서버 스냅숏을 보호 하 고 모든 가상 서버의 보안을 강화 합니다.

  - 그룹 정책을 사용 하 여 보안 lockdowns를 구현 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

