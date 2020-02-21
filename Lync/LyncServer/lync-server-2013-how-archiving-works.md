---
title: 'Lync Server 2013: 보관 작동 방식'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc6266cdf81f4462adf82c5878bcc47a6060fdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="cd69c-102">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="cd69c-102">How Archiving works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd69c-103">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="cd69c-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="cd69c-104">Lync Server 2013 보관은 준수 요구 사항을 충족 하는 데 도움이 되는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-104">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="cd69c-105">조직의 요구 사항을 가장 효율적으로 충족 하는 방식으로 구현 하 고 유지 관리 하려면 다음 사항을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-105">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="cd69c-106">보관할 수 있는 정보</span><span class="sxs-lookup"><span data-stu-id="cd69c-106">What information can be archived.</span></span>

  - <span data-ttu-id="cd69c-107">사용자의 배포 환경에서 보관을 설정하고 해제하는 방법</span><span class="sxs-lookup"><span data-stu-id="cd69c-107">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="cd69c-108">보관의 구현 방법을 제어하기 위해 구성할 수 있는 보관 옵션</span><span class="sxs-lookup"><span data-stu-id="cd69c-108">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="cd69c-109">보관할 수 있는 정보</span><span class="sxs-lookup"><span data-stu-id="cd69c-109">What Information Can Be Archived?</span></span>

