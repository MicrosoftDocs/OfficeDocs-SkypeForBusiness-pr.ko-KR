---
title: 영구 채팅 서버 모범 사례
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="60019-102">영구 채팅 서버 모범 사례</span><span class="sxs-lookup"><span data-stu-id="60019-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60019-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="60019-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="60019-104">범주와 영구 채팅방을 만들고 범위 및 구성원을 디자인할 때 다음 팁을 사용 하 여 계획을 세울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="60019-105">회사에 윤리적인 벽이 필요 하지 않은 경우 범주 트리에서 범위를 좁혀 주지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="60019-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="60019-106">모든 사용자를 한 범주에 포함 하 고 해당 범주의 모든 채팅방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60019-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="60019-107">그 이후에는 구성원 목록만 사용 하 여 각 채팅방에 대 한 액세스 권한을 부여 하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="60019-108">대부분의 경우에는 사용자가 새로운 채팅방을 만들어 언제 든 지 새 항목에 대 한 토론을 시작할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60019-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="60019-109">이 작업은 **작성자** 목록을 **allowedmembers** 목록과 동일 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60019-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="60019-110">그러나 중앙 지원 팀 또는 지정 된 사용자만 회의실을 만들 수 있도록 허용 하려면 **작성자** 목록을 적절 한 하위 집합으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60019-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="60019-111">각 채팅방에 조직에 맞는 위치를 설명 하는 전체 이름 및 설명 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60019-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="60019-112">채팅방을 사용할 때 사용자가 범주 이름을 볼 수 없기 때문에 사용자는 범주 이름을 사용 하 여 채팅방에 대 한 원하는 토론 포럼을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="60019-113">특정 명명 규칙이 나 다른 액세스 제어 또는 유효성 검사를 구현할 경우 사용자 지정 회의실 만들기 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="60019-114">영구 채팅 구성을 사용 하 여 **RoomManagementUrl** 를 호스트 하는 항목으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="60019-115">예를 들어 사용자가 Lync 클라이언트에서 **채팅방 만들기** 를 클릭 하면 사용자 지정 솔루션으로 리디렉션될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="60019-116">다른 비즈니스 데이터를 채팅방으로 가져와 채팅방의 환경을 개선 하는 데 도움이 되는 다양 한 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="60019-117">관리자는 시스템에서 허용 하려는 추가 기능을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60019-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="60019-118">채팅방 관리자와 제작자는 해당 채팅방에 가장 적합 한 추가 기능 목록에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60019-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="60019-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60019-119">See Also</span></span>


[<span data-ttu-id="60019-120">Lync Server 2013에서 범주, 채팅방 및 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="60019-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

