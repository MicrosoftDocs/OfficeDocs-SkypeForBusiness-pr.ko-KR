---
title: 'Lync Server 2013: 전화 접속 회의 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca8b82fe77e578f1ac513d00583c42dd56162a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="682bc-102">Lync Server 2013에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="682bc-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="682bc-103">_**마지막으로 수정한 주제:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="682bc-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="682bc-104">이 섹션에서는 Lync Server 2013 전화 접속 회의를 구성 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="682bc-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="682bc-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="682bc-105">In This Section</span></span>

  - [<span data-ttu-id="682bc-106">Lync Server 2013의 전화 접속 회의 구성 필수 구성 요소 및 권한</span><span class="sxs-lookup"><span data-stu-id="682bc-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="682bc-107">Lync Server 2013 의 전화 접속 회의 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="682bc-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="682bc-108">Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="682bc-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="682bc-109">다이얼 플랜 설정 Lync 서버 2013에 지역이 지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="682bc-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="682bc-110">(선택 사항) Lync Server 2013에서 PIN 정책 설정 확인</span><span class="sxs-lookup"><span data-stu-id="682bc-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="682bc-111">Lync Server 2013에서 전화 접속에 대한 회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="682bc-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="682bc-112">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</span><span class="sxs-lookup"><span data-stu-id="682bc-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="682bc-113">(선택 사항) Lync Server 2013에서 전화 접속 회의 설정 확인</span><span class="sxs-lookup"><span data-stu-id="682bc-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="682bc-114">(선택 사항) Lync Server 2013에서 DTMF 명령에 대한 키 매핑 수정</span><span class="sxs-lookup"><span data-stu-id="682bc-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="682bc-115">(선택 사항) Lync Server 2013에서 회의 참가/나가기 알림 활성화/비활성화</span><span class="sxs-lookup"><span data-stu-id="682bc-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="682bc-116">(선택 사항) Lync Server 2013에서 전화 접속 회의 확인</span><span class="sxs-lookup"><span data-stu-id="682bc-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="682bc-117">Lync 2013용 온라인 모임 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="682bc-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="682bc-118">Lync Server 2013에서 사용자 계정 설정 구성</span><span class="sxs-lookup"><span data-stu-id="682bc-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="682bc-119">(권장) 전화 회의 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="682bc-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="682bc-120">(선택 사항) Lync Server 2013에서 사용자에게 전화 접속 회의 시작 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="682bc-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="682bc-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="682bc-121">Related Sections</span></span>

[<span data-ttu-id="682bc-122">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="682bc-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

