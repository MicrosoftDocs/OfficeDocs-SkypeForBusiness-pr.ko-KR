---
title: 'Lync Server 2013: 보관 작동 방식'
description: 'Lync Server 2013: 보관이 작동 하는 방식입니다.'
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
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543384"
---
# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="ecf39-103">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="ecf39-103">How Archiving works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecf39-104">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="ecf39-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="ecf39-105">Lync Server 2013 보관은 준수 요구 사항을 충족 하는 데 도움이 되는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-105">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="ecf39-106">조직의 요구 사항을 가장 효율적으로 충족 하는 방식으로 구현 하 고 유지 관리 하려면 다음 사항을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-106">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="ecf39-107">보관할 수 있는 정보</span><span class="sxs-lookup"><span data-stu-id="ecf39-107">What information can be archived.</span></span>

  - <span data-ttu-id="ecf39-108">사용자의 배포 환경에서 보관을 설정하고 해제하는 방법</span><span class="sxs-lookup"><span data-stu-id="ecf39-108">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="ecf39-109">보관의 구현 방법을 제어하기 위해 구성할 수 있는 보관 옵션</span><span class="sxs-lookup"><span data-stu-id="ecf39-109">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="ecf39-110">보관할 수 있는 정보</span><span class="sxs-lookup"><span data-stu-id="ecf39-110">What Information Can Be Archived?</span></span>

