---
title: 'Lync Server 2013: 사용자별 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6430bf1935cd3ca457c0f3bb63876eae8d115976
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="f729c-102">Lync Server 2013에서 사용자별 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f729c-103">_**마지막으로 수정 된 항목:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="f729c-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="f729c-p101">사용자나 사용자 그룹에 특정 정책을 지정하여 전역 정책 등 다른 사용자에게 지정된 정책에서 정의된 설정에서 파생된 특정 설정을 할당할 수 있으며, 이러한 정책은 사용자별 정책이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f729c-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f729c-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f729c-106">In This Section</span></span>

  - [<span data-ttu-id="f729c-107">Lync Server 2013에서 사용자별 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="f729c-108">Lync Server 2013에서 사용자별 클라이언트 버전 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="f729c-109">Lync Server 2013에서 사용자별 PIN 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="f729c-110">Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="f729c-111">Lync Server 2013에서 사용자별 보관 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="f729c-112">Lync Server 2013에서 사용자별 위치 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="f729c-113">Lync Server 2013에서 사용자별 모바일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="f729c-114">Lync Server 2013에서 사용자별 영구 채팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="f729c-115">Lync Server 2013에서 사용자별 다이얼 플랜 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="f729c-116">Lync Server 2013에서 사용자별 음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f729c-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f729c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f729c-117">See Also</span></span>


[<span data-ttu-id="f729c-118">Lync Server 2013에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="f729c-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