<span data-ttu-id="cd69c-110">보관할 수 있는 콘텐츠 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-110">The following types of content can be archived:</span></span>

  - <span data-ttu-id="cd69c-111">피어 투 피어 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="cd69c-111">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="cd69c-112">단체 인스턴트 메시지인 회의(모임)</span><span class="sxs-lookup"><span data-stu-id="cd69c-112">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="cd69c-113">업로드된 콘텐츠(예: 참고 파일) 및 이벤트 관련 콘텐츠(예: 입장, 퇴장, 업로드 공유 및 표시 여부 변경)를 비롯한 회의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="cd69c-113">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="cd69c-114">회의 중 공유된 화이트보드 및 설문</span><span class="sxs-lookup"><span data-stu-id="cd69c-114">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="cd69c-115">보관되지 않는 콘텐츠 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-115">The following types of content are not archived:</span></span>

  - <span data-ttu-id="cd69c-116">피어 투 피어 파일 전송</span><span class="sxs-lookup"><span data-stu-id="cd69c-116">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="cd69c-117">피어 투 피어 인스턴스 메시지 및 회의에 대한 오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="cd69c-117">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="cd69c-118">피어 투 피어 인스턴스 메시지 및 회의에 대한 데스크톱 및 응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="cd69c-118">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="cd69c-119">또한 Lync Server에서는 영구 채팅 대화를 보관 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-119">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="cd69c-120">영구 채팅 대화를 보관 하려면 Microsoft Lync Server 2013, 영구 채팅 서버를 사용 하 여 배포할 수 있는 구성 요소인 준수 서비스를 사용 하도록 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-120">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="cd69c-121">자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-121">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="cd69c-122">보관 사용을 시작하는 방법</span><span class="sxs-lookup"><span data-stu-id="cd69c-122">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="cd69c-p103">보관은 서버를 배포할 때 각 프런트 엔드 서버에 자동으로 설치되지만 사용자가 구성하기 전까지는 사용하도록 설정되지 않습니다. 구성 방법은 보관의 배포 방법에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="cd69c-125">**Microsoft Exchange 통합을 사용 하 여 보관**</span><span class="sxs-lookup"><span data-stu-id="cd69c-125">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="cd69c-126">Exchange 2013에 있는 사용자가 있고 해당 사서함이 원본 위치 유지 상태로 설정 되어 있는 경우 Lync Server 2013 저장소를 Exchange 저장소와 통합 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-126">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="cd69c-127">Microsoft Exchange 통합 옵션을 선택 하는 경우 Exchange 2013 정책 및 구성을 사용 하 여 해당 사용자에 대 한 Lync Server 2013 데이터 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-127">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="cd69c-128">**Lync Server 보관 데이터베이스를 사용 하 여 보관**</span><span class="sxs-lookup"><span data-stu-id="cd69c-128">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="cd69c-129">Exchange 2013에 속하지 않았거나 사서함에 원본 위치 유지를 설정 하지 않았거나 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않으려는 경우 또는, SQL Server를 사용 하 여 Lync Server 보관 데이터베이스를 배포할 수 있습니다.  해당 사용자에 대 한 보관 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-129">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="cd69c-130">이 경우 Lync Server 2013 보관 정책 및 구성에서는 보관이 사용 되는지 여부와이를 구현 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-130">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="cd69c-131">Lync Server 2013을 사용 하려면 적절 한 SQL Server 데이터베이스를 토폴로지에 추가 하 고 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-131">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="cd69c-132">Microsoft Exchange 통합을 사용 하는 경우 보관 설정</span><span class="sxs-lookup"><span data-stu-id="cd69c-132">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="cd69c-133">사용자가 Exchange 2013에 있고 해당 사서함이 원본 위치 유지 상태로 설정 된 경우에는이 섹션의 뒷부분에 설명 된 **Microsoft Exchange 통합** 옵션을 선택 하 여 해당 사용자에 대 한 lync server 2013를 보관 한 다음 Exchange 원본 위치 유지 정책 및 설정을 지정 하 여 해당 사용자에 대 한 보관을 제어할 수 있으며, lync server 구성을 사용 하 여 다음을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-133">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="cd69c-134">IM이나 회의 내용 또는 두 가지를 모두 보관할지 여부</span><span class="sxs-lookup"><span data-stu-id="cd69c-134">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="cd69c-135">Lync Server 배포에 대해 중요 모드를 구현할지 여부</span><span class="sxs-lookup"><span data-stu-id="cd69c-135">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="cd69c-136">Microsoft Exchange 통합 옵션을 선택한 후 보관 된 데이터를 저장 하는 데 Exchange 2013을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-136">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="cd69c-137">이러한 Lync Server 2013 보관 구성 옵션에 대해서는이 섹션 뒷부분에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-137">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="cd69c-138">보관을 지원 하기 위해 Exchange 원본 위치 유지 정책 및 설정을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-138">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="cd69c-139">Lync Server 보관 데이터베이스 저장소를 사용할 경우의 보관 설정</span><span class="sxs-lookup"><span data-stu-id="cd69c-139">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="cd69c-140">SQL Server 데이터베이스를 사용 하 여 Lync Server 보관 데이터베이스를 사용 하 여 배포의 모든 사용자에 대 한 데이터를 보관 하려면 해당 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하는 Lync Server 보관 정책을 구성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-140">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="cd69c-141">각 보관 정책에서는 다음 두 항목 중 하나 또는 모두에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-141">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="cd69c-142">내부 통신</span><span class="sxs-lookup"><span data-stu-id="cd69c-142">Internal communications</span></span>

  - <span data-ttu-id="cd69c-143">외부 통신</span><span class="sxs-lookup"><span data-stu-id="cd69c-143">External communications</span></span>

