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
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="72996-102">Lync Server 2013에서 Kerberos 인증 설정</span><span class="sxs-lookup"><span data-stu-id="72996-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72996-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="72996-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="72996-104">Lync Server 2013에서는 웹 서비스에 대 한 NTLM 및 Kerberos 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="72996-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="72996-105">Office Communications Server 2007 및 Office Communications Server 2007 R2는 사용자 계정으로 기본 RTCComponentService 및 RTCService를 사용 하 여 웹 서비스 응용 프로그램 풀을 실행 하 고, SPN (서비스 사용자 이름)을 할당할 수 있도록 합니다. 계정 및 인증 사용자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="72996-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="72996-106">Lync Server는 NetworkService를 사용 하 여 웹 서비스를 실행 하 고 NetworkService에서 Spn을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72996-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="72996-107">Spn을 보유 하는 Active Directory 개체가 없는 경우의 문제를 해결 하려면 Lync Server 제어판에서이 용도로 컴퓨터 계정 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72996-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="72996-108">컴퓨터 계정 개체는 SPN을 보유할 수 있으며, 이전 버전에서 사용자 계정 사용 시 문제가 되었던 암호 만료가 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72996-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="72996-109">Windows PowerShell cmdlet을 사용 하 여 Kerberos 인증을 제공 하도록 컴퓨터 개체를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="72996-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72996-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="72996-110">In This Section</span></span>

  - [<span data-ttu-id="72996-111">Lync Server 2013에서 Kerberos 인증을 사용 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="72996-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="72996-112">Lync Server 2013에서 Kerberos 인증 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="72996-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="72996-113">Lync Server 2013에서 사이트에 Kerberos 인증 계정 할당</span><span class="sxs-lookup"><span data-stu-id="72996-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="72996-114">Lync Server 2013에서 Kerberos 인증 계정 암호 설정</span><span class="sxs-lookup"><span data-stu-id="72996-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="72996-115">Lync Server 2013에서 다른 사이트에 Kerberos 인증 추가</span><span class="sxs-lookup"><span data-stu-id="72996-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="72996-116">Lync Server 2013에서 사이트에서 Kerberos 인증 제거</span><span class="sxs-lookup"><span data-stu-id="72996-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="72996-117">Lync Server 2013에서 Kerberos 인증 상태 및 할당 테스트 및 보고</span><span class="sxs-lookup"><span data-stu-id="72996-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

