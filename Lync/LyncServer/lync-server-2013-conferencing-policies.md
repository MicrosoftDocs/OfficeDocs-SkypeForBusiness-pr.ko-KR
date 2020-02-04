---
title: 'Lync Server 2013: 회의 정책'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d1d9ed6fc0ad75e316a41ef7939f36ecaba354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="467bc-102">Lync Server 2013의 회의 정책</span><span class="sxs-lookup"><span data-stu-id="467bc-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="467bc-103">_**마지막으로 수정한 주제:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="467bc-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="467bc-104">회의 정책은 회의 중에 사용자가 사용할 수 있는 기능 (모임이 라고도 함)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="467bc-105">회의 정책 설정에는 모임에서 IP 오디오 및 비디오를 참석할 수 있는 최대 사용자 수까지 포함할 수 있는지 여부에 이르기까지 다양 한 일정 및 참가 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="467bc-106">관리자는 회의 정책을 사용 하 여 보안, 대역폭, 모임에 대 한 법적 측면을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="467bc-107">회의 정책은 전역 범위, 사이트 범위, 사용자 범위 등 세 가지 수준에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="467bc-108">설정은 해당 사용자에 게 가장 좁은 범위의 범위에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="467bc-109">사용자에 게 사용자 정책을 할당 하면 해당 설정이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="467bc-110">사용자 정책을 할당 하지 않으면 사이트 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="467bc-111">적용 되는 사용자 또는 사이트 정책이 없는 경우 전역 정책은 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="467bc-112">전역 정책은 기본적으로 존재 하므로 새 전역 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="467bc-113">또한 기존 전역 정책을 삭제할 수 없지만 기존 전역 정책을 변경 하 여 기본 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="467bc-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="467bc-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="467bc-114">In This Section</span></span>

  - [<span data-ttu-id="467bc-115">Lync Server 2013에서 회의 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="467bc-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="467bc-116">Lync Server 2013에서 회의 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="467bc-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="467bc-117">Lync Server 2013에서 기존 회의 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="467bc-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="467bc-118">Lync Server 2013에 대 한 회의 정책 설정 참조</span><span class="sxs-lookup"><span data-stu-id="467bc-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

