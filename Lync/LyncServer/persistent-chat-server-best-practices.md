---
title: 영구 채팅 서버 모범 사례
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe9742b76ec6abfd7b7407f38edda937bdf6ecc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="7b854-102">영구 채팅 서버 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7b854-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b854-103">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7b854-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7b854-104">범주와 영구 대화방을 만들고 범위와 구성원을 디자인할 때 다음 팁을 계획에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="7b854-105">회사에서 교신 차단 영역 벽이 필요 하지 않은 경우 범주 트리에서 범위를 좁히는 것은 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="7b854-106">모든 사용자를 한 범주의 범위에 넣고 해당 범주의 모든 채팅방을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="7b854-107">그런 다음 구성원 목록만 사용 하 여 각 대화방에 대 한 액세스 권한을 부여 하거나 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="7b854-108">대부분의 경우 사용자가 새 채팅방을 만들어 언제 든 지 새 항목에 대 한 토론을 시작할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="7b854-109">이 작업은 **제작자** 목록을 **allowedmembers** 목록과 동일 하 게 설정 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="7b854-110">그러나 중앙 지원 팀 이나 지정 된 사용자만 대화방을 만들 수 있도록 하려면 **작성자** 목록을 적절 한 하위 집합으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="7b854-111">각 대화방에 조직에 맞는 위치를 설명 하는 전체 이름 및 설명 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="7b854-112">사용자가 대화방을 사용할 때 종류 이름이 표시 되지 않으므로 사용자가 해당 채팅방에 대해 원하는 토론 포럼을 결정 하는 데 도움이 되는 범주 이름을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="7b854-113">특정 명명 규칙이 나 기타 액세스 제어 또는 유효성 검사를 구현할 경우에는 사용자 지정 대화방 만들기 워크플로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="7b854-114">영구 채팅 구성을 사용 하면 호스트 하는 항목에 대해 **RoomManagementUrl** 를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="7b854-115">예를 들어 사용자가 Lync 클라이언트에서 **대화방 만들기** 를 클릭 하면 사용자 지정 솔루션으로 리디렉션될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="7b854-116">다른 비즈니스 데이터를 대화방에 추가 하 여 대화방의 경험을 향상 시키는 데 도움이 되는 다양 한 추가할 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="7b854-117">관리자는 시스템에서 허용 하려는 추가 기능을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="7b854-118">대화방 관리자 및 작성자는 해당 채팅방에 가장 적합 한 추가 기능 목록 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b854-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7b854-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b854-119">See Also</span></span>


[<span data-ttu-id="7b854-120">Lync Server 2013에서 범주, 대화방 및 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="7b854-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

