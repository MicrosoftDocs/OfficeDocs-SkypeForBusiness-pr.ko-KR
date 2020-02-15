---
title: 'Lync Server 2013: 전화 접속 회의 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef825aa799cdcdec66903e002791f30d9b4cac00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="051bf-102">Lync Server 2013에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="051bf-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="051bf-103">_**마지막으로 수정 된 항목:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="051bf-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="051bf-104">이 섹션에서는 Lync Server 2013 전화 접속 회의를 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="051bf-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="051bf-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="051bf-105">In This Section</span></span>

  - [<span data-ttu-id="051bf-106">Lync Server 2013의 전화 접속 회의 구성 필수 구성 요소 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="051bf-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="051bf-107">Lync Server 2013의 전화 접속 회의에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="051bf-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="051bf-108">Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="051bf-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="051bf-109">다이얼 플랜 Lync Server 2013에 지역이 할당 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="051bf-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="051bf-110">반드시 Lync Server 2013에서 PIN 정책 설정 확인</span><span class="sxs-lookup"><span data-stu-id="051bf-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="051bf-111">Lync Server 2013에서 전화 접속에 대 한 회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="051bf-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="051bf-112">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</span><span class="sxs-lookup"><span data-stu-id="051bf-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="051bf-113">반드시 Lync Server 2013에서 전화 접속 회의 설정 확인</span><span class="sxs-lookup"><span data-stu-id="051bf-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="051bf-114">반드시 Lync Server 2013의 DTMF 명령에 대 한 키 매핑 수정</span><span class="sxs-lookup"><span data-stu-id="051bf-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="051bf-115">반드시 Lync Server 2013에서 전화 회의 참가 및 탈퇴 알림 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="051bf-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="051bf-116">반드시 Lync Server 2013에서 전화 접속 회의 확인</span><span class="sxs-lookup"><span data-stu-id="051bf-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="051bf-117">Lync 2013 용 온라인 모임 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="051bf-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="051bf-118">Lync Server 2013에서 사용자 계정 설정 구성</span><span class="sxs-lookup"><span data-stu-id="051bf-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="051bf-119">는 전화 회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="051bf-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="051bf-120">반드시 Lync Server 2013에서 사용자에 게 전화 접속 회의 시작</span><span class="sxs-lookup"><span data-stu-id="051bf-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="051bf-121">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="051bf-121">Related Sections</span></span>

[<span data-ttu-id="051bf-122">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="051bf-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