<span data-ttu-id="ecf39-111">보관할 수 있는 콘텐츠 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-111">The following types of content can be archived:</span></span>

  - <span data-ttu-id="ecf39-112">피어 투 피어 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="ecf39-112">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="ecf39-113">단체 인스턴트 메시지인 회의(모임)</span><span class="sxs-lookup"><span data-stu-id="ecf39-113">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="ecf39-114">업로드된 콘텐츠(예: 참고 파일) 및 이벤트 관련 콘텐츠(예: 입장, 퇴장, 업로드 공유 및 표시 여부 변경)를 비롯한 회의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ecf39-114">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="ecf39-115">회의 중 공유된 화이트보드 및 설문</span><span class="sxs-lookup"><span data-stu-id="ecf39-115">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="ecf39-116">보관되지 않는 콘텐츠 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-116">The following types of content are not archived:</span></span>

  - <span data-ttu-id="ecf39-117">피어 투 피어 파일 전송</span><span class="sxs-lookup"><span data-stu-id="ecf39-117">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="ecf39-118">피어 투 피어 인스턴스 메시지 및 회의에 대한 오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="ecf39-118">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="ecf39-119">피어 투 피어 인스턴스 메시지 및 회의에 대한 데스크톱 및 응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="ecf39-119">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="ecf39-120">또한 Lync Server에서는 영구 채팅 대화를 보관 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-120">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="ecf39-121">영구 채팅 대화를 보관 하려면 Microsoft Lync Server 2013, 영구 채팅 서버를 사용 하 여 배포할 수 있는 구성 요소인 준수 서비스를 사용 하도록 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-121">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="ecf39-122">자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-122">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="ecf39-123">보관 사용을 시작하는 방법</span><span class="sxs-lookup"><span data-stu-id="ecf39-123">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="ecf39-p103">보관은 서버를 배포할 때 각 프런트 엔드 서버에 자동으로 설치되지만 사용자가 구성하기 전까지는 사용하도록 설정되지 않습니다. 구성 방법은 보관의 배포 방법에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="ecf39-126">**Microsoft Exchange 통합을 사용 하 여 보관**</span><span class="sxs-lookup"><span data-stu-id="ecf39-126">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="ecf39-127">Exchange 2013에 있는 사용자가 있고 해당 사서함이 보존 In-Place 있는 경우 Lync Server 2013 storage with Exchange storage를 통합 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-127">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="ecf39-128">Microsoft Exchange 통합 옵션을 선택 하는 경우 Exchange 2013 정책 및 구성을 사용 하 여 해당 사용자에 대 한 Lync Server 2013 데이터 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-128">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="ecf39-129">**Lync Server 보관 데이터베이스를 사용 하 여 보관**</span><span class="sxs-lookup"><span data-stu-id="ecf39-129">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="ecf39-130">Exchange 2013에 있지 않거나 사서함이 보존 In-Place에 포함 되지 않은 사용자가 있거나, 배포 환경의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않으려는 경우 또는 해당 사용자에 대 한 보관 데이터를 저장 하기 위해 SQL Server를 사용 하 여 Lync Server 보관 데이터베이스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-130">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="ecf39-131">이 경우 Lync Server 2013 보관 정책 및 구성에서는 보관이 사용 되는지 여부와이를 구현 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-131">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="ecf39-132">Lync Server 2013을 사용 하려면 적절 한 SQL Server 데이터베이스를 토폴로지에 추가 하 고 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-132">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="ecf39-133">Microsoft Exchange 통합을 사용 하는 경우 보관 설정</span><span class="sxs-lookup"><span data-stu-id="ecf39-133">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="ecf39-134">사용자가 Exchange 2013에 있고 해당 사서함이 보존 In-Place에 있는 경우에는이 섹션 뒷부분에서 설명 하는 **Microsoft Exchange 통합** 옵션을 선택 하 여 해당 사용자에 대 한 lync server 2013를 보관 한 다음 Exchange In-Place 보류 정책 및 설정을 지정 하 여 해당 사용자에 대 한 보관을 제어할 수 있으며, Lync server 구성을 통해 다음을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-134">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="ecf39-135">IM이나 회의 내용 또는 두 가지를 모두 보관할지 여부</span><span class="sxs-lookup"><span data-stu-id="ecf39-135">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="ecf39-136">Lync Server 배포에 대해 중요 모드를 구현할지 여부</span><span class="sxs-lookup"><span data-stu-id="ecf39-136">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="ecf39-137">Microsoft Exchange 통합 옵션을 선택한 후 보관 된 데이터를 저장 하는 데 Exchange 2013을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-137">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="ecf39-138">이러한 Lync Server 2013 보관 구성 옵션에 대해서는이 섹션 뒷부분에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-138">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="ecf39-139">보관을 지원 하기 위해 Exchange In-Place 보류 정책 및 설정을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-139">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="ecf39-140">Lync Server 보관 데이터베이스 저장소를 사용할 경우의 보관 설정</span><span class="sxs-lookup"><span data-stu-id="ecf39-140">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="ecf39-141">SQL Server 데이터베이스를 사용 하 여 Lync Server 보관 데이터베이스를 사용 하 여 배포의 모든 사용자에 대 한 데이터를 보관 하려면 해당 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하는 Lync Server 보관 정책을 구성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-141">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="ecf39-142">각 보관 정책에서는 다음 두 항목 중 하나 또는 모두에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-142">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="ecf39-143">내부 통신</span><span class="sxs-lookup"><span data-stu-id="ecf39-143">Internal communications</span></span>

  - <span data-ttu-id="ecf39-144">외부 통신</span><span class="sxs-lookup"><span data-stu-id="ecf39-144">External communications</span></span>

