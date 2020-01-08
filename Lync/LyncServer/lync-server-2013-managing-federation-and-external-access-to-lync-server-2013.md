---
title: 'Lync Server 2013: Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="104a3-102">Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-102">Managing federation and external access to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="104a3-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="104a3-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="104a3-104">외부 사용자를 지원 하기 위한 첫 번째 단계는 Edge 서버 또는 Edge 풀 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="104a3-105">Edge 서버 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="104a3-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="104a3-106">Lync Server 2013의 내부 배포를 설치 하 고 구성한 후 조직의 내부 사용자가 AD DS (Active Directory 도메인 서비스)에 SIP 계정이 있는 다른 내부 사용자와 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-106">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="104a3-107">공동 작업에는 인스턴트 메시지 보내기 및 받기를 비롯 하 여 현재 상태를 업데이트 하 고 회의에 참여할 수 있습니다 ("모임"이 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="104a3-107">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="104a3-108">지원 되는 외부 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하도록 외부 사용자 액세스를 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-108">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="104a3-109">외부 사용자는 배포의 원격 사용자, 페더레이션 사용자 (공공 메신저 대화 서비스 공급자의 지원 되는 사용자 포함), XMPP 페더레이션 및 컨퍼런스 참가자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-109">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="104a3-110">배포에 Lync Server 2013 Edge 서버 또는 Edge 풀 설치가 포함 된 경우에는 외부 사용자 액세스에 대 한 다양 한 옵션 및 다른 SIP 페더레이션 도메인의 구성원과 통신 하는 데 사용할 수 있는 통신 유형의 범위가 크게 확장 됩니다. SIP 페더레이션 공급자 및 XMPP 페더레이션 사용자.</span><span class="sxs-lookup"><span data-stu-id="104a3-110">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="104a3-111">Edge 서버 또는 Edge 풀을 설정한 후에는 제공 하려는 외부 사용자 액세스 유형을 사용 하도록 설정 하 고 외부 액세스를 제어 하는 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-111">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="104a3-112">Lync Server 2013에서 lync Server 제어판, Lync Server 관리 셸 또는 둘 다를 사용 하 여 외부 사용자 액세스 및 정책을 설정 하 고 작업 요구 사항에 따라 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-112">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="104a3-113">이러한 관리 도구에 대 한 자세한 내용은 운영 설명서의 [Lync server 2013 관리 도구](lync-server-2013-lync-server-administrative-tools.md) , 운영 설명서의 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) , 운영 설명서의 [Lync server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="104a3-113">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="104a3-114">외부 사용자 액세스에 대 한 구성 및 정책을 디자인할 때는 정책의 우선 순위와 정책이 적용 되는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-114">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="104a3-115">하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-115">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="104a3-116">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="104a3-116">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="104a3-117">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-117">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="104a3-118">기본적으로 조직에 대 한 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 모든 정책이 외부 사용자 액세스를 지원 하도록 구성 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-118">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="104a3-119">외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-119">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="104a3-120">여기에는 다음과 같은 외부 액세스 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-120">This includes the following external access policies:</span></span>

  - <span data-ttu-id="104a3-121">**전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-121">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="104a3-122">기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-122">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="104a3-123">전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-123">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="104a3-124">전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-124">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="104a3-125">전역 정책을 삭제 해도 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-125">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="104a3-126">대신 기본 설정으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-126">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="104a3-127">**사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-127">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="104a3-128">사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="104a3-129">예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-129">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="104a3-130">기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-130">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="104a3-131">**사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-131">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="104a3-132">사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-132">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="104a3-133">예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-133">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="104a3-134">사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-134">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="104a3-135">만들거나 편집 해야 하는 구성 설정 및 정책을 결정 하려면 다음 결정 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="104a3-135">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="104a3-136">**도메인의 내부 및 외부 사용자가 인스턴트 메시지, 웹 회의 및 오디오/비디오를 사용 하 여 공동 작업을 할 수 있도록 허용 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-136">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="104a3-137">Lync server [2013에서 원격 사용자 액세스를 제어 하는 정책을 구성 하](lync-server-2013-configure-policies-to-control-remote-user-access.md)고 [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정 하는 항목에 대 한 세부 정보 구성</span><span class="sxs-lookup"><span data-stu-id="104a3-137">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="104a3-138">**익명 사용자가 참가 하 고 배포의 사용자가 호스팅하는 회의에 초대할 수 있도록 허용 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-138">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="104a3-139">[Lync server 2013에서 익명 사용자를 지원 하도록 회의 정책 지정](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)항목에서 설명 하는 대로 설정을 구성 하 고 lync server 2013 및 [lync server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md) [에서 회의 정책 만들기 또는 수정](lync-server-2013-create-or-modify-a-conferencing-policy.md)</span><span class="sxs-lookup"><span data-stu-id="104a3-139">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="104a3-140">**사용자가 SIP 페더레이션 도메인 연락처와 통신할 수 있도록 허용 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-140">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="104a3-141">[Lync server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), lync server [2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)설정, [LYNC 2013 server에서 조직의 SIP 페더레이션 도메인 관리에 대 한](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) 자세한 내용은이 항목에서 설명 하는 대로 설정을 구성 하세요.</span><span class="sxs-lookup"><span data-stu-id="104a3-141">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="104a3-142">**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우 XMPP 페더레이션 파트너 연락처와 통신을 사용 하도록 설정 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-142">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="104a3-143">[Lync server 2013에서 XMPP 페더레이션된 사용자 액세스를 제어 하](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) 고 [lync server 2013에서 xmpp 페더레이션된 파트너를 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)하도록 정책 구성 항목에서 자세히 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-143">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="104a3-144">**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우 SIP 페더레이션 자동 검색을 사용 하도록 설정 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-144">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="104a3-145">[Lync Server 2013의 페더레이션 파트너 검색 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)항목에 설명 된 대로 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-145">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="104a3-146">**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우, 보관을 사용 하는 것을 알리는 페더레이션 대화 상대에 게 고 지 사항을 보낼 수 있도록 설정 하 고 해당 통신을 보관할지 여부를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="104a3-146">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="104a3-147">[Lync Server 2013의 페더레이션 파트너에 게 보관 거부 전송 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)항목에 설명 된 대로 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-147">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="104a3-148">**사용자가 Windows Live Messenger, AOL, Yahoo\!와 같은 공용 공급자와 통신 하는 데 사용할 수 있는 SIP 페더레이션 공급자와 통신 하도록 허용 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-148">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="104a3-149">설정 항목에서 세부 정보를 구성 하 여 lync [server 2013에서 공용 사용자 액세스를 제어 하는 정책을 구성할](lync-server-2013-configure-policies-to-control-public-user-access.md)수 있습니다. lync server[2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)설정 하 고 [LYNC server 2013에서 공용 SIP 페더레이션 공급자를 만들거나 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-149">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="104a3-150">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-150">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="104a3-151">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-151">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="104a3-152">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-152">Messenger until the service shut down date.</span></span> <span data-ttu-id="104a3-153">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="104a3-153">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="104a3-154">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-154">has been announced.</span></span> <span data-ttu-id="104a3-155">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="104a3-155">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="104a3-156">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-156">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="104a3-157">받으려면.</span><span class="sxs-lookup"><span data-stu-id="104a3-157">Messenger.</span></span> <span data-ttu-id="104a3-158">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-158">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="104a3-159">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-159">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="104a3-160">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-160">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="104a3-161">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-161">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="104a3-162">**사용자가 Microsoft Office 365, Microsoft Lync Online 및 Microsoft Lync Online 2010을 실행 하는 호스트 된 공급자 인 SIP 페더레이션 공급자와 통신할 수 있도록 허용 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-162">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft Office 365, Microsoft Lync Online and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="104a3-163">설정 항목에서 세부 정보 구성 [Lync server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정 및 [호스트 된 SIP 페더레이션 공급자 만들기 또는 편집 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="104a3-163">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="104a3-164">**일부 사용자는 온-프레미스 배포에서 홈 서버를 사용 하 고 다른 사용자는 온라인 환경에서 홈 서버로 구성 되어 있는 분할 (하이브리드이 라고도 함) 도메인에 배포 되어 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="104a3-164">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="104a3-165">[Lync server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정, [호스트 된 SIP 페더레이션 공급자 만들기 또는 편집 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 의 항목에 설명 된 대로 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-165">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="104a3-166">요구 사항이 나열 된 표를 원한다 면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-166">If you prefer a table that lists the requirements:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="104a3-167">페더레이션 또는 외부 액세스 (간) 페더레이션 또는 외부 액세스 형식 (하위)의 탭</span><span class="sxs-lookup"><span data-stu-id="104a3-167">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="104a3-168">외부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="104a3-168">External Access Policy</span></span></th>
<th><span data-ttu-id="104a3-169">액세스에 지 구성</span><span class="sxs-lookup"><span data-stu-id="104a3-169">Access Edge Config</span></span></th>
<th><span data-ttu-id="104a3-170">SIP 페더레이션 도메인</span><span class="sxs-lookup"><span data-stu-id="104a3-170">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="104a3-171">SIP 페더레이션 공급자</span><span class="sxs-lookup"><span data-stu-id="104a3-171">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="104a3-172">XMPP 페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="104a3-172">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="104a3-173">원격 사용자</span><span class="sxs-lookup"><span data-stu-id="104a3-173">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="104a3-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="104a3-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="104a3-176">SIP 페더레이션 대화 상대</span><span class="sxs-lookup"><span data-stu-id="104a3-176">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="104a3-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="104a3-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="104a3-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013에서 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="104a3-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="104a3-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="104a3-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리</a></span><span class="sxs-lookup"><span data-stu-id="104a3-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="104a3-182">XMPP 페더레이션 대화 상대</span><span class="sxs-lookup"><span data-stu-id="104a3-182">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="104a3-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="104a3-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="104a3-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="104a3-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</a></span><span class="sxs-lookup"><span data-stu-id="104a3-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="104a3-187">도메인/하이브리드 사용자 분할</span><span class="sxs-lookup"><span data-stu-id="104a3-187">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="104a3-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="104a3-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="104a3-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013에서 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집</a></span><span class="sxs-lookup"><span data-stu-id="104a3-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="104a3-191">공용 메신저 대화 서비스 연락처</span><span class="sxs-lookup"><span data-stu-id="104a3-191">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="104a3-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</a></span><span class="sxs-lookup"><span data-stu-id="104a3-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="104a3-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></span><span class="sxs-lookup"><span data-stu-id="104a3-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="104a3-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</a></span><span class="sxs-lookup"><span data-stu-id="104a3-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="104a3-195">모임 및 회의에 대 한 익명 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="104a3-195">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="104a3-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당</a></span><span class="sxs-lookup"><span data-stu-id="104a3-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="104a3-197">또한 회의 정책에서 다음과 같은 구성 설정을 고려해 야 합니다. Lync Server 2013 및 <A href="lync-server-2013-conferencing-policy-settings-reference.md">Lync server 2013에 대 한 회의 정책 설정 참조</A> <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">에서 회의 정책 만들기 또는 수정</A></span><span class="sxs-lookup"><span data-stu-id="104a3-197">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="104a3-198">조직에 대 한 외부 사용자 액세스를 설정 하지 않은 경우에도 외부 사용자 액세스를 제어 하는 데 사용 하려는 모든 정책을 포함 하 여 외부 사용자 액세스 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-198">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization.</span></span> <span data-ttu-id="104a3-199">그러나 조직에 대 한 외부 사용자 액세스를 사용할 수 있는 경우에만 구성 하는 정책 및 기타 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-199">However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization.</span></span> <span data-ttu-id="104a3-200">외부 사용자 액세스를 사용 하지 않도록 설정 하거나 외부 사용자 액세스 정책이 지원 하도록 구성 되어 있지 않은 경우 외부 사용자는 조직의 사용자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-200">External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="104a3-201">Edge 배포는 외부 사용자의 유형 (익명 사용자를 제외한, 회의를 만들 때 익명 참가자에 게 전송 되는 암호와 회의 ID를 통해 인증 된 자격 증명) 및 컨트롤 (참가자 초대)을 인증 합니다. edge 지원 구성 방법에 따라 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-201">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support.</span></span> <span data-ttu-id="104a3-202">통신을 제어 하기 위해 하나 이상의 정책을 구성 하 고 배포 내부 및 외부 사용자 들이 서로 통신 하는 방식을 정의 하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-202">In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other.</span></span> <span data-ttu-id="104a3-203">정책 및 설정에는 외부 사용자 액세스에 대 한 기본 전역 정책 외에도 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용 하도록 만들기 및 구성할 수 있는 사이트 및 사용자 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="104a3-203">The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="104a3-204">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="104a3-204">In This Section</span></span>

  - [<span data-ttu-id="104a3-205">Lync Server 2013에서 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-205">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="104a3-206">Lync Server 2013에서 조직에 대한 액세스 에지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-206">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="104a3-207">Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-207">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="104a3-208">Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-208">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="104a3-209">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="104a3-209">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="104a3-210">Lync Server 2013에서 Lync Online 고객에 대 한 페더레이션 지원 구성</span><span class="sxs-lookup"><span data-stu-id="104a3-210">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