<span data-ttu-id="cd69c-144">기본적으로 모든 Lync Server 보관 정책의 내부 통신 또는 외부 통신에 대해 보관을 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-144">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="cd69c-145">Lync server 2013 제어판 또는 Lync Server 2013 관리 셸에서 cmdlet을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-145">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="cd69c-146">Lync Server 2013 보관 정책에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-146">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="cd69c-147">**전역 보관 정책**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-147">**Global Archiving policy**.</span></span> <span data-ttu-id="cd69c-148">기본 보관 정책이며 전체 배포에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-148">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="cd69c-149">이 기능은 Lync Server 2013를 배포할 때 만들어지며 기본적으로 내부 및 외부 통신 모두에 대해 보관을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-149">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="cd69c-150">이 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-150">You cannot delete this policy.</span></span> <span data-ttu-id="cd69c-151">삭제 옵션을 선택하더라도 글로벌 정책은 기본 설정으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-151">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="cd69c-p110">**사이트 보관 정책**. 선택적으로 사이트에 대한 사이트 수준의 보관 정책을 만들고 구성해서 하나 이상의 특정 사이트에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사이트 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만든 사이트 수준의 보관 정책은 삭제할 수 있습니다. 사이트 수준의 보관 정책은 글로벌 정책을 무시하지만 해당 정책에 지정된 사이트로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하도록 설정하고 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사이트 정책을 만들었다면 해당 사이트에 대해서는 내부 통신만 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="cd69c-p111">**사용자 보관 정책**. 선택적으로 지정된 사용자 및 사용자 그룹에 대해 사용자 수준의 보관 정책을 만들고, 구성 및 적용하여 하나 이상의 특정 사용자 및 사용자 그룹에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사용자 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만드는 사용자 수준의 보관 정책은 삭제할 수 있으며 해당 보관 정책이 적용되는 사용자 및 사용자 그룹을 변경할 수 있습니다. 사용자 수준의 보관 정책은 글로벌 정책 및 모든 사이트 정책을 무시하지만 해당 정책이 적용되는 사용자 및 사용자 그룹으로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하지 않도록 설정하고, 내부 및 외부 통신에 대한 보관을 사용하도록 설정하는 사이트 수준의 정책을 만들고, 다시 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사용자 수준의 정책을 만들었다면 사용자 수준의 정책이 적용되는 사용자의 경우 내부 통신만 보관되고 이를 제외한 모든 사이트 사용자에 대해서는 외부 및 내부 통신이 모두 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="cd69c-164">보관을 배포할 때 초기 보관 정책을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 " [Lync Server 2013에서 보관 정책 구성 및 할당](lync-server-2013-configuring-and-assigning-archiving-policies.md) "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-164">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="cd69c-165">배포 후 보관 정책을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd69c-165">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd69c-166">Lync Server 2013 보관 데이터베이스를 모두 구현 하 고 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013 정책은 Lync Server 보관 정책 보다 우선 하지만 Exchange 2013에 속해 있으며 사서함이 원본 위치 유지 상태로 설정 된 사용자 에게만 적용 됩니다. .</span><span class="sxs-lookup"><span data-stu-id="cd69c-166">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cd69c-167">Lync 보관은 Microsoft Exchange 원본 위치 유지 정책만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-167">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="cd69c-168">보관 구성을 위한 옵션</span><span class="sxs-lookup"><span data-stu-id="cd69c-168">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="cd69c-169">정책을 사용하고 보관을 사용 및 사용하지 않도록 설정하는 것 외에도 전체 배포에 대해 그리고 선택적으로 특정 사이트 및 풀에 대해 구성할 수 있는 보관 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-169">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="cd69c-170">Lync Server 2013 제어판에서 사용할 수 있는 하나 이상의 보관 구성을 사용 하 여 대부분의 보관 옵션을 제어 하지만 Lync Server 2013 관리 셸을 사용 하 여 구성에만 사용할 수 있는 다른 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-170">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="cd69c-171">Lync Server 2013 제어판에서 제공되는 보관 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="cd69c-171">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="cd69c-172">각 보관 구성은 다음과 같은 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-172">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="cd69c-p115">전역 수준의 구성은 보관을 배포할 때 자동으로 만들어지며, 사용자가 구성할 수 있지만 삭제할 수는 없습니다. 전역 구성을 삭제하도록 옵션을 선택해도 설정이 기본값으로 다시 설정됩니다. 전역 구성과 함께 보관 설정을 제어하는 사이트 및 풀 구성은 여러 개 만들 수 있습니다. 전역 구성과 각 사이트 및 풀 구성에서는 다음과 같은 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="cd69c-177">보관을 사용하지 않도록 설정하거나, IM(인스턴트 메시징)에 대해서만 보관을 사용하도록 설정하거나, IM 및 회의 모두 보관을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-177">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="cd69c-178">Lync Server 오류가 발생 하는 경우 IM 및 회의 세션을 차단 하도록 중요 모드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-178">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="cd69c-179">오류에는 다음 항목들이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-179">Failures include the following:</span></span>
    
      - <span data-ttu-id="cd69c-180">**IM**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-180">**IM**.</span></span> <span data-ttu-id="cd69c-181">Lync Server 저장소 서비스에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-181">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="cd69c-182">이 경우 보관을 사용하도록 설정된 사용자의 IM이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-182">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="cd69c-p118">**회의**. 오류는 사용할 수 없는 파일 공유이거나 저장소 서비스 관련 문제일 수 있습니다. 이 경우 오류 시점에 풀에 호스팅된 모든 활성 회의가 제한 모드로 전환되고 새로운 회의를 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="cd69c-186">오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-186">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="cd69c-187">Lync Server 2013 보관 데이터를 저장 하기 위해 별도의 SQL Server 데이터베이스를 설정 하는 대신 Microsoft Exchange Server 2013 통합을 사용 하 여 보관 된 데이터를 저장할 수 있도록 Exchange 2013를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-187">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="cd69c-p119">보관된 데이터의 삭제 옵션을 구성합니다. 여기에는 다음 두 가지 중 하나일 수 있는 보관된 데이터를 삭제할 시간 지정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="cd69c-190">지정한 특정 일 수 이후</span><span class="sxs-lookup"><span data-stu-id="cd69c-190">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="cd69c-191">보관 데이터를 내보낸 후에 (Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange로 업로드 된 데이터 포함)</span><span class="sxs-lookup"><span data-stu-id="cd69c-191">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd69c-192">Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013에 있는 사용자를 제거 하 고 해당 사서함을 원본 위치 유지에 사용 하는 경우 Exchange에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-192">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="cd69c-193">유일한 자격 증명은 Lync Server 파일 공유에 저장 되는 회의 파일에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-193">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="cd69c-194">이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-194">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="cd69c-195">기본적으로는 모든 보관 옵션이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-195">By default, no archiving options are enabled.</span></span> <span data-ttu-id="cd69c-196">Lync Server 2013 제어판을 사용 하 여 보관 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-196">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="cd69c-197">다음 보관 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-197">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="cd69c-198">**전역 보관 구성**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-198">**Global Archiving configuration**.</span></span> <span data-ttu-id="cd69c-199">이 구성은 기본 보관 구성이며 전체 배포에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-199">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="cd69c-200">이 도구는 Lync Server 2013를 배포할 때 만들어지며 기본적으로 보관 기능을 사용 하도록 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-200">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="cd69c-201">전역 구성은 수정할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-201">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="cd69c-202">구성에 대한 삭제 옵션을 선택해도 전역 구성이 기본 설정으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-202">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="cd69c-p123">**사이트 보관 구성**. 선택적으로 개별 사이트에 대해 사이트 수준의 보관 구성을 만들고 구성하여 하나 이상의 특정 사이트에 대한 보관을 구성할 수 있습니다. 사이트 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 사이트 수준의 보관 구성은 수정하거나 삭제할 수 있습니다. 사이트 수준의 보관 구성은 전역 구성을 무시하지만 해당 사이트 수준의 구성에 지정된 사이트로만 제한됩니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고 IM 및 회의 모두에 대해 보관을 사용하도록 설정하는 사이트 구성을 만들었다면 조직 전체가 아니라 해당 사이트에 대해서만 회의 내용이 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="cd69c-p124">**풀 보관 구성**. 선택적으로 개별 풀에 대해 풀 수준의 구성을 만들고 구성하여 하나 이상의 특정 풀에 대한 보관 설정을 지정할 수 있습니다. 풀 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 풀 수준의 보관 구성은 수정 및 삭제할 수 있습니다. 풀 수준의 보관 구성은 전역 구성 및 사용자가 만들었을 수 있는 모든 사이트 보관 구성을 무시합니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고, 특정 사이트에 대해 IM 및 회의 모두 보관을 사용하도록 설정하는 사이트 수준의 구성을 만들고, IM에 대해서만 보관을 사용하도록 설정하는 풀 수준의 구성을 만들었으면 풀 수준 구성에 지정된 풀에 있는 사용자를 제외하고 해당 사이트의 모든 사용자에 대해 IM과 회의 내용 모두 통신이 보관됩니다. 조직 내 다른 모든 사용자의 경우에는 IM에 대해서만 보관이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="cd69c-216">보관을 배포할 때 초기 보관 구성을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관 옵션 구성을](lync-server-2013-configuring-archiving-options.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-216">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="cd69c-217">보관 정책을 사용 하 여 배포 후에 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [조직, 사이트 및 풀에 대해 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-217">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="cd69c-218">Windows PowerShell에서만 사용 가능한 보관 옵션</span><span class="sxs-lookup"><span data-stu-id="cd69c-218">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="cd69c-219">Lync Server 2013 관리 셸을 사용 하 여 cmdlet을 사용 하 여 Lync Server 2013 제어판에서는 사용할 수 없는 옵션을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-219">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="cd69c-220">이러한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-220">These options include the following:</span></span>

  - <span data-ttu-id="cd69c-221">**중복 메시지 보관**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-221">**Archive duplicate messages**.</span></span> <span data-ttu-id="cd69c-222">자세한 내용은 작업 설명서에서 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 및 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-222">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="cd69c-223">**보관된 데이터 내보내기**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-223">**Export archived data**.</span></span> <span data-ttu-id="cd69c-224">자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-224">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="cd69c-225">보관된 데이터에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="cd69c-225">How Do I Access Archived Data?</span></span>

<span data-ttu-id="cd69c-226">보관된 데이터에 대한 액세스는 데이터가 저장된 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-226">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="cd69c-227">**Microsoft Exchange 저장소**</span><span class="sxs-lookup"><span data-stu-id="cd69c-227">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="cd69c-228">Exchange 통합 옵션을 선택 하면 Lync Server는 exchange 2013에 있는 모든 사용자에 대해 exchange 2013 저장소의 보관 콘텐츠를 저축금과 하 고 사서함이 원본 위치 유지 상태로 설정 된 경우를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-228">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cd69c-229">보관 된 데이터는 사용자에 게 표시 되지 않으며 Exchange **검색 관리** 역할을 가진 사용자만 검색할 수 있도록 하는 User 사서함 복구 가능한 항목 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-229">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="cd69c-230">Exchange에서는 연결 된 검색 및 검색과 SharePoint (배포 된 경우)를 함께 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-230">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="cd69c-231">Exchange에 저장 된 데이터의 저장, 보존 및 검색에 대 한 자세한 내용은 Exchange 2013 및 SharePoint 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd69c-231">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="cd69c-232">**Lync Server 저장소**.</span><span class="sxs-lookup"><span data-stu-id="cd69c-232">**Lync Server storage**.</span></span> <span data-ttu-id="cd69c-233">Lync server 데이터 저장용 lync server 2013 보관 데이터베이스를 설정 하는 경우 lync Server 저축금과 Exchange 2013에 포함 되지 않은 모든 사용자에 대 한 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)의 콘텐츠를 보관 합니다. 원본 위치 유지</span><span class="sxs-lookup"><span data-stu-id="cd69c-233">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cd69c-234">이 데이터는 검색할 수 없지만 다른 도구를 사용해서 검색할 수 있는 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd69c-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="cd69c-235">보관 데이터베이스에 저장 된 데이터를 내보내는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013에서 보관 된 데이터 내보내기를](lync-server-2013-exporting-archived-data.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-235">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="cd69c-236">Lync Server 2013 및 Exchange 2013가 함께 작동 하는 방식에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) (영문)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd69c-236">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