<span data-ttu-id="ecf39-145">기본적으로 모든 Lync Server 보관 정책의 내부 통신 또는 외부 통신에 대해 보관을 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-145">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="ecf39-146">Lync server 2013 제어판 또는 Lync Server 2013 관리 셸에서 cmdlet을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-146">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="ecf39-147">Lync Server 2013 보관 정책에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-147">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="ecf39-148">**전역 보관 정책**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-148">**Global Archiving policy**.</span></span> <span data-ttu-id="ecf39-149">기본 보관 정책이며 전체 배포에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-149">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="ecf39-150">이 기능은 Lync Server 2013를 배포할 때 만들어지며 기본적으로 내부 및 외부 통신 모두에 대해 보관을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-150">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="ecf39-151">이 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-151">You cannot delete this policy.</span></span> <span data-ttu-id="ecf39-152">삭제 옵션을 선택하더라도 글로벌 정책은 기본 설정으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-152">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="ecf39-p110">**사이트 보관 정책**. 선택적으로 사이트에 대한 사이트 수준의 보관 정책을 만들고 구성해서 하나 이상의 특정 사이트에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사이트 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만든 사이트 수준의 보관 정책은 삭제할 수 있습니다. 사이트 수준의 보관 정책은 글로벌 정책을 무시하지만 해당 정책에 지정된 사이트로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하도록 설정하고 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사이트 정책을 만들었다면 해당 사이트에 대해서는 내부 통신만 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="ecf39-p111">**사용자 보관 정책**. 선택적으로 지정된 사용자 및 사용자 그룹에 대해 사용자 수준의 보관 정책을 만들고, 구성 및 적용하여 하나 이상의 특정 사용자 및 사용자 그룹에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사용자 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만드는 사용자 수준의 보관 정책은 삭제할 수 있으며 해당 보관 정책이 적용되는 사용자 및 사용자 그룹을 변경할 수 있습니다. 사용자 수준의 보관 정책은 글로벌 정책 및 모든 사이트 정책을 무시하지만 해당 정책이 적용되는 사용자 및 사용자 그룹으로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하지 않도록 설정하고, 내부 및 외부 통신에 대한 보관을 사용하도록 설정하는 사이트 수준의 정책을 만들고, 다시 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사용자 수준의 정책을 만들었다면 사용자 수준의 정책이 적용되는 사용자의 경우 내부 통신만 보관되고 이를 제외한 모든 사이트 사용자에 대해서는 외부 및 내부 통신이 모두 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="ecf39-165">보관을 배포할 때 초기 보관 정책을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 " [Lync Server 2013에서 보관 정책 구성 및 할당](lync-server-2013-configuring-and-assigning-archiving-policies.md) "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-165">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="ecf39-166">배포 후 보관 정책을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecf39-166">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ecf39-167">Lync Server 2013 보관 데이터베이스를 모두 구현 하 고 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013 정책은 Exchange 2013에 있는 사용자에 한 해 해당 사서함을 In-Place 보류 상태로 유지 한 상태에서 Lync Server 보관 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-167">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ecf39-168">Lync 보관은 Microsoft Exchange In-Place 보류 정책만 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-168">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="ecf39-169">보관 구성을 위한 옵션</span><span class="sxs-lookup"><span data-stu-id="ecf39-169">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="ecf39-170">정책을 사용하고 보관을 사용 및 사용하지 않도록 설정하는 것 외에도 전체 배포에 대해 그리고 선택적으로 특정 사이트 및 풀에 대해 구성할 수 있는 보관 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-170">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="ecf39-171">Lync Server 2013 제어판에서 사용할 수 있는 하나 이상의 보관 구성을 사용 하 여 대부분의 보관 옵션을 제어 하지만 Lync Server 2013 관리 셸을 사용 하 여 구성에만 사용할 수 있는 다른 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-171">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="ecf39-172">Lync Server 2013 제어판에서 제공되는 보관 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="ecf39-172">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="ecf39-173">각 보관 구성은 다음과 같은 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-173">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="ecf39-p115">전역 수준의 구성은 보관을 배포할 때 자동으로 만들어지며, 사용자가 구성할 수 있지만 삭제할 수는 없습니다. 전역 구성을 삭제하도록 옵션을 선택해도 설정이 기본값으로 다시 설정됩니다. 전역 구성과 함께 보관 설정을 제어하는 사이트 및 풀 구성은 여러 개 만들 수 있습니다. 전역 구성과 각 사이트 및 풀 구성에서는 다음과 같은 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="ecf39-178">보관을 사용하지 않도록 설정하거나, IM(인스턴트 메시징)에 대해서만 보관을 사용하도록 설정하거나, IM 및 회의 모두 보관을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-178">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="ecf39-179">Lync Server 오류가 발생 하는 경우 IM 및 회의 세션을 차단 하도록 중요 모드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-179">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="ecf39-180">오류에는 다음 항목들이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-180">Failures include the following:</span></span>
    
      - <span data-ttu-id="ecf39-181">**IM**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-181">**IM**.</span></span> <span data-ttu-id="ecf39-182">Lync Server 저장소 서비스에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-182">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="ecf39-183">이 경우 보관을 사용하도록 설정된 사용자의 IM이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-183">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="ecf39-p118">**회의**. 오류는 사용할 수 없는 파일 공유이거나 저장소 서비스 관련 문제일 수 있습니다. 이 경우 오류 시점에 풀에 호스팅된 모든 활성 회의가 제한 모드로 전환되고 새로운 회의를 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="ecf39-187">오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-187">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="ecf39-188">Lync Server 2013 보관 데이터를 저장 하기 위해 별도의 SQL Server 데이터베이스를 설정 하는 대신 Microsoft Exchange Server 2013 통합을 사용 하 여 보관 된 데이터를 저장할 수 있도록 Exchange 2013를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-188">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="ecf39-p119">보관된 데이터의 삭제 옵션을 구성합니다. 여기에는 다음 두 가지 중 하나일 수 있는 보관된 데이터를 삭제할 시간 지정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="ecf39-191">지정한 특정 일 수 이후</span><span class="sxs-lookup"><span data-stu-id="ecf39-191">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="ecf39-192">보관 데이터를 내보낸 후에 (Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange로 업로드 된 데이터 포함)</span><span class="sxs-lookup"><span data-stu-id="ecf39-192">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecf39-193">Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013에 있는 사용자에 대해 삭제 하 고 해당 사서함을 포함 하는 In-Place는 Exchange에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-193">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="ecf39-194">유일한 자격 증명은 Lync Server 파일 공유에 저장 되는 회의 파일에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-194">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="ecf39-195">이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-195">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="ecf39-196">기본적으로는 모든 보관 옵션이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-196">By default, no archiving options are enabled.</span></span> <span data-ttu-id="ecf39-197">Lync Server 2013 제어판을 사용 하 여 보관 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-197">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="ecf39-198">다음 보관 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-198">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="ecf39-199">**전역 보관 구성**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-199">**Global Archiving configuration**.</span></span> <span data-ttu-id="ecf39-200">이 구성은 기본 보관 구성이며 전체 배포에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-200">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="ecf39-201">이 도구는 Lync Server 2013를 배포할 때 만들어지며 기본적으로 보관 기능을 사용 하도록 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-201">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="ecf39-202">전역 구성은 수정할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-202">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="ecf39-203">구성에 대한 삭제 옵션을 선택해도 전역 구성이 기본 설정으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-203">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="ecf39-p123">**사이트 보관 구성**. 선택적으로 개별 사이트에 대해 사이트 수준의 보관 구성을 만들고 구성하여 하나 이상의 특정 사이트에 대한 보관을 구성할 수 있습니다. 사이트 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 사이트 수준의 보관 구성은 수정하거나 삭제할 수 있습니다. 사이트 수준의 보관 구성은 전역 구성을 무시하지만 해당 사이트 수준의 구성에 지정된 사이트로만 제한됩니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고 IM 및 회의 모두에 대해 보관을 사용하도록 설정하는 사이트 구성을 만들었다면 조직 전체가 아니라 해당 사이트에 대해서만 회의 내용이 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="ecf39-p124">**풀 보관 구성**. 선택적으로 개별 풀에 대해 풀 수준의 구성을 만들고 구성하여 하나 이상의 특정 풀에 대한 보관 설정을 지정할 수 있습니다. 풀 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 풀 수준의 보관 구성은 수정 및 삭제할 수 있습니다. 풀 수준의 보관 구성은 전역 구성 및 사용자가 만들었을 수 있는 모든 사이트 보관 구성을 무시합니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고, 특정 사이트에 대해 IM 및 회의 모두 보관을 사용하도록 설정하는 사이트 수준의 구성을 만들고, IM에 대해서만 보관을 사용하도록 설정하는 풀 수준의 구성을 만들었으면 풀 수준 구성에 지정된 풀에 있는 사용자를 제외하고 해당 사이트의 모든 사용자에 대해 IM과 회의 내용 모두 통신이 보관됩니다. 조직 내 다른 모든 사용자의 경우에는 IM에 대해서만 보관이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="ecf39-217">보관을 배포할 때 초기 보관 구성을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관 옵션 구성을](lync-server-2013-configuring-archiving-options.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-217">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="ecf39-218">보관 정책을 사용 하 여 배포 후에 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [조직, 사이트 및 풀에 대해 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-218">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="ecf39-219">Windows PowerShell에서만 사용 가능한 보관 옵션</span><span class="sxs-lookup"><span data-stu-id="ecf39-219">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="ecf39-220">Lync Server 2013 관리 셸을 사용 하 여 cmdlet을 사용 하 여 Lync Server 2013 제어판에서는 사용할 수 없는 옵션을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-220">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="ecf39-221">이러한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-221">These options include the following:</span></span>

  - <span data-ttu-id="ecf39-222">**중복 메시지 보관**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-222">**Archive duplicate messages**.</span></span> <span data-ttu-id="ecf39-223">자세한 내용은 작업 설명서에서 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 및 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-223">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="ecf39-224">**보관된 데이터 내보내기**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-224">**Export archived data**.</span></span> <span data-ttu-id="ecf39-225">자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-225">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="ecf39-226">보관된 데이터에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="ecf39-226">How Do I Access Archived Data?</span></span>

<span data-ttu-id="ecf39-227">보관된 데이터에 대한 액세스는 데이터가 저장된 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-227">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="ecf39-228">**Microsoft Exchange 저장소**</span><span class="sxs-lookup"><span data-stu-id="ecf39-228">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="ecf39-229">Exchange 통합 옵션을 선택 하면 Lync Server는 exchange 2013에 있는 모든 사용자의 Exchange 2013 저장소에 있는 보관 콘텐츠를 저축금과 해당 사서함이 보류 된 In-Place 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-229">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ecf39-230">보관 된 데이터는 사용자에 게 표시 되지 않으며 Exchange **검색 관리** 역할을 가진 사용자만 검색할 수 있도록 하는 User 사서함 복구 가능한 항목 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-230">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="ecf39-231">Exchange에서는 연결 된 검색 및 검색과 SharePoint (배포 된 경우)를 함께 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-231">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="ecf39-232">Exchange에 저장 된 데이터의 저장, 보존 및 검색에 대 한 자세한 내용은 Exchange 2013 및 SharePoint 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecf39-232">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="ecf39-233">**Lync Server 저장소**.</span><span class="sxs-lookup"><span data-stu-id="ecf39-233">**Lync Server storage**.</span></span> <span data-ttu-id="ecf39-234">Lync server 데이터 저장용 lync server 2013 보관 데이터베이스를 설정 하는 경우 lync Server 저축금과는 Exchange 2013에 포함 되지 않은 사용자에 대 한 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)의 콘텐츠를 보관 하 고 사서함을 In-Place 보류 상태로 두지 않은 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-234">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ecf39-235">이 데이터는 검색할 수 없지만 다른 도구를 사용해서 검색할 수 있는 형식으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf39-235">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="ecf39-236">보관 데이터베이스에 저장 된 데이터를 내보내는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013에서 보관 된 데이터 내보내기를](lync-server-2013-exporting-archived-data.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-236">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="ecf39-237">Lync Server 2013 및 Exchange 2013가 함께 작동 하는 방식에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) (영문)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ecf39-237">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

